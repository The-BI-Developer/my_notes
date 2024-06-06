#downgrading wordpress site
## deactivate plugins and themes via sftp
* wp-content/plugins --renamed--> wp-content/plugins_deactivated
* wp-content/themes/my_theme_deactivated //temp renaming to force rollback to twnetytwenty

note if no default theme: unzip to theme folder and activate it

## to delete in downloaded wordpress version
wp-config-sample.php #connection to db; will have to enter all the information into the db back
wp-content #media plugin themes

## update database after ftp
login to the site upgrade
rename back themes and plugins for reactivation
