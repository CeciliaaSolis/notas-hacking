## Descripción

*How about some hide and seek?Download this file [here](https://artifacts.picoctf.net/c_titan/6/unknown.zip).*
## Pistas

*How can you view the information about the picture?*

*If something isn't in the expected form, maybe it deserves attention?*
## Solución

*Kali*
```
                                                                                                      
┌──(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c_titan/6/unknown.zip   
--2025-05-11 00:58:12--  https://artifacts.picoctf.net/c_titan/6/unknown.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:3a00:16:5ec5:2840:93a1, 2600:9000:25ed:9600:16:5ec5:2840:93a1, 2600:9000:25ed:5e00:16:5ec5:2840:93a1, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:3a00:16:5ec5:2840:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2252298 (2.1M) [application/octet-stream]
Saving to: ‘unknown.zip’

unknown.zip               100%[===================================>]   2.15M  2.20MB/s    in 1.0s    

2025-05-11 00:58:13 (2.20 MB/s) - ‘unknown.zip’ saved [2252298/2252298]

                                                                                                      
┌──(kali㉿kali)-[~]
└─$ unzip unknown.zip  
Archive:  unknown.zip
  inflating: ukn_reality.jpg         
                                                                                                      
┌──(kali㉿kali)-[~]
└─$ ls
Desktop  ukn_reality.jpg  unknown.zip
                                                                                                      
┌──(kali㉿kali)-[~]
└─$ exiftool ukn_reality.jpg 
ExifTool Version Number         : 13.00
File Name                       : ukn_reality.jpg
Directory                       : .
File Size                       : 2.3 MB
File Modification Date/Time     : 2024:02:15 17:40:21-05:00
File Access Date/Time           : 2024:02:15 17:40:21-05:00
File Inode Change Date/Time     : 2025:05:11 00:59:14-04:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 72
Y Resolution                    : 72
XMP Toolkit                     : Image::ExifTool 11.88
Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fYTZkZjhkYjh9Cg==
Image Width                     : 4308
Image Height                    : 2875
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 4308x2875
Megapixels                      : 12.4
                                                                                                      
┌──(kali㉿kali)-[~]
└─$ echo "cGljb0NURntNRTc0RDQ3QV9ISUREM05fYTZkZjhkYjh9Cg=="| base64 -d
picoCTF{ME74D47A_HIDD3N_a6df8db8}

```

## Notas Adicionales 

*Descargamos el archivo zip, lo descomprimimos y vemos que nos dio una imagen .jpg, observamos que tiene con exiftool para ver los metadatos, de igual manera hay un codigo que parece base 64, le hacemos un echo, y efectivamente nos da la bandera ya decodificada.*

## Referencias 

