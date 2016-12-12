# Documentation Home

!!! progress
    A dump of all things Drupal related

## D8 Setup

Get latest drush

    apt-get install git drush -y    # Get latest drush

Download drupal 8

    cd /var/www/drupal
    drush dl drupal-8

Move all Drupal files to "/home/htdocs/drupal":

    mv drupal-*/* .
    rm -rf drupal-*/

Go to the directory 'sites/default' and copy the two configuration files 

    'settings.php' and 'services.yml':
    cd sites/default
    cp default.settings.php settings.php
    cp default.services.yml services.yml

Then create a new directory 'files' and change the permission of all files and folders in 'sites/default' directory:

    mkdir files/
    chmod a+w *

Go to the '/home/htdocs/drupal' directory and change the owner of the drupal directory to the user and group 'www-data' or whatever user:group you like:

    cd /var/www/
    chown -R www-data:www-data drupal/

Run update.php if /admin pages are inaccessible

    */update.php

Set up Git

    git init
    cp example.gitignore .gitignore   # Add .gitignore
    git add . && git commit -m "Init project" && git push origin/master   # Commit and push up


## MySQL Set up

    mysql -u root -p
    create database databasename;
    create user drupaluser@localhost identified by 'drupaluser@';
    grant all privileges on drupaldb.* to drupaluser@localhost identified by 'drupaluser@';
    flush privileges;
    exit

## D8 Project Structure

    /project_root
    /project_root/config   # Not web accessible
    /project_root/docroot  # Drupal source
    /project_root/test

## Configuration Management

By default, the config folder is located inside 'sites/default/files/config...'. Config data that contains information about the site should not be placed inside a web accessile location.

To improve this security issue we need to move it outside of the root and add a .htaccess file which ignores the existence of this directory altogether.

Config location
    
    Move out of root^1 (cd ../)
    mkdir config
    cd config
    mkdir sync

Inside settings.php

    $config_directories['sync'] = '../config/sync'  # settings.php

## Useful Drush Commands with CM

Export

    drush cex --add   # For granular diff of export changes
