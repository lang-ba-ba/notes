- pacman -Sy openssl
- openssl req -newkey rsa:4096 -x509 -sha512 -days 365 -nodes -out certificate.pem -keyout privatekey.pem

- openssl list --digest-commands
- get two pem file
- openssl x509 -noout -in certificate.pem -text
- openssl x509 -pubkey -noout -in certificate.pem |tee pubickey

