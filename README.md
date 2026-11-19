# Inji-Config
This Repository contains configurations for Inji Stack, These are the split up of the properties used by different modules in the inji stack

### Inji Mobile
- [inji-default.properties](inji-default.properties) - Default Configuration for Inji Mobile App is mentioned here

### Inji Web
- [credential-template.html](credential-template.html) - PDF Template for Inji Web Credential Download is mentioned here

### Mimoto
- `mosip.inji.mdocTemplateBaseUrl` and `mosip.inji.mdocTemplates` in [inji-default.properties](inji-default.properties) - Where the mdoc card SVGs are hosted (this repository's `gh-pages` branch, `mdoc`) and which SVG each mdoc docType uses. Inji Wallet reads them through Mimoto's `allProperties`.
- [mimoto-default.properties](mimoto-default.properties) - Default Configuration for Mimoto App is mentioned here
- [mimoto-issuers-config.json](mimoto-issuers-config.json) - Configuration of All Supported Credential Issuers is mentioned here
- [mimoto-trusted-verifiers.json](mimoto-trusted-verifiers.json) - Configuration of All Trusted Credential Verifiers is mentioned here
  - The **response_uri** is used to receive vp_token for cross device flow support.

When credential issuers are not hosting their wellknown, mimoto will host the fallback wellknown from config server  

- [mimoto-mock-identity-wellknown.json](mimoto-mock-identity-wellknown.json) - Fallback wellknown Configuration for Mock Identity usecase
- [mimoto-mosipid-identity-wellknown.json](mimoto-mosipid-identity-wellknown.json) - Fallback wellknown Configuration for Mosipid Identity usecase
- [mimoto-sunbird-insurance-wellknown.json](mimoto-sunbird-insurance-wellknown.json) - Fallback wellknown Configuration for Sunbird Insurance usecase

### DataShare

- [data-share-default.properties](data-share-default.properties) - Default Configuration for Datashare is mentioned here
- [data-share-standalone.properties](data-share-standalone.properties) - Standalone Configuration for Datashare is mentioned here, which lets you use datashare service without PMS 


### Inji Certify

[certify-default.properties](certify-default.properties) - This file holds only the certify's core properties and will have the last section for properties that is suppose to be overridden by the plugin-usecase properties

Right now we will be maintaining the below 3 plugin-usecase property files, one for each plugin that is readily available for certify integration. 
And each plugin is associated with an example usecase.

1. [certify-mock-identity.properties](certify-mock-identity.properties) - Uses mock plugin and showcases identity usecase
2. [certify-mosipid-identity.properties](certify-mosipid-identity.properties) - Uses mosip identity plugin and showcases identity usecase
3. [certify-sunbird-insurance.properties](certify-sunbird-insurance.properties) - Uses sunbird RC plugin and showcases insurance usecase
4. [certify-postgres-landregistry.properties](certify-postgres-landregistry.properties) - Uses posgtres dataprovider plugin and showcases land registry and land statement usecases


Each plugin-usecase property file will contain the below 3 sections
1. Properties to enable the plugin
2. Properties specific to plugins
3. Properties that is available in the certify-default.properties but needs to be overriden specific to the usecase
