PREREQUISITES
==============
- cURL Support in your PHP
- JSON SUpport in your PHP
- SSL Support in your Web Server

HOW TO INSTALL
==============
Step 1. Include oauth.php in php script which needs authentication.
-------------------------------------------------------------------
    <?php 
    require_once 'oauth.php';
    
    [YOUR CODE]
    ?>

Step 2. Create a new instance of oauth class.
---------------------------------------------
    <?php
    require_once 'oauth.php';
    $oauth = new oauth([CLIENT_ID], [CLIENT_SECRET], [CALLBACK_URL], [LOGIN_URL], [CACHE_DIR]);
    
    [YOUR CODE]
    ?>

- LOGIN_URL and CACHE_DIR are optional.
- access token, refresh token and instance url are saved under CACHE_DIR in case of using auth_with_password() method.

Step 3. Execute $oauth->auth_with_code() or $oauth->auth_with_password() depeding on your application.
------------------------------------------------------------------------------------------------------
If you apply standard web server authetication flow, use auth_with_code() method as follows.
This type of flow is the most common when you provide external web service that needs access to Force.com/Database.com
    <?php
    require_once 'oauth.php';
    $oauth = new oauth([CLIENT_ID], [CLIENT_SECRET], [CALLBACK_URL], [LOGIN_URL], [CACHE_DIR]);
    $oauth->auth_with_code();
    
    [YOUR CODE]
    ?>

If you apply username/password authetication flow, use auth_with_password() method as follows.
This type of flow is used in case you need users access to web contents without authentication while the contents still needs login to Force.com/Database.com.

    <?php
    require_once 'oauth.php';
    $oauth = new oauth([CLIENT_ID], [CLIENT_SECRET], [CALLBACK_URL], [LOGIN_URL], [CACHE_DIR]);
    $oauth->auth_with_password([USERNAME], [PASSWORD]);
    
    [YOUR CODE]
    ?>


That's it. Enjoy.
