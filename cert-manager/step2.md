The first stage of the ACME protocol is for the client to register with the ACME server. This phase includes generating an asymmetric key pair which is then associated with the email address specified in the Issuer. Make sure to change this email address to a valid one that you own. It is commonly used to send expiry notices when your certificates are coming up for renewal. The generated private key is stored in a Secret named letsencrypt-staging.

We must provide one or more Solvers for handling the ACME challenge. In this case we want to use HTTP validation so we specify an http01 Solver. We could optionally map different domains to use different Solver configurations.

Once we have created the above Issuer we can use it to obtain a certificate.


    apiVersion: cert-manager.io/v1
    kind: Certificate
    metadata:
    name: example-com
    namespace: default
    spec:
    secretName: example-com-tls
    issuerRef:
        name: letsencrypt-staging
    commonName: example.com
    dnsNames:
    - www.example.com