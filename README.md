# Magento-2-Permissions
Magento-2-Permissions

The owner of the Magento file system: Must have full control (read/write/execute) of all files and directories. Must not be the web server user; it should be a different user.

The web server user must have write access to the following files and directories: var app/etc pub generated.

In addition, the web server’s group must own the Magento file system so that the Magento user (who is in the group) can share access to files with the web server user. (This includes files created by the Magento Admin or other web-based utilities.).

Set Magento Permissions : We recommend permissions for Magento as follows.

All directories have 770 permissions. 770 permissions give full control (that is, read/write/execute) to the owner and to the group and no permissions to anyone else.

All files have 660 permissions. 660 permissions mean the owner and the group can read and write but other users have no permissions.

You should set as bellow recommended Permissions.

cd <your Magento install dir>

For files 644 : find . -type f -exec chmod 644 {} \;

For Directory 755 : find . -type d -exec chmod 755 {} \;

For var folder 777 : find ./var -type d -exec chmod 777 {} \;

For pub/media folder 777 : find ./pub/media -type d -exec chmod 777 {} \;

For pub/static folder 777 : find ./pub/static -type d -exec chmod 777 {} \;

For app/etc folder 777 : chmod 777 ./app/etc

For app/etc .xml file 644 : chmod 644 ./app/etc/*.xml

chown -R :<web server group> .

chmod u+x bin/magento
