
## Descripción

*Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag! Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).*

## Pistas

*Cargo is Rust's package manager and will make your life easier. See the getting started page [here](https://doc.rust-lang.org/book/ch01-03-hello-cargo.html)*

*[println!](https://doc.rust-lang.org/std/macro.println.html)*

*Rust has some pretty great compiler error messages. Read them maybe?*
## Solución

*Webshell*
```
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz
--2025-04-13 23:44:21--  https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 2600:9000:20d1:9400:e:c945:f180:93a1, 2600:9000:20d1:3600:e:c945:f180:93a1, 2600:9000:20d1:4e00:e:c945:f180:93a1, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|2600:9000:20d1:9400:e:c945:f180:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1415 (1.4K) [application/octet-stream]
Saving to: ‘fixme1.tar.gz’

fixme1.tar.gz             100%[====================================>]   1.38K  --.-KB/s    in 0s      

2025-04-13 23:44:21 (13.8 MB/s) - ‘fixme1.tar.gz’ saved [1415/1415]

                                                                                                       
┌──(kali㉿kali)-[~]
└─$ tar -xvzf fixme1.tar.gz
fixme1/
fixme1/Cargo.toml
fixme1/Cargo.lock
fixme1/src/
fixme1/src/main.rs
                                                                                                       
┌──(kali㉿kali)-[~]
└─$ cd fixme1 
                                                                                                       
┌──(kali㉿kali)-[~/fixme1]
└─$ cargo build
Command 'cargo' not found, but can be installed with:
sudo apt install cargo 
sudo apt install rustup
                                                                                                       
┌──(kali㉿kali)-[~/fixme1]
└─$ sudo apt install rustup
[sudo] password for kali: 
Sorry, try again.
[sudo] password for kali: 
Error: Unable to locate package rustup
                                                                                                       
┌──(kali㉿kali)-[~/fixme1]
└─$ curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

info: downloading installer

Welcome to Rust!

This will download and install the official compiler for the Rust
programming language, and its package manager, Cargo.

Rustup metadata and toolchains will be installed into the Rustup
home directory, located at:

  /home/kali/.rustup

This can be modified with the RUSTUP_HOME environment variable.

The Cargo home directory is located at:

  /home/kali/.cargo

This can be modified with the CARGO_HOME environment variable.

The cargo, rustc, rustup and other commands will be added to
Cargo's bin directory, located at:

  /home/kali/.cargo/bin

This path will then be added to your PATH environment variable by
modifying the profile files located at:

  /home/kali/.profile
  /home/kali/.bashrc
  /home/kali/.zshenv

You can uninstall at any time with rustup self uninstall and
these changes will be reverted.

Current installation options:


   default host triple: x86_64-unknown-linux-gnu
     default toolchain: stable (default)
               profile: default
  modify PATH variable: yes

1) Proceed with standard installation (default - just press enter)
2) Customize installation
3) Cancel installation
>

info: profile set to 'default'
info: default host triple is x86_64-unknown-linux-gnu
info: syncing channel updates for 'stable-x86_64-unknown-linux-gnu'
info: latest update on 2025-04-03, rust version 1.86.0 (05f9846f8 2025-03-31)
info: downloading component 'cargo'
  8.8 MiB /   8.8 MiB (100 %) 719.5 KiB/s in  9s         
info: downloading component 'clippy'
  2.8 MiB /   2.8 MiB (100 %)   1.5 MiB/s in  2s         
info: downloading component 'rust-docs'
 21.2 MiB /  21.2 MiB (100 %) 470.0 KiB/s in 26s         
info: downloading component 'rust-std'
 27.1 MiB /  27.1 MiB (100 %)   5.3 MiB/s in  5s         
info: downloading component 'rustc'
 72.8 MiB /  72.8 MiB (100 %) 609.4 KiB/s in  1m 15s          
info: downloading component 'rustfmt'
  2.4 MiB /   2.4 MiB (100 %)   1.2 MiB/s in  1s         
info: installing component 'cargo'
  8.8 MiB /   8.8 MiB (100 %)   4.7 MiB/s in  1s         
info: installing component 'clippy'
info: installing component 'rust-docs'
 21.2 MiB /  21.2 MiB (100 %)   1.5 MiB/s in 21s             
info: installing component 'rust-std'
 27.1 MiB /  27.1 MiB (100 %)   3.2 MiB/s in  8s         
info: installing component 'rustc'
 72.8 MiB /  72.8 MiB (100 %)   3.5 MiB/s in 19s         
info: installing component 'rustfmt'
info: default toolchain set to 'stable-x86_64-unknown-linux-gnu'

  stable-x86_64-unknown-linux-gnu installed - rustc 1.86.0 (05f9846f8 2025-03-31)


Rust is installed now. Great!

To get started you may need to restart your current shell.
This would reload your PATH environment variable to include
Cargo's bin directory ($HOME/.cargo/bin).

To configure your current shell, you need to source
the corresponding env file under $HOME/.cargo.

This is usually done by running one of the following (note the leading DOT):
. "$HOME/.cargo/env"            # For sh/bash/zsh/ash/dash/pdksh
source "$HOME/.cargo/env.fish"  # For fish
source "$HOME/.cargo/env.nu"    # For nushell
                                                                                                       
┌──(kali㉿kali)-[~/fixme1]
└─$ cargo build                                                   
Command 'cargo' not found, but can be installed with:
sudo apt install cargo 
sudo apt install rustup
                                                                                                       
┌──(kali㉿kali)-[~/fixme1]
└─$ rustc --version

Command 'rustc' not found, but can be installed with:
sudo apt install rustc 
sudo apt install rustup
                                                                                                       
┌──(kali㉿kali)-[~/fixme1]
└─$ source $HOME/.cargo/env

                                                                                                       
┌──(kali㉿kali)-[~/fixme1]
└─$ source $HOME/.cargo/env

                                                                                                       
┌──(kali㉿kali)-[~/fixme1]
└─$ cargo build            
    Updating crates.io index
  Downloaded xor_cryptor v1.2.3
  Downloaded crossbeam-utils v0.8.20
  Downloaded crossbeam-deque v0.8.5
  Downloaded either v1.13.0
  Downloaded crossbeam-epoch v0.9.18
  Downloaded rayon-core v1.12.1
  Downloaded rayon v1.10.0
  Downloaded 7 crates (388.2 KB) in 1.21s
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/kali/fixme1)
error: expected `;`, found keyword `let`
 --> src/main.rs:5:37
  |
5 |     let key = String::from("CSUCKS") // How do we end statements in Rust?
  |                                     ^ help: add `;` here
...
8 |     let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", "1c", "7e", "59", "6...
  |     --- unexpected token

error: argument never used
  --> src/main.rs:26:9
   |
25 |         ":?", // How do we print out a variable in the println function? 
   |         ---- formatting specifier missing
26 |         String::from_utf8_lossy(&decrypted_buffer)
   |         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ argument never used

error[E0425]: cannot find value `ret` in this scope
  --> src/main.rs:18:9
   |
18 |         ret; // How do we return in rust?
   |         ^^^ help: a local variable with a similar name exists: `res`

For more information about this error, try `rustc --explain E0425`.
error: could not compile `rust_proj` (bin "rust_proj") due to 3 previous errors
                                                                                                       
┌──(kali㉿kali)-[~/fixme1]
└─$ cd src     
                                                                                                       
┌──(kali㉿kali)-[~/fixme1/src]
└─$ nano main.rs
                                                                                                       
┌──(kali㉿kali)-[~/fixme1/src]
└─$ cargo build 
   Compiling rust_proj v0.1.0 (/home/kali/fixme1)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 1.07s
                                                                                                       
┌──(kali㉿kali)-[~/fixme1/src]
└─$ cargo run  
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.04s
     Running `/home/kali/fixme1/target/debug/rust_proj`
picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}:?

```
picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}
## Notas Adicionales 

*Descargue el archivo, lo descomprimi, vi que contenia.*
*Al ser el primer reto de este tipo, me di cuenta que no tenia instalado rust en kali linux, lo que hice fue instalarlo,para despues hacer el cargo build donde nos muestra los errores de sintaxis, por medio de las pistas y entrar a la pagina donde explican algunos comandos de rust, vi que faltaba un ; y un print le faltaba {}, en un return decia ret y lo complete, finalmente volvi hacer build  que es compilar en rust, ya no mando errores y luego cargo run para correrlo y que nos mostrara la bandera.*

## Referencias 

https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz