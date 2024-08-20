## Self-Signed SSL Certificate

### Generate PEM
openssl genrsa -out smexnet_key.pem 4096

### Convert private Key to PKCS#8 format (so Java can read it)
openssl pkcs8 -topk8 -inform PEM -outform DER -in smexnet_key.pem -out smexnet_key.der -nocrypt

### Generate public key
openssl rsa -in smexnet_key.pem -pubout -outform DER -out smexnet_public_key.der
openssl rsa -in smexnet_key.pem -pubout -out smexnet_public.key

## Import into truststore

### Create CSR (Certificate Signing Request)
openssl req -new -out smexnet.csr -key smexnet_key.pem

### Generate Certificate
openssl x509 -req -days 2500 -in smexnet.csr -signkey smexnet_key.pem -out smexnet.crt

### Make it a P12 file
```sh
openssl pkcs12 -export -in smexnet.crt -inkey smexnet_key.pem -out smexnet.p12 -name smexnet-dev -CAfile ca.crt -caname root
```

```sh
openssl pkcs12 -export -in smexnet-ciam_eon_com.crt -inkey smexnet-ciam_eon_com.key -out smexnet-prod.p12 -name smexnet-prod -CAfile ca.crt -caname root
```

### Import into truststore

#### P12
```sh
keytool -importkeystore -deststorepass testTutGuut! -destkeypass Smexnet_2021 -destkeystore truststore.jks -srckeystore smexnet.p12 -srcstoretype PKCS12 -srcstorepass Smexnet_2021  -alias smexnet-dev
```

```sh
keytool -importkeystore -deststorepass testTutGuut! -destkeypass Smexnet_Prod_2021 -destkeystore truststore.jks -srckeystore smexnet-prod.p12 -srcstoretype PKCS12 -srcstorepass Smexnet_Prod_2021  -alias smexnet-prod
```

```sh
openssl pkcs12 -export -in spie.crt -inkey privateKey.key -out spie.p12 -name spie-dev -CAfile ca.crt -caname root

keytool -importkeystore -deststorepass testTutGuut! -destkeypass Spie_2021 -destkeystore truststore.jks -srckeystore spie.p12 -srcstoretype PKCS12 -srcstorepass Spie_2021  -alias spie-dev
```

#### PFX

```sh
keytool -importkeystore -deststorepass testTutGuut! -destkeypass Smexnet_Prod_2021 -destkeystore truststore.jks -srckeystore smexnet-prod.p12 -srcstoretype PKCS12 -srcstorepass Smexnet_Prod_2021  -alias smexnet-prod
```


## Convert CRT tp PFX

openssl pkcs12 -export -out gep_eon_com.pfx -inkey gep.eon.com.key -in gep_eon_com.crt

## Change PFX Password

```sh
openssl pkcs12 -in old-cert.pfx -out temp.pem -nodes -passin pass:$(old_password)
openssl pkcs12 -export -legacy -out new-cert.pfx -in temp.pem -passout pass:$(new_password)
```

## Mac Specifics

```sh
openssl pkcs12 -export -legacy -out Certificate.p12 -in certificate.pem -inkey key.pem
```
