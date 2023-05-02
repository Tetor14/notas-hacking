# Mind your Ps and Qs

## Descripcion
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values)

## Pistas
- Bits are expensive, I used only a little bit over 100 to save money

## Solución

```
C:\Users\hectr\Segu\notas-hacking>python
Python 3.8.10 (tags/v3.8.10:3d8993a, May  3 2021, 11:48:03) [MSC v.1928 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> from Crypto.Util.number import long_to_bytes
>>> from Crypto.Util.number import inverse
>>> c = 421345306292040663864066688931456845278496274597031632020995583473619804626233684
>>> n = 631371953793368771804570727896887140714495090919073481680274581226742748040342637
>>> e = 65537
>>> p = 1461849912200000206276283741896701133693
>>> q = 431899300006243611356963607089521499045809
>>> tn = (p-1)*(q-1)
>>> d = inverse(e, tn)
>>> m = pow(c, d, n)
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_55304594}'
```

## Bandera
picoCTF{sma11_N_n0_g0od_55304594}

## Notas adicionales
- Descarga el archivo con los valores
- Los valores de p y q se obtienen introduciendo n en esta pagina: http://www.factordb.com/

## Referencias