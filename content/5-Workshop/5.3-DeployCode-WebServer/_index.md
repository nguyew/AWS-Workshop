---
title : "Source Code Deployment and Web Server Configuration"
date : 2026-08-02
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

* Go to **EC2**.

![ec2](/AWS-Workshop/images/5-Workshop/5.3-Deploy-Config/12.png)

* Select **Instances**, then click **Connect**.

![ec2](/AWS-Workshop/images/5-Workshop/5.3-Deploy-Config/13.png)

* Verify that the instance status shows **3/3 checks passed**, then select **SSM Session Manager**.

![ec2](/AWS-Workshop/images/5-Workshop/5.3-Deploy-Config/14.png)

* Click **Connect**.

![ec2](/AWS-Workshop/images/5-Workshop/5.3-Deploy-Config/15.png)

* After clicking **Connect**, you will automatically be redirected to the **Systems Manager** session.

![ec2](/AWS-Workshop/images/5-Workshop/5.3-Deploy-Config/16.png)

## Deploy the Splitly Application on EC2

After accessing the EC2 instance through:

**EC2 → Connect → Session Manager → Connect**

Run the following command to switch to the `ec2-user` account:

```bash
sudo su - ec2-user
```

---

### 1. Create the Deployment Directory

Create a deployment directory for the Splitly project:

```bash
sudo mkdir -p /opt/splitly
sudo chown -R ec2-user:ec2-user /opt/splitly
cd /opt/splitly
```

---

### 2. Clone the Source Code from GitHub

Clone the project repository into the deployment directory:

```bash
git clone <GITHUB_REPOSITORY_URL> .
```

Example:

```bash
git clone https://github.com/username/splitly.git .
```

After cloning the repository, verify that the following directories are available:

```text
app
backend
```

The expected project structure is:

```text
/opt/splitly
├── app
└── backend
```

---

### 3. Deploy the Backend

Go to the backend directory:

```bash
cd /opt/splitly/backend
```

#### Create the Backend Environment File

Create a `.env` file:

```bash
nano .env
```

Copy the environment variables from the `.env` file in the source code and update the required values:

```env
PORT=5000

MONGODB_URI=<MONGODB_ATLAS_CONNECTION_STRING>
MONGODB_DB=Splitly

JWT_SECRET=<JWT_SECRET_KEY>

EMAIL_PROVIDER=gmail
GMAIL_SMTP_USER=<GMAIL_ADDRESS>
GMAIL_APP_PASSWORD=<GMAIL_APP_PASSWORD>
EMAIL_FROM=Splitly <<GMAIL_ADDRESS>>

AWS_REGION=ap-southeast-1
S3_RECEIPTS_BUCKET=<S3_BUCKET_NAME>
S3_RECEIPTS_PREFIX=receipts/
S3_PRESIGN_EXPIRES_SECONDS=3000

FRONTEND_URL=http://<EC2_PUBLIC_IP>

VNPAY_TMN_CODE=
VNPAY_HASH_SECRET=
VNPAY_URL=https://sandbox.vnpayment.vn/paymentv2/vpcpay.html
```

Save and close the file:

```text
Ctrl + O
Enter
Ctrl + X
```

> Do not commit the `.env` file or expose sensitive information such as the MongoDB connection string, JWT secret, Gmail App Password, or VNPay credentials.

#### Install Dependencies and Build the Backend

```bash
npm install
npm run build
```

#### Start the Backend with PM2

```bash
pm2 start dist/server.js --name splitly-api
pm2 save
pm2 status
```

The `splitly-api` process should have the following status:

```text
online
```

---

### 4. Deploy the Frontend

Go to the frontend directory:

```bash
cd /opt/splitly/app
```

#### Create the Frontend Environment File

Create a `.env.production` file:

```bash
nano .env.production
```

Copy the environment variables from the frontend source code and update the required values:

```env
VITE_API_URL=http://<EC2_PUBLIC_IP>
VITE_RECEIPTS_PUBLIC_BASE_URL=
VITE_GOOGLE_CLIENT_ID=<GOOGLE_CLIENT_ID>
```

Save and close the file:

```text
Ctrl + O
Enter
Ctrl + X
```

#### Install Dependencies and Build the Frontend

```bash
npm install
npm run build
```

#### Verify the Frontend Build

```bash
test -f dist/index.html && echo "Frontend build: OK"
```

Expected result:

```text
Frontend build: OK
```

---

### 5. Configure and Run Nginx

Create an Nginx configuration file for Splitly:

```bash
sudo nano /etc/nginx/conf.d/splitly.conf
```

Add the following configuration:

```nginx
server {
    listen 80;
    server_name _;

    root /opt/splitly/app/dist;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }

    location /api/ {
        proxy_pass http://127.0.0.1:5000;
        proxy_http_version 1.1;

        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

Save and close the file:

```text
Ctrl + O
Enter
Ctrl + X
```

#### Validate the Nginx Configuration

```bash
sudo nginx -t
```

A successful result should look similar to:

```text
syntax is ok
test is successful
```

#### Restart Nginx

```bash
sudo systemctl restart nginx
sudo systemctl is-active nginx
```

Expected result:

```text
active
```

---

### 6. Verify the Complete Deployment

Check the backend process:

```bash
pm2 status
```

Check whether the backend is listening on port `5000`:

```bash
sudo ss -lntp | grep 5000
```

Check the frontend build:

```bash
test -f /opt/splitly/app/dist/index.html && echo "Frontend build: OK"
```

Validate the Nginx configuration:

```bash
sudo nginx -t
```

Check the Nginx service:

```bash
sudo systemctl is-active nginx
```

Test the website locally:

```bash
curl -I http://127.0.0.1
```

A successful response should contain:

```text
HTTP/1.1 200 OK
```

---

### 7. Access the Splitly Application

Open a web browser and access the application using the EC2 public IP address:

```text
http://<EC2_PUBLIC_IP>
```

Example:

```text
http://13.xxx.xxx.xxx
```

If the deployment is successful, the Splitly frontend interface will be displayed. API requests beginning with `/api/` will be forwarded by Nginx to the backend application running on port `5000`.
