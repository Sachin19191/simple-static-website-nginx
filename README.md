# Project 1 - Deploy a Simple Web Application

## Prerequisites:
- An AWS Ubuntu instance (t2.micro) with SSH and HTTP traffic allowed in the security settings.
- Git and Nginx installed on your instance.

## Steps to Set Up and Run the Application Locally:

1. **Connect to your AWS Ubuntu instance** using SSH:
    ```bash
    ssh -i <your-key-file>.pem ubuntu@<your-server-ip>
    ```

2. **Update and install dependencies**:
    - Check if Git and Docker are installed:
    ```bash
    sudo apt update
    sudo apt install git -y
    ```

3. **Clone the repository for the web application**:
    ```bash
    git clone https://github.com/Sachin19191/simple-static-website-nginx.git
    cd simple-static-website-nginx
    ```

4. **Install Nginx web server**:
    ```bash
    sudo apt install nginx -y
    ```

5. **Configure Nginx**:
    - Make sure the default configuration points to the correct root directory:
    ```bash
    sudo vim /etc/nginx/sites-available/default
    ```
    Ensure it contains:
    ```nginx
    root /usr/share/nginx/html;
    ```

6. **Copy the website files to Nginx's document root**:
    ```bash
    sudo cp -r ~/simple-static-website-nginx/* /usr/share/nginx/html/
    ```

7. **Restart Nginx** to apply the changes:
    ```bash
    sudo systemctl restart nginx
    ```

8. **Test your application**:
    - Open your browser and visit your server's public IP:
    ```
    http://<your-server-ip>
    ```
### Live Testing
[3.6.160.37:80](http://3.6.160.37)
