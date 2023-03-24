# Reto

## Descripcion
Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:64944/](http://mercury.picoctf.net:64944/)

## Pistas


## Solución

```
Al entrar en la pagina se te pedira un tipo de galleta para obtener la bandera, por lo que se desarrollo un codigo para buscar todas las posibles galletas mas faciles.
import requests
import re

url= "http://mercury.picoctf.net:64944/check"

for i in range(21):
	cookies = {'name':'{}'.format(i)}
	r = requests.get(url, cookies=cookies)
	if 'picoCTF{' in r.text:
		flag=re.findall('picoCTF\{.*\}',r.text)[0]
		print(flag)
```

## Bandera
picoCTF{3v3ry1_l0v3s_c00k135_cc9110ba}

## Notas adicionales

## Referencias