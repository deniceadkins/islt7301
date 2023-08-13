# Installing Omeka

## 1. Open your VM

Go to Google Cloud SDK Shell. Enter the following to access your VM terminal window:
```
gcloud compute ssh --zone "zone-info" "name-info" --project "project-name"
```

##2. Install the Prerequisites

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


