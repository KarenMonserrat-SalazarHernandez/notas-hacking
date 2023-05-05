# Includes




## Descripción
Can you get the flag?Go to this [website](http://saturn.picoctf.net:54554/) and see what you can discover.

## Pistas
- Is there more code than what the inspector initially shows?

## Solución

- Inspeccionamos el código fuente de la página:
![[Pasted image 20230420203617.png]]

- Entramos a "style.css" y encontramos la primera parte de la bandera:
``` bash
body {
  background-color: lightblue;
}

/*  picoCTF{1nclu51v17y_1of2_  */
```

- Despues entramos a "script.js" y encontramos la segunda parte de la bandera:
``` bash
function greetings()
{
  alert("This code is in a separate file!");
}

//  f7w_2of2_df589022}
```

## Bandera
picoCTF{1nclu51v17y_1of2_f7w_2of2_df589022}



