# Insp3ct0r


## Descripción
Kishor Balan tipped us off that the following code may need inspection: `https://jupiter.challenges.picoctf.org/problem/41511/` ([link](https://jupiter.challenges.picoctf.org/problem/41511/)) or http://jupiter.challenges.picoctf.org:41511

## Pistas
- How do you inspect web code on a browser?
- There's 3 parts

## Solución

- Entramos a la pagina web:   ([link](https://jupiter.challenges.picoctf.org/problem/41511/)) 
- Dando click derecho en la pagina web seleccionamos la opción "Ver código fuente de la página", nos abre el código funte donde se encuentra de forma comentada  la primera parte de la bandera:
``` bash
<!-- Html is neat. Anyways have 1/3 of the flag: picoCTF{tru3_d3 -->
```

- Dentro del codigo fuente hay unas lineas de código en donde hay unos links y seran las otras partes de la bandera :
``` bash
<link rel="stylesheet" type="text/css" href="[mycss.css](https://jupiter.challenges.picoctf.org/problem/41511/mycss.css)">

<script type="application/javascript" src="[myjs.js](https://jupiter.challenges.picoctf.org/problem/41511/myjs.js)"></script>
```

- Entramos a cada uno de ellos:

	- En el primer link [mycss.css](https://jupiter.challenges.picoctf.org/problem/41511/mycss.css) obtenemos la segunda parte de la bandera:
		``` bash
/* You need CSS to make pretty pages. Here's part 2/3 of the flag: t3ct1ve_0r_ju5t */
```

	- En el segundo link [myjs.js](https://jupiter.challenges.picoctf.org/problem/41511/myjs.js) obtenemos la tercer parte de la bandera:
		``` bash
/* Javascript sure is neat. Anyways part 3/3 of the flag: _lucky?832b0699} */
```

## Bandera
picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?832b0699}}



