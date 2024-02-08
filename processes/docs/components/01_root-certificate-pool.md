# Root Certificate Pool

The Root Certificate Pool is used as a trusted source of root certificates from various ecosystem certificate authorities (V2G, OEM, eMSP) by the participants (OEM, CPO, eMSP, CPS). 
The stored root certificates are checked before addition to the pool, and regularly with automated processes. Expired or revoked certificates will be invalidated. The storage of root certificates is executed manually by RCP Authority administrators.

Other systems of a PnC Ecosystem use this pool as the mutual trust store.


## API

The root certificate pool offers a REST API to request registered root certificates.

![RCP interfaces](../../assets/images/interfaces_rcp.png)

The documenatation can be found at [rcp.v1.json](../../specification/apis/rcp/rcp.api.v1.json).

## Processes

The root certificate pool is involved in multiple processes across the ecosystem. The Direct Processes are described bellow:

### 1. Deliver Root Certificates

The delivery of root certificates of the OEM, V2G, eMSP, and possibly PE-CAs to the Root Certificate Pool is an organizational process, which can be proceeded by different methods, like signed email, SFTP, OFTP2 or similar methodologies. After approval the new root certificates are added to the root certificate pool by the RCP Operator. Therefore the PUT and DELETE interfaces of the pool are restricted for authorized administrative use only.


### 2. Request Root Certificates

All participants of the PKI may request root certificates published in the RCP. The connected systems may request the list of certificates on regular basis.


### 3. Data Cleansing

The Root Certificate Pool watches all contained root certificates on regular basis. 

## Additional notes

If a Root CA revokes a root certificate, the Plug&Charge Ecosystem operator should not immediately revoke all related certificates, including the contract certificates. This can cause deletion of all related certificates and the charging service to stop working. For this case, an organizational process _must_ be defined between the Operator and the respective customers to ensure a customer friendly transition to another Root CA.

Until the delivery of a new root certificate, it will not be possible to send any new leaf certificate. Because the validation of the trust chain of the certificate cannot be proceeded. For more information about the validation process please see chapter interface description.
