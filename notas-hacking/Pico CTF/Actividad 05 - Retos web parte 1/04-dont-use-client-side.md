# dont-use-client-side


## Descripción
Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/37821/` ([link](https://jupiter.challenges.picoctf.org/problem/37821/)) or http://jupiter.challenges.picoctf.org:37821

## Pistas
- Never trust the client

## Solución

- Entramos a la pagina web:  [link](https://jupiter.challenges.picoctf.org/problem/37821/)
- Inspeccionar el código fuente
- Se tiene una función llamada **verificar**,  que verifica si la contraseña ingresada es correcta. Al leer la función línea por línea podemos obtener la contraseña.

**1-**  Primero obtenemos el valor insertado por el usuario en la variable checkpass

**2-**  Luego de esto, le asignamos 4 a la variable split. 

**3-**  La primera declaración if verifica si las primeras 4 posiciones de la contraseña dada son "pico", si es así, pasa a la siguiente declaración if.

**4-**  El segundo if verifica si el valor en el intervalo entre las posiciones 24 a 28 (-1) es a3c8, si es cierto pasa al siguiente if..

**5-**  El tercer if compara el intervalo entre las posiciones 4 a 8 (-1) a CTF{, si es cierto pasa al siguiente if.

**6-**  Y así sucesivamente... hata encontrar la bandera completa.

``` bash
<script type="text/javascript">

function verify() {

checkpass = document.getElementById("pass").value;

split = 4;

if (checkpass.substring(0, split) == 'pico') {

if (checkpass.substring(split*6, split*7) == 'a3c8') {

if (checkpass.substring(split, split*2) == 'CTF{') {

if (checkpass.substring(split*4, split*5) == 'ts_p') {

if (checkpass.substring(split*3, split*4) == 'lien') {

if (checkpass.substring(split*5, split*6) == 'lz_1') {

if (checkpass.substring(split*2, split*3) == 'no_c') {

if (checkpass.substring(split*7, split*8) == '9}') {

alert("Password Verified")

}
```
Despues de haber comparado todas las sentencia if, obtenemos la bandera.

## Bandera
picoCTF{no_clients_plz_1a3c89}


