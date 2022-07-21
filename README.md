# pgp-encrypt-decrypt-sftp

This sample includes steps to follow in order to setup PGP Encryption and Decryption of NACHA files with the help of Operations in SFTP route.

## Quick start

Clone this repo for easy start. Make sure you have permissions to configure SFTP routes (you able to see SFTP tab on Dashboard in Routes section). If not, contact support@verygoodsecurity.com.

#### 1. Fill in the .env file:
```
VAULT="tntenbznyv2"
ENVIRONMENT="sandbox"
NAME="Corey Taylor"
EMAIL="corey.taylor@email.com"
TESTFILE="file.txt"
```
#### 2. Install gnupg:
```
pip install python-gnupg
```
#### 3. Generate keys:

It will ask you for the passphrase. You'll get the fingerprint on the output:
```
python quick_start.py generate_keys
```
If you have GPG Keychain installed, the keys are automatically added there.
#### 4. Import inbound_route.yml:
This is the basic Inbound Route that redacts three JSON fields: `$.private_key`, `$.public_key` and `$.passphrase`.
Make sure it does not conflict with another Inbound Route.
#### 5. Alias the keys:
It will again ask for the passphrase since the script needs to get the private key from GPG DB:
```
python quick_start.py create_aliases
```
On the output you'll get three aliases:
```

```

















