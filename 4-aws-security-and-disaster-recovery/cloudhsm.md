# CloudHSM

- KMS => AWS manages the software encryption
- CloudHSM => AWS provisions encryption hardware, we have to use our own client to do the encryption
- HSM device is tamper resistant, FIPS 140-2 Level 3 compliant
- HSM cluster can be set across multiple AZ (HA)
- Supports both symmetric and asymmetric encryption (SSL/TLS keys)
- No free tier available for CloudHSM
- Redshift supports CloudHSM for database encryption and key management
- CloudHSM is also a good idea for SSE-C encryption for S3
- **AWS can not recover credentials keys in case they are lost!**

- You can configure your own CloudHSM cluster and authorize AWS KMS to use it as a dedicated key store for your keys rather than the default AWS KMS key store. When you create keys in AWS KMS you can choose to generate the key material in your CloudHSM cluster. CMKs that are generated in your custom key store never leave the HSMs in the CloudHSM cluster in plaintext and all AWS KMS operations that use those keys are only performed in your HSMs.
