# JaWT Scratchpad

## Descripcion
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/63090/` or http://jupiter.challenges.picoctf.org:63090

## Pistas
- What is that cookie?
- Have you heard of JWT?

## Solución

```
Debes crackear la cookie del sitio con la palabra admin, pero tambien debes de averiguar la firma de la cookie, para esto debes de hacer uso de john, una programa para crackear cookies, john lo puedes descargar en la misma pagina del reto, la palabra para crackear la cookies es : "ilovepico", ahora genera la cookie con el usuario admin y la palabra obtenida con john y pegala en las cookies del sitio.
```

## Bandera
picoCTF{jawt_was_just_what_you_thought_f859ab2f}

## Notas adicionales
Tienes que hacer uso de john y tener descargado rockyou.txt

## Referencias
https://es.wikipedia.org/wiki/JSON