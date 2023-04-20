# waves over lambda




## Descripción
We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 43522`.

## Pistas
- Flag is not in the usual flag format

## Solución

- Nos conectamos al puerto y obtenemos lo siguiente:
``` bash
┌──(kali㉿kali)-[~]
└─$ nc jupiter.challenges.picoctf.org 43522
-------------------------------------------------------------------------------
yzcewnfo xdwd qo uzjw sgne - swdvjdcyu_qo_y_zmdw_gnbphn_zesbnjcwns
-------------------------------------------------------------------------------
td tdwd czf bjyx bzwd fxnc n vjnwfdw zs nc xzjw zjf zs zjw oxqi fqgg td ont xdw oqck, nch fxdc q jchdwofzzh szw fxd sqwof fqbd txnf tno bdncf pu n oxqi szjchdwqce qc fxd odn.  q bjof nykcztgdhed q xnh xnwhgu dudo fz gzzk ji txdc fxd odnbdc fzgh bd oxd tno oqckqce; szw swzb fxd bzbdcf fxnf fxdu wnfxdw ijf bd qcfz fxd pznf fxnc fxnf q bqexf pd onqh fz ez qc, bu xdnwf tno, no qf tdwd, hdnh tqfxqc bd, inwfgu tqfx swqexf, inwfgu tqfx xzwwzw zs bqch, nch fxd fxzjexfo zs txnf tno udf pdszwd bd.

                                                                                                                                                            
┌──(kali㉿kali)-[~]
└─$ 
``` 

- Con ayuda de  [alphabetic Substitution](https://www.dcode.fr/monoalphabetic-substitution) encontramos la Bandera al aplicar 
``` bash
------------------------------------------------------------------------------- CONGRATS HERE IS YOUR FLAG - FREQUENCY_IS_C_OVER_LAMBDA_OGFMAUNRAF ------------------------------------------------------------------------------- WE WERE NOT MUCH MORE THAN A QUARTER OF AN HOUR OUT OF OUR SHIP TILL WE SAW HER SINK, AND THEN I UNDERSTOOD FOR THE FIRST TIME WHAT WAS MEANT BY A SHIP FOUNDERING IN THE SEA. I MUST ACKNOWLEDGE I HAD HARDLY EYES TO LOOK UP WHEN THE SEAMEN TOLD ME SHE WAS SINKING; FOR FROM THE MOMENT THAT THEY RATHER PUT ME INTO THE BOAT THAN THAT I MIGHT BE SAID TO GO IN, MY HEART WAS, AS IT WERE, DEAD WITHIN ME, PARTLY WITH FRIGHT, PARTLY WITH HORROR OF MIND, AND THE THOUGHTS OF WHAT WAS YET BEFORE ME.
```

## Bandera
FREQUENCY_IS_C_OVER_LAMBDA_OGFMAUNRAF

## Referencias
-  [alphabetic Substitution](https://www.dcode.fr/monoalphabetic-substitution)

