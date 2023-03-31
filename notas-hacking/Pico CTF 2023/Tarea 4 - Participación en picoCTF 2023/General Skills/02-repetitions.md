# repetitions



## Descripción
Can you make sense of this file?Download the file [here](https://artifacts.picoctf.net/c/304/enc_flag).

## Pistas
- Multiple decoding is always good.

## Solución

- Se descarga el archivo en donde se encuntra la bandera en base64
- Con base64 se va decifrando la bandera:
``` bash
──(kali㉿kali)-[~/Descargas]
└─$ ls                                                                                                                 
 enc_flag    
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas]
└─$ cat enc_flag                                                                                                       
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbFZrTTBKdldXeG9iMDFHV2tkV2JFNXBDbUY2UmtoWk1GWlhWMGRHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas]
└─$ cat enc_flag | base64 -d
VjFSQ2EyTXlSblJUV0dSVllrWmFWRmx0TlZOalJtUlhZVVU1YVZKVVZuaFdWekZoWVZkR2NrNVVX
bUZTVmtwUVdWUkdibVZXVm5WUgpiSEJzWVRCd2VWVXhXbXBOUlRWSFdqTnNWZ3BYUjFKeVZGZHdW
MlZzVWxaVmJFNW9UVVJDTlZaWE1XRlVkM0JvWWxob01GWkdWbE5pCmF6RkhZMFZXV0dGdGVFVlhi
bTkzVDFWT2JsQlVNRXNLCg==
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas]
└─$ cat enc_flag | base64 -d | base64 -d
V1RCa2MyRnRTWGRVYkZaVFltNVNjRmRXYUU5aVJUVnhWVzFhYVdGck5UWmFSVkpQWVRGbmVWVnVR
bHBsYTBweVUxWmpNRTVHWjNsVgpXR1JyVFdwV2VsUlZVbE5oTURCNVZXMWFUd3BoYlhoMFZGVlNi
azFHY0VWWGFteEVXbm93T1VOblBUMEsK
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas]
└─$ cat enc_flag | base64 -d | base64 -d | base64 -d
WTBkc2FtSXdUbFZTYm5ScFdWaE9iRTVxVW1aaWFrNTZaRVJPYTFneVVuQlpla0pyU1ZjME5GZ3lV
WGRrTWpWelRVUlNhMDB5VW1aTwphbXh0VFVSbk1GcEVXamxEWnowOUNnPT0K
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas]
└─$ cat enc_flag | base64 -d | base64 -d | base64 -d | base64 -d
Y0dsamIwTlVSbnRpWVhObE5qUmZiak56ZEROa1gyUnBZekJrSVc0NFgyUXdkMjVzTURSa00yUmZO
amxtTURnMFpEWjlDZz09Cg==
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas]
└─$ cat enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d
cGljb0NURntiYXNlNjRfbjNzdDNkX2RpYzBkIW44X2Qwd25sMDRkM2RfNjlmMDg0ZDZ9Cg==
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas]
└─$ cat enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_69f084d6}
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas]
└─$ 

```

## Bandera
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_69f084d6}