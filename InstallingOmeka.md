# Installing Omeka

## 1. Open your VM

Go to Google Cloud SDK Shell. Enter the following to access your VM terminal window:
```
gcloud compute ssh --zone "zone-info" "name-info" --project "project-name"
```

## 2. Install the Prerequisites

- Install ImageMagick. This is a suite of utilities to work with photo files. It's used by Omeka to create thumbnail images of any photo uploaded to the digital library. See Imagemagick for more information.

```
sudo apt install imagemagick
```

- Enable Apache mod_rewrite. This is an Apache module used to rewrite URLs. Omeka uses this to create appropriate URLs for items and collections in its digital libraries.

```
sudo a2enmod rewrite
```

- Restart Apache after enabling rewrite:

```
sudo systemctl restart apache2
```

## 3. Go to https://omeka.org/classic/download.  

- Click on the *Installation/upgrade instructions* for a general overview of the intallation process.
- Click on *All versions* to find downloaadable packages for Omeka.
-- The *All versions* page will take you to their GitHub page. From here, right-click on v.3.1.1 Source coe (tar.gz) and copy the file name.
-- In your VM, enter the following:
  ```
  cd /var/www/html/
  sudo wget https://github.com/omeka/Omeka/archive/refs/tags/v3.1.1.tar.gz
  ```

## 4. Create an Omeka database and login on your VM
Enter MySQL as a superuser. 
```
sudo su
mysql -u root
```

In MySQL, enter the following:
```
create user 'omeka'@'localhost' identified by 'XXXXXXXX';
create database omeka;
grant all privileges on omeka.* to 'omeka'@'localhost';
show databases;
\q
exit
```



