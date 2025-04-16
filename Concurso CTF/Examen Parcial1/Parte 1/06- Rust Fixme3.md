
## Descripción

*Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz).*

## Pistas

*Read the comments...darn it!*
## Solución

*Webshell*
```
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz
--2025-04-14 00:11:21--  https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 2600:9000:20d1:ea00:e:c945:f180:93a1, 2600:9000:20d1:5600:e:c945:f180:93a1, 2600:9000:20d1:d600:e:c945:f180:93a1, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|2600:9000:20d1:ea00:e:c945:f180:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1776 (1.7K) [application/octet-stream]
Saving to: ‘fixme3.tar.gz’

fixme3.tar.gz             100%[====================================>]   1.73K  --.-KB/s    in 0s      

2025-04-14 00:11:22 (19.7 MB/s) - ‘fixme3.tar.gz’ saved [1776/1776]

                                                                                                       
┌──(kali㉿kali)-[~]
└─$ tar -xvzf fixme3.tar.gz
fixme3/
fixme3/Cargo.toml
fixme3/Cargo.lock
fixme3/src/
fixme3/src/main.rs
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ cargo build 
error: could not find `Cargo.toml` in `/home/kali` or any parent directory
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ cd fixme3  
                                                                                                       
┌──(kali㉿kali)-[~/fixme3]
└─$ cargo build
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/kali/fixme3)
error[E0133]: call to unsafe function `std::slice::from_raw_parts` is unsafe and requires unsafe function or block
  --> src/main.rs:31:31
   |
31 |         let decrypted_slice = std::slice::from_raw_parts(decrypted_ptr, decrypted_len);
   |                               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ call to unsafe function                                                                                           
   |
   = note: consult the function's documentation for information on how to avoid undefined behavior

For more information about this error, try `rustc --explain E0133`.
error: could not compile `rust_proj` (bin "rust_proj") due to 1 previous error
                                                                                                       
┌──(kali㉿kali)-[~/fixme3]
└─$ cd src     
                                                                                                       
┌──(kali㉿kali)-[~/fixme3/src]
└─$ nano main.rs
                                                                                                       
┌──(kali㉿kali)-[~/fixme3/src]
└─$ cargo build 
   Compiling rust_proj v0.1.0 (/home/kali/fixme3)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 1.24s
                                                                                                       
┌──(kali㉿kali)-[~/fixme3/src]
└─$ cargo run  
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.03s
     Running `/home/kali/fixme3/target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{n0w_y0uv3_f1x3d_1h3m_411}

```
picoCTF{n0w_y0uv3_f1x3d_1h3m_411}
## Notas Adicionales 

*Descargamos el archivo, lo descomprimimos, lo compilamos y hay errores, entramos a src y despues nano main.rs para corregir el codigo, me doy cuenta que en los comentarios hay lineas que deben estar sin comentar, las descomente, guarde el archivo, lo compile con cargo build, lo cori con cargo run y finalmente me mostro la bandera.*
## Referencias 

https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz