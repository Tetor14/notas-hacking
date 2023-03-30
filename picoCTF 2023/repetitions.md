## Descripcion
Can you make sense of this file? Download the file [here](https://artifacts.picoctf.net/c/471/enc_flag).

## Pistas 
****** 
## Solucion
```
jt@jt-VirtualBox:~/Downloads$ cat enc_flag | base64 -d
VjFSQ2EyTXlSblJUV0dSVllrWmFWRmx0TlZOalJtUlhZVVU1YVZKVVZuaFdWekZoWVZkR2NrNVVX
bUZTVmtwUVdWUkdibVZXVm5WUgpiSEJzWVRCd2VWVXhXbXBOUlRWSFdqTnNWZ3BYUjFKeVZGZHdW
MlZzVWxaVmJFNW9UVVJDTlZaWE1XRlhaM0JYVWxoQ2VWWkdXbXRUCmF6VkhZa2hHV0dGdGVFVlhi
bTkzVDFWT2JsQlVNRXNLCg==
jt@jt-VirtualBox:~/Downloads$ !! | base64 -d
cat enc_flag | base64 -d | base64 -d
V1RCa2MyRnRTWGRVYkZaVFltNVNjRmRXYUU5aVJUVnhWVzFhYVdGck5UWmFSVkpQWVRGbmVWVnVR
bHBsYTBweVUxWmpNRTVHWjNsVgpXR1JyVFdwV2VsUlZVbE5oTURCNVZXMWFXZ3BXUlhCeVZGWmtT
azVHYkhGWGFteEVXbm93T1VOblBUMEsK
jt@jt-VirtualBox:~/Downloads$ !! | base64 -d
cat enc_flag | base64 -d | base64 -d | base64 -d
WTBkc2FtSXdUbFZTYm5ScFdWaE9iRTVxVW1aaWFrNTZaRVJPYTFneVVuQlpla0pyU1ZjME5GZ3lV
WGRrTWpWelRVUlNhMDB5VW1aWgpWRXByVFZkSk5GbHFXamxEWnowOUNnPT0K
jt@jt-VirtualBox:~/Downloads$ !! | base64 -d
cat enc_flag | base64 -d | base64 -d | base64 -d | base64 -d
Y0dsamIwTlVSbnRpWVhObE5qUmZiak56ZEROa1gyUnBZekJrSVc0NFgyUXdkMjVzTURSa00yUmZZ
VEprTVdJNFlqWjlDZz09Cg==
jt@jt-VirtualBox:~/Downloads$ !! | base64 -d
cat enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d
cGljb0NURntiYXNlNjRfbjNzdDNkX2RpYzBkIW44X2Qwd25sMDRkM2RfYTJkMWI4YjZ9Cg==
jt@jt-VirtualBox:~/Downloads$ !! | base64 -d
cat enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_a2d1b8b6}
jt@jt-VirtualBox:~/Downloads$ 
```
## bandera
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_a2d1b8b6}

## Notas adicionales 

## Referencias