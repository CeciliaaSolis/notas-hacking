## Descripción

*Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/d1375e383810d8d957c04eef9e345732/cat.jpg)*
## Pistas

*Look at the details of the file*
*Make sure to submit the flag as picoCTF{XXXXX}*
## Solución

*Kali*
```
┌──(kali㉿kali)-[~]
└─$ wget https://mercury.picoctf.net/static/d1375e383810d8d957c04eef9e345732/cat.jpg
--2025-05-11 00:02:12--  https://mercury.picoctf.net/static/d1375e383810d8d957c04eef9e345732/cat.jpg
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 878136 (858K) [application/octet-stream]
Saving to: ‘cat.jpg’

cat.jpg                   100%[===================================>] 857.55K   660KB/s    in 1.3s    

2025-05-11 00:02:14 (660 KB/s) - ‘cat.jpg’ saved [878136/878136]

                                                                                                      
┌──(kali㉿kali)-[~]
└─$ file cat.jpg       
cat.jpg: JPEG image data, JFIF standard 1.02, aspect ratio, density 1x1, segment length 16, baseline, precision 8, 2560x1598, components 3
                                                                                                      
┌──(kali㉿kali)-[~]
└─$ exiftool cat.jpg       
ExifTool Version Number         : 13.00
File Name                       : cat.jpg
Directory                       : .
File Size                       : 878 kB
File Modification Date/Time     : 2021:03:15 14:24:46-04:00
File Access Date/Time           : 2025:05:11 00:02:19-04:00
File Inode Change Date/Time     : 2025:05:11 00:02:14-04:00
File Permissions                : -rw-rw-r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
                                         
```

Cyberchef
Input: cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Recipe: From Base64
Output:picoCTF{the_m3tadata_1s_modified}
## Notas Adicionales 

*Solo descargue el archivo,vi de que tipo era,decidi ver con exiftool los metadatos de la imagen,en la license parece algo encriptado, entonces lo paso a cyberchef me da la opcion de que parece base 64, lo decodifica y sale la bandera.*
## Referencias 

https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnQwYUdWZmJUTjBZV1JoZEdGZk1YTmZiVzlrYVdacFpXUjkNCg&ieol=CRLF&oeol=CRLF