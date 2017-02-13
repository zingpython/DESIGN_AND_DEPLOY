
# Deploy site with git

Connect to server
ssh root@ip
Install Apache2 on your server
sudo apt-get update
sudo apt-get install apache2
Install git on your server
sudo apt-get install git
Create the Directory Structure
sudo mkdir -p /var/www/your_folder_name/public_html
Grant Permissions
sudo chown -R $USER:$USER /var/www/your_folder_name/public_html
sudo chmod -R 755 /var/www
Get into your directory
cd /var/www/your_folder_name/public_html
Clone your project from your GitHub repo
git clone https://github.com/your_name_on_github/your_project_repo.git
Configure 000-default.conf file
sudo nano /etc/apache2/sites-available/000-default.conf
Add your path "/var/www/your_folder_name/public_html/your_project_repo" to index.html file to DocumentRoot
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/your_folder_name/public_html/your_project_repo
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
Restart Apache2 to make these changes take effect
service apache2 restart
Go to browser use your ip address


```python

```
