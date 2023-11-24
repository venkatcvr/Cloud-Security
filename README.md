# Cloud-Security

1.generate a private key (private.pem) encrypted with AES-128 and secured with the passphrase "CloudSecurityFall2023".]

command: openssl genrsa -aes128 -passout pass:CloudSecurityFall2023 -out private.pem 4096

2.derive the corresponding public key (public.pem) from the private key.

command: openssl rsa -pubout -in private.pem -out public.pem


3. Create a signature of the file using the private key:

generates a SHA256-based digital signature (signature.sha256) for the file hadoop-3.3.6-src.tar.gz using the private key (private.pem).]

command: openssl dgst -sha256 -sign private.pem -out signature.sha256 hadoop-3.3.6-src.tar.gz
