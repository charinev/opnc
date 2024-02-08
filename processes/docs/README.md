# Plug and Charge Ecosystems

**Interface description Version DOC_DATE**

## Introduction

Plug&Charge (PnC) Ecosystems enable EV OEMs, Mobility Operators and Charge Point Operators to use the ISO 15118 standard for the Plug&Charge functionalities.
PnC-Ecosystems manage certificates from V2G-, OEM- and eMSP-PKIs. It manages the publication in pools  and offers signing services for trusted data. V2G Root CAs can be a trust anchor for all participants of ISO 15118. The V2G-, OEM- and eMSP-CAs are published in the Root Certificate Pools of a Plug&Charge Ecosystem. It is possible to operate also parts like just a RCP, PCP, CPS, CCP or PKI Signing Services

The interfaces of the OPCP are fully compatible with ISO 15118-2:2014 and the VDE application rule (“VDE Anwendungsregel”). It aims to also cover all of the use cases described in the CharIN "PKI Interoperability Guide". It is also fully interoperable for all relaying parties. The specific implementation/description is based on international best practices, security of communication and protection of data.

The Ecosystem components can be divided into three main categories:
 * The Plug&Charge Certificate pools and Certificate Provisioning Service
 * The Plug&Charge PKI Services
 * The Plug&Charge Callback Service

Plug&Charge PKI Services are managed services of V2G Root Operators, to provide all necessary certificates for EV OEMs, Mobility Operators, Certificate Provisioning Services and Charge Point Operators.

The Certificate pools and the Certificate Provisioning Service are for publishing certificates and contract certificates between all ISO 15118 involved actors.

## Related documents

 * [DIN EN ISO 15118-2:2014: Road vehicles - Vehicle-to-Grid Communication Interface - Part 2: Network and application protocol requirements (ISO 15118-2:2014)](https://www.din.de/en/getting-involved/standards-committees/naautomobil/publications/wdc-beuth:din21:250999944)
 * [VDE Anwendungsregel: VDE-AR-E 2802-100-1, Anwendungsregel: 2017-10, „Zertifikats-Handhabung für E-Fahrzeuge, Ladeinfrastruktur und Backend-Systeme im Rahmen der Nutzung von ISO/IEC 15118“](https://www.vde-verlag.de/normen/0800432/vde-ar-e-2802-100-1-anwendungsregel-2017-10.html)
 * [Whitepaper of Charging Interface Initiative e.V. "Interoperability Guide – Public Key Infrastructure (PKI) use casesVersion 1.0"](https://www.charin.global/media/pages/technology/knowledge-base/f50187baf9-1683808407/charin_interoperability_guide-pki_use_cases_v1.0.pdf)

## Further reading

 * [Abbreviations](./01_abbreviations.md)
 * [Business Processes](./02_PnC_business-processes.md)
 * [Publications and Repository_Responsibilities](./03_publications-and-repository-responsibilities.md)
 * [Authentication](./04_authentication.md)
 * [Handling of IDs](./05_handling-of-ids.md)

## System-Components

This section describes the components of the Plug&Charge Ecosystem and their purpose of use.

* [Root Certificate Pool (RCP)](./components/01_root-certificate-pool.md) – stores and distributes root certificates of all participating PKIs.
* [Provisioning Certificate Pool (PCP)](./components/02_provisioning-certificate-pool.md) – stores OEM provisiong certificates and makes them available to the eMSPs.
* [Certificate Provisioning Service (CPS)](./components/03_certificate-provisioning-service.md) – provisions contract certificates to prepare them to get installed in the EV.
* [Contract Certificate Pool (CCP)](./components/04_contract-certificate-pool.md) – stores provisioned contract certificates waiting to get installed.
* [Plug&Charge PKI Services](./components/05_v2g-pki-services.md)
* [Plug&Charge Webhook Service](./components/06_webhook-service.md)
