# Generate Local SSL Certificates

## 1. Create the `openssl-san.cnf` file

```ini
[req]
default_bits       = 2048
prompt             = no
default_md         = sha256
distinguished_name = dn
req_extensions     = req_ext

[dn]
CN = localhost

[req_ext]
subjectAltName = @alt_names

[alt_names]
DNS.1 = localhost
IP.1 = 127.0.0.1
IP.2 = ::1
```

## 2. Generate the private key (`cert.key`)

```powershell
openssl genrsa -out cert.key 2048
```

## 3. Generate the certificate (`cert.crt`), valid for **365** days

```powershell
openssl req -x509 -new -nodes -key cert.key -sha256 -days 365 -out cert.crt -config .\openssl-san.cnf -extensions req_ext
```

### Verify the certificate

```powershell
openssl x509 -in cert.crt -noout -text
```

You should see something like:

```text
X509v3 Subject Alternative Name:
    DNS:localhost
    IP Address:127.0.0.1
    IP Address:::1

Validity
    Not Before: Feb 26 13:00:00 2026 GMT
    Not After : Feb 26 13:00:00 2027 GMT
```

## 4. Generate the `.pem` file

```powershell
Get-Content cert.key, cert.crt | Set-Content cert.pem
```

## 5. (Optional) Generate the `.pfx` file

```powershell
openssl pkcs12 -export -out cert.pfx -inkey cert.key -in cert.crt -password pass:anyPasswordWillDo
```

### PFX verification

```powershell
openssl pkcs12 -info -in cert.pfx -password pass:anyPasswordWillDo -nodes
```

---

⚠️ All the above commands must be run in **PowerShell** as **Administrator**.

---

## Summary

This process will generate a private key `cert.key` and a public certificate `cert.crt` that can be used to enable HTTPS in your local applications or servers.
