# Certificate Provisioning Service

The CPS provides interfaces for generating and signing contract data of eMSPs. eMSPs can provide contract data to the CPS for signage directly or send contract information to generate contract data via the Mobility Operator CA. The signed contract data are either returned to the eMSP and/or stored in the CCP.


## API

The Certificate Provisioning Service can receive and sign contract data through a REST API, using one of the multiple endpoints. The signed data can be optionally stored into Contract Certificate Pool (this is usually the case).

![CPS interfaces](../../assets/images/interfaces_cps.png)

All CPS API documenatation can be found at [cps.v1.json](./../../../specification/apis/cps/cps.api.v1.json).

