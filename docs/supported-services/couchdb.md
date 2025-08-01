[comment]: # (Do not edit this file as it is autogenerated. Go to docs/individual-docs if you want to make edits.)


[comment]: # (Please add your documentation on top of this line)

## Options

### services\.couchdb\.enable



Whether to enable CouchDB process\.



*Type:*
boolean



*Default:*
` false `



*Example:*
` true `



### services\.couchdb\.package



Which version of CouchDB to use



*Type:*
package



*Default:*
` pkgs.couchdb3 `



### services\.couchdb\.baseDir

The directory where CouchDB will store its data\.



*Type:*
string *(read only)*



*Default:*
` config.env.DEVENV_STATE + "/couchdb" `



### services\.couchdb\.settings



CouchDB configuration\.
to know more about all settings, look at:
\<link
xlink:href=“https://docs\.couchdb\.org/en/stable/config/couchdb\.html”
/>



*Type:*
attribute set of section of an INI file (attrs of INI atom (null, bool, int, float or string))



*Default:*
` { } `



*Example:*

```
{
  couchdb = {
    database_dir = baseDir;
    single_node = true;
    view_index_dir = baseDir;
    uri_file = "${config.services.couchdb.baseDir}/couchdb.uri";
  };
  admins = {
    "admin_username" = "pass";
  };
  chttpd = {
    bind_address = "127.0.0.1";
    port = 5984;
  };
}

```



### services\.couchdb\.settings\.chttpd\.bind_address



Defines the IP address by which CouchDB will be accessible\.



*Type:*
string



*Default:*
` "127.0.0.1" `



### services\.couchdb\.settings\.chttpd\.port



Defined the port number to listen\.



*Type:*
16 bit unsigned integer; between 0 and 65535 (both inclusive)



*Default:*
` 5984 `



### services\.couchdb\.settings\.couchdb\.database_dir



Specifies location of CouchDB database files (\*\.couch named)\. This
location should be writable and readable for the user the CouchDB
service runs as (couchdb by default)\.



*Type:*
absolute path



*Default:*
` config.env.DEVENV_STATE + "/couchdb" `



### services\.couchdb\.settings\.couchdb\.single_node



When this configuration setting is set to true, automatically create
the system databases on startup\. Must be set false for a clustered
CouchDB installation\.



*Type:*
boolean



*Default:*
` true `



### services\.couchdb\.settings\.couchdb\.uri_file



This file contains the full URI that can be used to access this
instance of CouchDB\. It is used to help discover the port CouchDB is
running on (if it was set to 0 (e\.g\. automatically assigned any free
one)\. This file should be writable and readable for the user that
runs the CouchDB service (couchdb by default)\.



*Type:*
absolute path



*Default:*
` config.env.DEVENV_STATE + "/couchdb"/couchdb.uri `



### services\.couchdb\.settings\.couchdb\.view_index_dir



Specifies location of CouchDB view index files\. This location should
be writable and readable for the user that runs the CouchDB service
(couchdb by default)\.



*Type:*
absolute path



*Default:*
` config.env.DEVENV_STATE + "/couchdb" `
