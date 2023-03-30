# Permissions
## Descripción
Can you read files in the root file?
The system admin has provisioned an account for you on the main server: `ssh -p 59565 picoplayer@saturn.picoctf.net` Password: `GhHrPQ2+zL` Can you login and read the root file?

## Pistas
- What permissions do you have?
## Solución
La forma de solucionarlo fue entrando a dicho servidor desde el bash.
Una vez dentro, usé el cd para retroceder hasta el root.
En la raíz encontré una carpeta llamada challenge, entré a ella y encontré un archivo .json
Di un cat en es archivo y en él se encontraba la bandera.

```bash
picoplayer@challenge:/$ ls
bin  boot  challenge  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
picoplayer@challenge:/$ cd challenge
picoplayer@challenge:/challenge$ ls
metadata.json
picoplayer@challenge:/challenge$ cat metadata.json
{"flag": "picoCTF{uS1ng_v1m_3dit0r_3dd6dcf4}", "username": "picoplayer", "password": "GhHrPQ2+zL"}picoplayer@challenge:/challenge$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
```

## Bandera
picoCTF{uS1ng_v1m_3dit0r_3dd6dcf4}

## Notas adicionales
None

## Referencias
None