## Start apache in any directory from command line

Install with npm - which comes with node here: http://nodejs.org/
```
sudo npm install pache -g
```
Run it:
```
pache site-directory 2000
```

Thanks to friends on StackOverflow
http://stackoverflow.com/questions/13695391/start-an-apache-server-in-any-directory-from-command-line#15936279

Only tested on Mac so far, but you can find a Linux script on SO in the meantime


Block all caching: Add a .htaccess file at the root of your apache server and paste in this code
```
# Prevent all caching because of a caching bug in iOS6 - run in directory with pache (github.com/devinrhode2/pache)
# ------------------------------------------------------------------------------
# | Expires headers (for better cache control)                                 |
# ------------------------------------------------------------------------------

<IfModule mod_expires.c>

    ExpiresActive on
    ExpiresDefault                                      "access plus 0 seconds"

  # CSS
    ExpiresByType text/css                              "access plus 0 seconds"

  # Data interchange
    ExpiresByType application/json                      "access plus 0 seconds"
    ExpiresByType application/xml                       "access plus 0 seconds"
    ExpiresByType text/xml                              "access plus 0 seconds"

  # Favicon (cannot be renamed!)
    ExpiresByType image/x-icon                          "access plus 0 seconds"

  # HTML components (HTCs)
    ExpiresByType text/x-component                      "access plus 0 seconds"

  # HTML
    ExpiresByType text/html                             "access plus 0 seconds"

  # JavaScript
    ExpiresByType application/javascript                "access plus 0 seconds"

  # Manifest files
    ExpiresByType application/x-web-app-manifest+json   "access plus 0 seconds"
    ExpiresByType text/cache-manifest                   "access plus 0 seconds"

  # Media
    ExpiresByType audio/ogg                             "access plus 0 seconds"
    ExpiresByType image/gif                             "access plus 0 seconds"
    ExpiresByType image/jpeg                            "access plus 0 seconds"
    ExpiresByType image/png                             "access plus 0 seconds"
    ExpiresByType video/mp4                             "access plus 0 seconds"
    ExpiresByType video/ogg                             "access plus 0 seconds"
    ExpiresByType video/webm                            "access plus 0 seconds"

  # Web feeds
    ExpiresByType application/atom+xml                  "access plus 0 seconds"
    ExpiresByType application/rss+xml                   "access plus 0 seconds"

  # Web fonts
    ExpiresByType application/font-woff                 "access plus 0 seconds"
    ExpiresByType application/vnd.ms-fontobject         "access plus 0 seconds"
    ExpiresByType application/x-font-ttf                "access plus 0 seconds"
    ExpiresByType font/opentype                         "access plus 0 seconds"
    ExpiresByType image/svg+xml                         "access plus 0 seconds"

</IfModule>
```


[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/devinrhode2/pache/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

