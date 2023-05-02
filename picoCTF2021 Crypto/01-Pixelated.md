# Pixelated

## Descripcion
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled2.png)

## Pistas
- [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
- Think of different ways you can "stack" images

## Solución

```
C:\Users\hectr>cd Downloads

C:\Users\hectr\Downloads>python
Python 3.8.10 (tags/v3.8.10:3d8993a, May  3 2021, 11:48:03) [MSC v.1928 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> from PIL import Image
>>> import numpy as np
>>> img1 = np.asarray(Image.open('scrambled1.png'))
>>> img2 = np.asarray(Image.open('scrambled2.png'))
>>> x = img1.copy()+img2.copy()
>>> nueva = Image.fromarray(x)
>>> nueva.save('nueva.png','PNG')
>>>
```

## Bandera
picoCTF{d562333d}

## Notas adicionales
Debes de descargar ambas imagenes y el codigo hacerlo en la carpeta en donde estan las imagenes.


## Referencias