# Reto

## Descripcion
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:28916/](http://mercury.picoctf.net:28916/)

## Pistas
- Maybe you have more than 2 choices
- Check out tools like Burpsuite to modify your requests and look at the responses

## Solución

```
Debes inspeccionar la pagina e ir a la parte de red, luego clickear el boton que dice "choose blue" y veras la peticion que se hizo, la peticion es de tipo POST, deberas modificarla a HEAD para obtener la bandera.
```

## Bandera
picoCTF{r3j3ct_th3_du4l1ty_70bc61c4}

## Notas adicionales

## Referencias