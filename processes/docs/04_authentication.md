# Authentication

This section describes the most important aspects of authentication and authorization for an PnC EcoSystem. All Endpoints shall be secured and can only be reached after a successful authentication. 

To establish secure connections via HTTPS, Transport Layer Security via TLS 1.3 is recommended.

## Oauth2

It is recommended in using [OAuth2](https://tools.ietf.org/html/rfc6749) as authentication method. You will need to issue a [JSON Web Token (JWT)](https://tools.ietf.org/html/rfc7519) that can be obtained by different ways as described in the following sections. The token may contain information about what you are allowed to do, e.g. role (CPO, eMSP, OEM, CPS), what APIs you are allowed to use and which EMAIDs or PCIDs you are allowed to check.

The issued token will contain all necessary information to access the system (you can check this online on your own e.g. [jwt.io](https://jwt.io/)). 

## Roles&Rights

Depending on the role and the company the access rights are distinct. 

### OEM
Depending on the WMI in the PCID (first 3 characters), the OEM has read/write access to its data. Please always inform the ecosystem operator of the needed WMIs actively. If the correct data are not configured, the Plug&Charge Ecosystem will deny the access to perform the action.

### eMSP
Depending on the EMAID (first 5 characters - CountryCode + ProviderID), the eMSP has read/write access to its data. Please always inform the ecosystem operator of the needed Country Codes and ProviderIDs activity. If the correct data are not configured, the Plug&Charge Ecosystem will deny the access to perform the action.

### CPO
Depending on the EVSEID (first 5 characters - CountryCode + OperatorID), the CPO has read/write access to its data. Please always inform the ecosystem operator of the needed Country Codes and OperatorID activity. If the correct data are not configured, the Plug&Charge Ecosystem will deny the access to perform the action.


| Service | Access rights                                            | Method                                            | Access Rights | OEM       | CPO       | eMSP with own PKI | eMSP without own PKI | CPS       |
|---------|----------------------------------------------------------|---------------------------------------------------|---------------|-----------|-----------|-------------------|----------------------|-----------|
| RCP     | OEM, CPO, eMSP                                           | GetRootCertificate                                | Read          | Access    | Access    | Access            | Access               | Access    |
| RCP     | OEM, CPO, eMSP                                           | GetRootCertificates                               | Read          | Access    | Access    | Access            | Access               | Access    |
| RCP     | Admin                                                    | DeleteRootCertificate                             | write         | No Access | No Access | No Access         | No Access            | No Access |
| RCP     | Admin                                                    | PutRootCertificate                                | write         | No Access | No Access | No Access         | No Access            | No Access |
| PCP     | OEM (Only those with the corresponding WMI)              | AddProvisioningCertificate                        | Write         | Access    | No Access | No Access         | No Access            | No Access |
| PCP     | OEM (Only those with the corresponding WMI)              | DeleteProvisioningCertificate                     | Delete        | Access    | No Access | No Access         | No Access            | No Access |
| PCP     | OEM,eMSP                                                 | GetProvisioningCertificate                        | Read          | Access    | No Access | Access            | Access               | Access    |
| PCP     | OEM,eMSP                                                 | lookupVehicle                                     | Read          | Access    | No Access | Access            | Access               | Access    |
| CPS     | OEM,eMSP,CPO,CPS                                         | GetCpsCertificates                                | Read          | Access    | Access    | Access            | Access               | Access    |
| CPS     | eMSP with own PKI (external PKI) (only their own EMAIDS) | SignContractData                                  | Write         | No Access | No Access | Access            | No Access            | No Access |
| CPS     | eMSP without own PKI (V2G PKI) (only their own EMAIDS)   | GenerateAndSignContractData                       | Write         | No Access | No Access | No Access         | Access               | No Access |
| CCP     | CPO                                                      | GetSignedContractDataByCertificateInstallationReq | Read          | No Access | Access    | No Access         | No Access            | No Access |
| CCP     | eMSP                                                     | DeleteSignedContractDataByEmaid                   | Delete        | No Access | No Access | Access            | Access               | No Access |
| CCP     | eMSP                                                     | GetContractDataByEmaid                            | Read          | No Access | No Access | Access            | Access               | No Access |
| CCP     | OEM                                                      | GetContractDataByPcid                             | Read          | Access    | No Access | No Access         | No Access            | No Access |
| CCP     | OEM                                                      | GetSignedContractDataByEmaidAndPcid               | Read          | Access    | No Access | No Access         | No Access            | No Access |
| CCP     | eMSP,CPS                                                 | AddSignedContractData                             | Write         | POST      | No Access | Access            | Access               | Access    |
| CCP     | OEM                                                      | SetSignedContractDataAsDefault                    | Read          | Access    | No Access | No Access         | No Access            | No Access |
| PKI     | OEM                                                      | simpleEnroll - OEM                                | Read & Write  | Access    | No Access | No Access         | No Access            | No Access |
| PKI     | OEM                                                      | caCerts - OEM                                     | Read          | Access    | No Access | No Access         | No Access            | No Access |
| PKI     | CPO                                                      | simpleEnroll - CPO                                | Read & Write  | No Access | Access    | No Access         | No Access            | No Access |
| PKI     | CPO                                                      | caCerts - CPO                                     | Read          | No Access | Access    | No Access         | No Access            | No Access |
| PKI     | eMSP                                                     | simpleEnroll - eMSP                               | Read & Write  | No Access | No Access | No Access         | Access               | No Access |
| PKI     | eMSP                                                     | caCerts - eMSP                                    | Read          | No Access | No Access | No Access         | Access               | No Access |
| PKI     | CPS                                                      | simpleEnroll - CPS                                | Read & Write  | No Access | No Access | No Access         | Access               | Access    |
| PKI     | CPS                                                      | caCerts - CPS                                     | Read          | No Access | No Access | No Access         | Access               | Access    |
| PKI     | OEM, CPO, eMSP                                           | revokeCert                                        | write         | Access    | Access    | No Access         | Access               | No Access |
| WEBHOOK | OEM, CPO, eMSP, CPS                                      | Get all endpoints                                 | Read          | Access    | Access    | Access            | Access               | Access    |
| WEBHOOK | OEM, CPO, eMSP, CPS                                      | GetEndpointById                                   | Read          | Access    | Access    | Access            | Access               | Access    |
| WEBHOOK | OEM, CPO, eMSP, CPS                                      | PostEndpoint                                      | Write         | Access    | Access    | Access            | Access               | Access    |
| WEBHOOK | OEM, CPO, eMSP, CPS                                      | UpdateEndpointById                                | Write         | Access    | Access    | Access            | Access               | Access    |
| WEBHOOK | OEM, CPO, eMSP, CPS                                      | DeleteEndpointById                                | Write         | Access    | Access    | Access            | Access               | Access    |
