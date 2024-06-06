#  Migrating wordpress site - local 2 host
## create empty database at live host

## modify wp-config.php for these
* define('DB_NAME'[DB_USER,DB_PASSWORD],'db_name'[...,...])

## import database to using phpmyadmin
# site url change
	wp_options
	
## uploading files to public_html which is root folder via FILEZILLA

# broken links
```
UPDATE wp_posts SET post_content = REPLACE(post_content, 'localhost/test/', 'www.yourlivesite.com/');
```
