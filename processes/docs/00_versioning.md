# Versioning

## Interface version

Version number syntax: `M.m.d`

* **M**ajor version: Incremented when API changes are not compatible with the former version.
* **m**inor version: Incremented when new functionality is added or compatible changes are made.
* **d**ocumentation: Incremented when the documentation has changed without functional impact.

The individual API definition files have separate version numbers. This allows to update only one service while the others remain unchanged. For compatibility reasons the major versions need to be the same over all services. For this reason the interface description documents are geeting released by interface major version and date. E.g. `1-2020-07-31`.


## URI structure

The unified URI structure is as follows:
```
https://{domain}/opnc/{version}/{service}/{object}
```
 * `domain`: Domain name of the plug&Charge actor with a server exposing OPNC services. May be organized into subdomains according to the region (us, eu,etc..) and the nature (staging, production, etc..) of the actor's platform  
 * `version`: Version tag of the API, e.g. _1.1.0_ or _1.2.3_.
 * `service`: ID of the ecosystems microservice to adress, e.g. _root_ for the RCP. See API definition.
 * `object`: Name of the object to modify, e.g. _rootCerts_. See API definition.

<!-- theme: warning -->

>  API consumers should be able to configure the parameters _region_, _stage_ and _domain_ per deployment.
