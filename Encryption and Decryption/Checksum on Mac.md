# Verify Checksum on Mac
## 1. openssl
```shell
Standard commands
asn1parse      ca             ciphers        crl            crl2pkcs7      
dgst           dh             dhparam        dsa            dsaparam       
ec             ecparam        enc            engine         errstr         
gendh          gendsa         genrsa         nseq           ocsp           
passwd         pkcs12         pkcs7          pkcs8          prime          
rand           req            rsa            rsautl         s_client       
s_server       s_time         sess_id        smime          speed          
spkac          verify         version        x509           

Message Digest commands (see the `dgst' command for more details)
md2            md4            md5            mdc2           rmd160         
sha            sha1           

Cipher commands (see the `enc' command for more details)
aes-128-cbc    aes-128-ecb    aes-192-cbc    aes-192-ecb    aes-256-cbc    
aes-256-ecb    base64         bf             bf-cbc         bf-cfb         
bf-ecb         bf-ofb         cast           cast-cbc       cast5-cbc      
cast5-cfb      cast5-ecb      cast5-ofb      des            des-cbc        
des-cfb        des-ecb        des-ede        des-ede-cbc    des-ede-cfb    
des-ede-ofb    des-ede3       des-ede3-cbc   des-ede3-cfb   des-ede3-ofb   
des-ofb        des3           desx           rc2            rc2-40-cbc     
rc2-64-cbc     rc2-cbc        rc2-cfb        rc2-ecb        rc2-ofb        
rc4            rc4-40         seed           seed-cbc       seed-cfb       
seed-ecb       seed-ofb       
```

More details:

```shell
$ man openssl
```

### To do the Checksum for the example file `README.md`:

* **md4**

	```
	$ openssl md2 README.md
	MD4(README.md)= 31d6cfe0d16ae931b73c59d7e0c089c0
	```
* **md5**

	```
	$ openssl md5 README.md
	MD5(README.md)= d41d8cd98f00b204e9800998ecf8427e
	```
* **sha**

	```
	$ openssl sha README.md
	SHA(README.md)= f96cea198ad1dd5617ac084a3d92c6107708c0ef
	```
* **sha1**

	```
	$ openssl sha1 README.md
	SHA1(README.md)= da39a3ee5e6b4b0d3255bfef95601890afd80709
	```
* **sha256**

	```
	$ openssl dgst -sha256 README.md
	SHA256(README.md)=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855
	```
* **sha512**

	```
	$ openssl dgst -sha512 README.md
	SHA512(README.md)= cf83e1357eefb8bdf1542850d66d8007d620e4050b5715dc83f4a921d36ce9ce47d0d13c5d85f2b0ff8318d2877eec2f63b931bd47417a81a538327af927da3e
	```


## 2. shasum

* **sha1**

	```
	$ shasum -a 1 README.md
	da39a3ee5e6b4b0d3255bfef95601890afd80709  README.md
	```
* **sha256**

	```
	$ shasum -a 256 README.md
	e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855  README.md
	```
* **sha512**

	```
	$ shasum -a 512 README.md
	cf83e1357eefb8bdf1542850d66d8007d620e4050b5715dc83f4a921d36ce9ce47d0d13c5d85f2b0ff8318d2877eec2f63b931bd47417a81a538327af927da3e  README.md
	```

## 3. md5

* **md5**

	```
	$ md5 README.md
	MD5 (README.md) = d41d8cd98f00b204e9800998ecf8427e
	```