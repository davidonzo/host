# apiosintDS MISP modules

MISP expansion/hover module implementing [apiosintDS API library](https://github.com/davidonzo/apiosintDS) to query [OSINT.digitalside.it](https://osint.digitalside.it) service against souspicious threat indicators.

## Supported input attributes are:
* domain
* domain|ip
* hostname
* ip-dst
* ip-src
* ip-dst|port
* ip-src|port
* url
* md5
* sha1
* sha256
* filename|md5
* filename|sha1
* filename|sha256"

## Module options
* **import_related_hashes** *(yes|no)*

...If *yes* for attributes differents from hashes, the module will attach a set of hashes (md5, sha1 and sha256) for any related URLs retrived.

* **cache** *(yes|no)* *highly recommended*

⋅⋅⋅OSINT.digitalside.it service are updated every 4 hours. Quering the service with no cache results in a useless bandwith compsumation for the MISP instance and the apiosintDS services too.

* **cache_directory** *(str,path)* *highly recommended*

⋅⋅⋅Option required if the cache system in enabled. Remember, the module won't create a directory for you. Unless the pure library version, there's no default cache directory.

### Reccomanded options
![Module Options](https://raw.githubusercontent.com/davidonzo/host/master/module_optionsGOOD.png)

## Examples

### 
