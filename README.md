# WordPress

## First Step 
`` Extract the Folder Brief8-E-commerce from Brief8-E-commerce.rar and put it inside your localhsot ``
## Second Step
`` Import the db into your phpMyAdmin ``

## The Used Plug-ins

>WooCommerce <br>
>RGPD (Cookies) <br>
>Dark Mode <br>
>Multi lang <br>

## Theme

>FrontStore


## For installing Multi sites

``
  Go to wp_config.php and put this define in it "define( 'WP_ALLOW_MULTISITE', true )" <br>
  then go to the wordpress project click at tools and choose install multi sites <br>
  after that step  a code will be generated copy it and past some of it inside htaccess in root wordpress <br>
  project and the other part past it in the wp_config.php file
  
  code for htaccess : ``
  
    RewriteEngine On
    
    RewriteRule .* - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]
    RewriteBase /your priject name/
    RewriteRule ^index\.php$ - [L] 
    # add a trailing slash to /wp-admin
    RewriteRule ^([_0-9a-zA-Z-]+/)?wp-admin$ $1wp-admin/ [R=301,L]
    RewriteCond %{REQUEST_FILENAME} -f [OR]
    RewriteCond %{REQUEST_FILENAME} -d
    RewriteRule ^ - [L]
    RewriteRule ^([_0-9a-zA-Z-]+/)?(wp-(content|admin|includes).*) $2 [L]
    RewriteRule ^([_0-9a-zA-Z-]+/)?(.*\.php)$ $2 [L]
    RewriteRule . index.php [L]
  ``
  
  code for wp_config.php : ``
    
    define('MULTISITE', true);
    define('SUBDOMAIN_INSTALL', false);
    define('DOMAIN_CURRENT_SITE', 'localhost');
    define('PATH_CURRENT_SITE', '/Brief8-E-commerce/');
    define('SITE_ID_CURRENT_SITE', 1);
    define('BLOG_ID_CURRENT_SITE', 1);
    
  ``
  
``
