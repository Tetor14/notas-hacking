# dont-use-client-side

## Descripcion
Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/37821/` ([link](https://jupiter.challenges.picoctf.org/problem/37821/)) or http://jupiter.challenges.picoctf.org:37821

## Pistas
- Never trust the client

## Solución

```
En el codigo fuente de la pagina se puede ver la bandera fragmentada en partes de cuatro caracteres, en el primer substring se toma desde la posición 0 hasta 4, y para las siguientes subcadenas puedes seguir el orden viendo el valor por el que se multiplica el primer split.
```

## Bandera
picoCTF{no_clients_plz_1a3c89}

## Notas adicionales
En el codigo se puede ver que se hace la validación del lado del cliente, cosa que nos permite encontrar la bandera mas facil.

## Referencias
https://www.cloudflare.com/es-es/learning/serverless/glossary/client-side-vs-server-side/