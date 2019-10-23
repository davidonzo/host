# apiosintDS MISP modules

MISP expansion/hover module implementing [apiosintDS API library](https://github.com/davidonzo/apiosintDS) to query [OSINT.digitalside.it](https://osint.digitalside.it) service against souspicious threat indicators.

**IMPORTANT**. This module is for people and organizations don't want to subscribe the [OSINT.digitalside.it MISP Feed](https://osint.digitalside.it/Threat-Intel/digitalside-misp-feed/), but want to interact with shared data as a simple lookup service.

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
	* If *yes* for attributes differents from hashes, the module will attach a set of hashes (md5, sha1 and sha256) for any related URLs retrived.

* **cache** *(yes|no)* *highly recommended*
	* OSINT.digitalside.it service are updated every 4 hours. Quering the service with no cache results in a useless bandwith compsumation for the MISP instance and the apiosintDS services too.

* **cache_directory** *(str,path)* *highly recommended*
	* Option required if the cache system in enabled. Remember, the module won't create a directory for you. Unless the pure library version, there's no default cache directory.

### Reccomanded options
![Module Options](https://raw.githubusercontent.com/davidonzo/host/master/examples_apiosintDS_MISP_Module/module_optionsGOOD.png)

## Examples

#### Usage: hover | Entity: IPv4 | import_related_hashes = no

Three urls returned as related items.

![usage_example_1](https://raw.githubusercontent.com/davidonzo/host/master/examples_apiosintDS_MISP_Module/ip_.png)

#### Usage: hover | Entity: IPv4 | import_related_hashes = yes
![usage_example_2](https://raw.githubusercontent.com/davidonzo/host/master/examples_apiosintDS_MISP_Module/ip_.png)

#### Usage: expantion | Entity: IPv4 | import_related_hashes = yes!
[usage_example_3](https://raw.githubusercontent.com/davidonzo/host/master/examples_apiosintDS_MISP_Module/enrich_results.png)

### More info
* [Other examples available](https://github.com/davidonzo/host/tree/master/examples_apiosintDS_MISP_Module)
* [apiosintDS docs](https://apiosintds.readthedocs.io/en/latest/)
