# Local Authority




## Descripción
Can you get the flag?Go to this [website](http://saturn.picoctf.net:55983/) and see what you can discover.

## Pistas
- How is the password checked on this website?

## Solución

- Tratamos de entrar con un usuario y una contraseña:
![[Pasted image 20230420205852.png]]

- No se puede ingresar con el usuario y contraseña ingresada:
![[Pasted image 20230420205914.png]]

- Inspeccionamos el código fuente de la página y entramos a "login.php":
![[Pasted image 20230420210011.png]]

- Una vez estando en "login.php" entramos a "secure.js":
![[Pasted image 20230420210115.png]]

- Una vez que se entro a  "secure.js" podemos ver los datos para poder tener acceso a la página y encontrar la bandera:
``` bash
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```

- Se ingresa admin como usuario y la contraseña strongPassword098765:
![[Pasted image 20230420210211.png]]

- Una vez ingresando los datos obtenemos la bandera:
![[Pasted image 20230420210253.png]]

## Bandera
picoCTF{j5_15_7r4n5p4r3n7_a8788e61}
