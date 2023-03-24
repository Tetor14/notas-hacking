# where are the robots

## Descripcion
Can you find the robots? `https://jupiter.challenges.picoctf.org/problem/36474/` ([link](https://jupiter.challenges.picoctf.org/problem/36474/)) or http://jupiter.challenges.picoctf.org:36474

## Pistas
- What part of the website could tell you where the creator doesn't want you to look?

## Solución

```
Debes ingresar robots.txt a un lado del link de la página y se mostraran las páginas
no indexadas al sitio, en robots.txt encontraras una cadena que debes pegar en el 
enlace y ahí se encuentra la bandera.
```

## Bandera
picoCTF{ca1cu1at1ng_Mach1n3s_477ce}

## Notas adicionales
En robots.txt se almacenan los sitios que no seran indexados

## Referencias
https://developers.google.com/search/docs/crawling-indexing/robots/intro?hl=es