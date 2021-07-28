# .htaccess-file-docs
Docs for Important code related to htaccess

# To Deny the Perticular Folder

```
Order Allow,Deny 
Deny from all 

<FilesMatch "\.(jpg|gif|png|php)$">
Order Deny,Allow
   Allow from all
</FilesMatch>

# Redirect Perticular Folder to 404.html page

```
# You can also deny access to a folder using RedirectMatch
Add the following line to htaccess
```
RedirectMatch 403 ^/folder/?$
```
This will return a 403 forbidden error for the folder ie : http://example.com/folder/ but it doest block access to files and folders inside that folder, if you want to block everything inside the folder then just change the regex pattern to ^/folder/.*$ .

Another option is mod-rewrite If url-rewrting-module is enabled you can use something like the following in root/.htaccss :
```
RewriteEngine on
RewriteRule ^folder/?$ - [F,L]
This will internally map a request for the folder to forbidden error page.
```

