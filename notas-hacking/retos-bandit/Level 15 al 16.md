# Bandit Level 15 → Level 16


## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

## Datos de acceso al nivel 
- bandit15
- jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## Solución
``` bash
bandit15@bandit:~$  openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 24 22:59:04 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 24 22:59:04 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 24 22:58:04 2023 GMT; NotAfter: Feb 24 22:59:04 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEdtHsNjANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwMjI0MjI1ODA0WhcNMjMwMjI0MjI1OTA0WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCx
mrCINhzIGCIeMR5GsleGkWUZWNcLl1D3FFa0OwDgYG0lj4VP3fC2jf7SJ8DbMdGT
jqyOhsM+LZhKWPJ+NH60lzWTeYq6/pe2OMFhZ6bbd84coT7Fo7Evjk4bye2+qYsH
J6MR7Gk+bhL9U4KpCVOpZwHitiC4ZbX+s7n8PHQsfMeQfhSS7J+Xa0vTw3KQoVCg
3BhKTD9bt3gXVfGNaIvECku2sCECDkFyCR5+AqswPHCT7QK8Q3sb9gbA0/zhWbXb
h4RVpbwm+NqmDivMxPVSH+J6NzgmBpLTpeFsN05rlN9CdzRP9l+tLCJnf1irtKMI
0KkVzlGMg/vwLKYA0G5pAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQBx
vsPCAfYKiOZH0RDDB18SoiFpjkw3A9lSM14tvFlYsEdx31DvJNwc6QT/E8uOV2sB
Kl4wGwJQPJ7VT93CClFN3je9drqlNryCm+P4VO1Fhay8JIb6PyW0z4WCIlJqCRKT
68SPozIEfx/lwquR+MPyopny7tIlA1IZN4aF5yA+Gi570zC7UtdRBVyfGrdANeS8
5pmwA2NzxauCh3QJc2jWYVk4qmmTsLJBgElaFN1QrZHk60rxaUjS4rFnsSYZ/d4n
kmj3TPpRidAxlDM5qnXqD7fcBNy3s7XXk40ygWS/GsJJx38sHr0yFmMV7l0QKVBC
rsP6Hy0UaGAkUNBjj/Fi
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 1989DD0365C76047E33A90142C266A4F4C96D8FC531896CAAA325A0AA5DFA2B1
    Session-ID-ctx:
    Resumption PSK: B23382C478C0037B715F8A1BFD41196C8259AF73F180A427675B341713A1240886AAFC8ABB0FB7A17816CA3AEC7CE767
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - cb 00 ae d3 fc cf 12 aa-e1 f0 d3 ef 6c 0e a6 aa   ............l...
    0010 - 29 57 80 05 bf 98 79 52-c1 72 7a 02 1f d0 82 40   )W....yR.rz....@
    0020 - 7d 08 21 06 83 97 c8 cb-41 fa d5 e9 7c 53 d3 53   }.!.....A...|S.S
    0030 - fd fd f0 0c 61 10 36 29-59 f2 e9 50 80 78 60 a9   ....a.6)Y..P.x`.
    0040 - 59 d7 30 ff 1a 19 fa 76-b3 cf fe 9a 3a ef cb 25   Y.0....v....:..%
    0050 - e5 39 9b e4 ec bf 19 00-04 d2 30 0f 61 80 94 16   .9........0.a...
    0060 - 64 03 20 91 4b 90 2d 00-45 eb aa 05 77 bf 9e fb   d. .K.-.E...w...
    0070 - 6b 75 3e a7 b8 c5 54 da-aa 4c fa 4e 5a 1f 46 b8   ku>...T..L.NZ.F.
    0080 - 71 b4 ce 43 ab f5 a0 da-f1 ae 40 c5 de 3e 70 e5   q..C......@..>p.
    0090 - a8 4d 50 08 71 19 9f 8c-e5 65 85 19 17 a9 1b ce   .MP.q....e......
    00a0 - cc ca e5 b2 52 9b 53 b1-2a d2 ff a1 d2 3e 70 5b   ....R.S.*....>p[
    00b0 - 11 d3 7c 8d 78 34 cf 5e-fe 4b 5a 13 66 81 b9 67   ..|.x4.^.KZ.f..g
    00c0 - 5e 10 16 af f4 0d 6b d6-02 1a ae 6f 80 7c 66 90   ^.....k....o.|f.

    Start Time: 1677301459
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 9285B466039A1B0FC620CE7FC9DC36320A69D9EF857852A0E2EBC13F005ED064
    Session-ID-ctx:
    Resumption PSK: FD89DA0385142A00FE4ED5E76A16EA51B1220B8DD39BEA5F58E200F6F981D4A1A7A5840D9D790773C5D37E4E05D953E3
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - cb 00 ae d3 fc cf 12 aa-e1 f0 d3 ef 6c 0e a6 aa   ............l...
    0010 - 23 96 e5 b6 c1 65 9c 83-37 f5 02 fb a9 a6 eb a0   #....e..7.......
    0020 - 70 ec 93 dc ea 62 c5 bd-29 88 64 c6 0c 38 aa a1   p....b..).d..8..
    0030 - 43 ae 33 8c 39 c8 7d 9f-a6 90 a2 57 89 c4 ec 2b   C.3.9.}....W...+
    0040 - 0a 0e 35 3f d4 ff 21 b5-af 54 b4 65 bc e2 99 38   ..5?..!..T.e...8
    0050 - b5 3c df 1d 2b e3 06 e6-35 0f 0e 1b 87 72 82 74   .<..+...5....r.t
    0060 - c3 87 dc aa db 22 37 61-8b 8c fe 9a b5 d3 d3 fc   ....."7a........
    0070 - c6 8d f7 d0 27 18 15 88-62 89 01 32 d7 a2 95 52   ....'...b..2...R
    0080 - 3a b4 b6 7d 09 4f c6 91-69 fd 1f a4 d9 64 7d 02   :..}.O..i....d}.
    0090 - bd 38 37 b6 22 a7 f2 75-47 63 d2 7f f4 bd c9 2a   .87."..uGc.....*
    00a0 - e4 70 cc e5 c1 97 5e 85-8d 8b c8 25 60 91 03 b5   .p....^....%`...
    00b0 - dd 11 37 5a c9 7c 09 59-b4 62 7e 2b c4 87 90 02   ..7Z.|.Y.b~+....
    00c0 - 13 08 10 88 19 25 d6 0a-35 99 50 80 d1 00 21 13   .....%..5.P...!.

    Start Time: 1677301459
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
bandit15@bandit:~$
```


## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| openssl | viene con una herramienta de cliente que puede usar para conectarse a un servidor mediante una conexión segura. La herramienta es similar a `telnet` o `nc`, pero este utiliza SSL/TLS para la conexión. |
| s_client|implementa un cliente genérico SSL/TLS que se conecta a un host remoto mediante estos protocolos
| -connect de s_client | permite especificar el host y el puerto al cual nos vamos a conectar. El formato de este es `host:port`. |

## Referencias
-  [Writeup - Wargame Bandit - Parte 2](https://www.w0lff4ng.org/wargame-bandit-2/)
