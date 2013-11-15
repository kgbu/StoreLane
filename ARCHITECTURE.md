Architecture
============

* FRONT END : as a folder/disk on end-users device (sometimes read access may be pended)
* BACK END : non-uniform storage layer (user disk/ S3 / Glacier etc.)
    * notify on change in filesystem
        * inotify on Linux
        * Active Folder on OSX
        * FindFirstChangeNotification on Windows OS
    * cook data process
        * meta-data tagging(path, userid, timestamp, size etc.)
        * encryption
        * signing
        * content addressing
    * cache layer (optional) : for performance and network trouble
    * immediate storage layer
    * archival storage layer (access with dalay)


FIXME
=====

* how to achieve pending state (in Glacier like status) 
    * explicit move to archive folder?
    * HTTP-like verbes and status code; "302" code against GET command?

