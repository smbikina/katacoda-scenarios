After creating the above Certificate, we can check whether it has been obtained successfully using kubectl describe:


    $ kubectl describe certificate example-com
    Events:
    Type    Reason          Age      From          Message
    ----    ------          ----     ----          -------
    Normal  CreateOrder     57m      cert-manager  Created new ACME order, attempting validation...
    Normal  DomainVerified  55m      cert-manager  Domain "example.com" verified with "http-01" validation
    Normal  DomainVerified  55m      cert-manager  Domain "www.example.com" verified with "http-01" validation
    Normal  IssueCert       55m      cert-manager  Issuing certificate...
    Normal  CertObtained    55m      cert-manager  Obtained certificate from ACME server
    Normal  CertIssued      55m      cert-manager  Certificate issued successfully