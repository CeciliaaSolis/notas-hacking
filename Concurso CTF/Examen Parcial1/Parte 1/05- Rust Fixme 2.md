
## Descripción

*The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee?Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz).*

## Pistas

*https://doc.rust-lang.org/book/ch04-02-references-and-borrowing.html*
## Solución

*Webshell*
```
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz
--2025-04-14 00:04:15--  https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 2600:9000:20d1:7600:e:c945:f180:93a1, 2600:9000:20d1:c000:e:c945:f180:93a1, 2600:9000:20d1:c800:e:c945:f180:93a1, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|2600:9000:20d1:7600:e:c945:f180:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1585 (1.5K) [application/octet-stream]
Saving to: ‘fixme2.tar.gz’

fixme2.tar.gz             100%[====================================>]   1.55K  --.-KB/s    in 0.007s  

2025-04-14 00:04:16 (219 KB/s) - ‘fixme2.tar.gz’ saved [1585/1585]

                                                                                                       
┌──(kali㉿kali)-[~]
└─$ tar -xvzf fixme2.tar.gz                                       
fixme2/
fixme2/Cargo.toml
fixme2/Cargo.lock
fixme2/src/
fixme2/src/main.rs
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ cargo build
error: could not find `Cargo.toml` in `/home/kali` or any parent directory
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ cd fixme2  
                                                                                                       
┌──(kali㉿kali)-[~/fixme2]
└─$ cargo build
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/kali/fixme2)
error[E0596]: cannot borrow `*borrowed_string` as mutable, as it is behind a `&` reference
 --> src/main.rs:9:5
  |
9 |     borrowed_string.push_str("PARTY FOUL! Here is your flag: ");
  |     ^^^^^^^^^^^^^^^ `borrowed_string` is a `&` reference, so the data it refers to cannot be borrowed as mutable                                                                                          
  |
help: consider changing this to be a mutable reference
  |
3 | fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mut String){ // How do we pass values to a function that we want to change?
  |                                                        +++

error[E0596]: cannot borrow `*borrowed_string` as mutable, as it is behind a `&` reference
  --> src/main.rs:20:5
   |
20 |     borrowed_string.push_str(&String::from_utf8_lossy(&decrypted_buffer));
   |     ^^^^^^^^^^^^^^^ `borrowed_string` is a `&` reference, so the data it refers to cannot be borrowed as mutable                                                                                         
   |
help: consider changing this to be a mutable reference
   |
3  | fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mut String){ // How do we pass values to a function that we want to change?
   |                                                        +++

For more information about this error, try `rustc --explain E0596`.
error: could not compile `rust_proj` (bin "rust_proj") due to 2 previous errors
                                                                                                       
┌──(kali㉿kali)-[~/fixme2]
└─$ cd src     
                                                                                                       
┌──(kali㉿kali)-[~/fixme2/src]
└─$ nano main.rs
                                                                                                       
┌──(kali㉿kali)-[~/fixme2/src]
└─$ cargo build 
   Compiling rust_proj v0.1.0 (/home/kali/fixme2)
error[E0308]: mismatched types
  --> src/main.rs:35:31
   |
35 |     decrypt(encrypted_buffer, &party_foul); // Is this the correct way to pass a value to a fun...
   |     -------                   ^^^^^^^^^^^ types differ in mutability
   |     |
   |     arguments to this function are incorrect
   |
   = note: expected mutable reference `&mut String`
                      found reference `&String`
note: function defined here
  --> src/main.rs:3:4
   |
3  | fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mut String){ // How do we pass values to...
   |    ^^^^^^^                           ----------------------------

For more information about this error, try `rustc --explain E0308`.
error: could not compile `rust_proj` (bin "rust_proj") due to 1 previous error
                                                                                                       
┌──(kali㉿kali)-[~/fixme2/src]
└─$ nano main.rs
                                                                                                       
┌──(kali㉿kali)-[~/fixme2/src]
└─$ cargo build 
   Compiling rust_proj v0.1.0 (/home/kali/fixme2)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 1.19s
                                                                                                       
┌──(kali㉿kali)-[~/fixme2/src]
└─$ cargo run   
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.03s
     Running `/home/kali/fixme2/target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{4r3_y0u_h4v1n5_fun_y31?}

```
picoCTF{4r3_y0u_h4v1n5_fun_y31?}
## Notas Adicionales 

*Como ya tenia instalado rust, solamente descargue el archivo, lo descomprimi, vi que habia dentro y compile el rust, me mostraba errores, entonces con ayuda de la pista, pude corregirlo al entrar a nano main.rs, agregue el mut que venia en la documentación, guarde el achrivo corregido y ahora si lo compile y  corri y mostro la bandera.*

*mut:. variables mutables, que se pueden usar en cualquier lugar donde se pueda vincular un valor a un nombre de variable.*
## Referencias 

https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz

https://doc.rust-lang.org/book/ch04-02-references-and-borrowing.html