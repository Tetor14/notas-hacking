# m00nwalk

## Descripcion
Decode this [message](https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav) from the moon.

## Pistas
- How did pictures from the moon landing get sent back to Earth?
- What is the CMU mascot?, that might help select a RX option

## Solución

```
Debemos instalar SSTV en nuestra maquina y descargar el archivo con los siguientes comandos:
wget https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav
git clone https://github.com/colaclanth/sstv.git
python setup.py install
Una vez instalados debemos ejecutar la siguiente linea: 
sstv -d message.wav -o result.png
Despues debemos de ir a la ubicación en donde esta result.png y veremos una imagen con la bandera.
```

## Bandera
picoCTF{beep_boop_im_in_space}

## Notas adicionales

## Referencias