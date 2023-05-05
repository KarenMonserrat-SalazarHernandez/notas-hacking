# Ready Gladiator 0




## Descripción
Can you make a CoreWars warrior that always loses, no ties? Your opponent is the Imp. The source is available [here](https://artifacts.picoctf.net/c/309/imp.red). If you wanted to pit the Imp against himself, you could download the Imp and connect to the CoreWars server like this: `nc saturn.picoctf.net 58570 < imp.red`

## Pistas
- CoreWars is a well-established game with a lot of docs and strategy
- Experiment with input to the CoreWars handler or create a self-defeating bot

## Solución

``` bash
┌──(kali㉿kali)-[~/Descargas]
└─$ cat imp.red 
;redcode
;name Imp Ex
;assert 1
mov 0, 1
end
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas]
└─$ nc saturn.picoctf.net 58570 
Submit your warrior: (enter 'end' when done)



xd
xd
end
end
Warrior1:
xd
endxd
xd
end
end
Warrior1:
xd
Warrior1:

xd
xd
end

Warning:
        Missing ';assert'. Warrior may not work with the current setting
Warning:
        No instructions
Number of warnings: 2

Rounds: 100
Warrior 1 wins: 0
Warrior 2 wins: 100
Ties: 0
You did it!
picoCTF{h3r0_t0_z3r0_4m1r1gh7_f1e207c4}
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas]
└─$ 
``` 

## Bandera
picoCTF{h3r0_t0_z3r0_4m1r1gh7_f1e207c4}