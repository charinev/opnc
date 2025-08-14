# OPNC
CharIN Open Plug&amp;Charge Protocol (OPNC)

Here you can find all documents and information about the open-source "Open Plug&amp;Charge Protocol (OPNC)" (OPNC).

As it is important to achieve the best possible interoperability in the eMobility market it is crucial to use the same protocols in the Plug&Charge use case.
The OPNC Project is an open-source project. The goal of the project is to specify an open-source protocol for enabling trusted and secure communication, including Plug and Charge authentication, in the electric vehicle charging ecosystem, covering the related ISO 15118 functions.

## OPNC enables and reflects following use cases:
  - independent Service Operation
    - [RCP Service]
    - [PCP Service]
    - [CPS Service]
    - [CCP Service]
    - [PKI Authorities]
  - [Authentication Method]
  - Multiple Contracts (EMAIDs) for one Vehicle (PCID)
  - [Standardized Event Service]
  - Interoperability between Ecosystems, V2G Root Operators etc
    - Multi Root -> CertificateSigningCertificate ability
    - Pool collaboration
  - ISO15118-20 readiness

![CharIN-Logo_Office_RGB](https://github.com/charinev/opnc/assets/83767351/1688cfe1-97de-46c7-9b97-65bcec242193)

## Disclaimer
This protocol description does not yet cover extended use cases nor defines every OSI-layer. This protocol is to be seen as addition to available industry standards and best practices.
The protocol is developed by the community and everyone is free and invited to contribute.

## API Documentation
An automatic routine was developed that will generate readable API documentation from the JSON files. This documentation is available in https://charinev.github.io/opnc/ and will be updated automatically if there are any changes in the code.

## Governance / EU PKI EcoSystem

The protocol OPNC will be used in the EU PKI EcoSystem to enable communication among market parties and various components, including the CA-Roots, the Pools, and PKI Services.

The EU PKI EcoSystem was developed by the subgroup **Governance & Standards** of the **Sustainable Transport Forum (STF)** under **EU DG Move**. The result of this effort produced two important documents:

**STF Subgroup Governance & Standards - Activity 2**
   
   [Development of a Governance and Architecture Framework for the implementation and operation of a Public Key Infrastructure ecosystem in the EU.](https://op.europa.eu/en/publication-detail/-/publication/b7910659-276c-11ee-839d-01aa75ed71a1/language-en)

**Support Study on the development of a governance framework for the EU Public Key Infrastructure (PKI)**
   
   [Final Report](https://op.europa.eu/en/publication-detail/-/publication/0d84b5b6-6f03-11ee-9220-01aa75ed71a1/language-en)

These two documents serve as the foundation for the delegated and implementation act for the **AFIR (Alternative Fuels Infrastructure Regulation)** and provide valuable input for the newly established **STF Subgroup “EU PKI Management.”**

Furthermore, the EU PKI EcoSystem will also be utilized by the **SAE EVPKI Consortium** for the establishment of the PKI EcoSystem in North America.


## License

Shield: [![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg
