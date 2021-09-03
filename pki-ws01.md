
```
echo abcdefghijklmnopqrstuvwxyz > message.txt
shasum -a 1 message.txt

openssl genrsa -out choompol.pem 512
openssl rsa -in choompol.pem -pubout > choompol.pub

openssl rsautl -encrypt -inkey choompol.pub -pubin -in message.txt > message.enc
openssl rsautl -decrypt -inkey choompol.pem -in message.enc

openssl dgst -sha1 -sign choompol.pem -out sha1.sign message.txt
openssl dgst -sha1 -verify choompol.pub -signature sha1.sign message.txt

ssh-keygen -i -m PKCS8 -f choompol.pem

https://medium.com/@bn121rajesh/rsa-sign-and-verify-using-openssl-behind-the-scene-bf3cac0aade2
https://opensource.com/article/21/4/encryption-decryption-openssl
https://security.stackexchange.com/questions/32768/converting-keys-between-openssl-and-openssh

```
