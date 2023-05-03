# vault-door-1


## Descripción
This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: [VaultDoor1.java](https://jupiter.challenges.picoctf.org/static/29b91e638ccbd76aaa8c0462d1c64d8d/VaultDoor1.java)

## Pistas
- Look up the charAt() method online.

## Solución

- En el código se encuentra la bandera (3er columna), hay que quitarle todo lo que esta a los lados para dejar unicamente la bandera:
``` bash
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ ls
VaultDoor1.java
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ cat VaultDoor1.java       
import java.util.*;

class VaultDoor1 {
    public static void main(String args[]) {
        VaultDoor1 vaultDoor = new VaultDoor1();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
    }

    // I came up with a more secure way to check the password without putting
    // the password itself in the source code. I think this is going to be
    // UNHACKABLE!! I hope Dr. Evil agrees...
    //
    // -Minion #8728
    public boolean checkPassword(String password) {
        return password.length() == 32 &&
               password.charAt(0)  == 'd' &&
               password.charAt(29) == '3' &&
               password.charAt(4)  == 'r' &&
               password.charAt(2)  == '5' &&
               password.charAt(23) == 'r' &&
               password.charAt(3)  == 'c' &&
               password.charAt(17) == '4' &&
               password.charAt(1)  == '3' &&
               password.charAt(7)  == 'b' &&
               password.charAt(10) == '_' &&
               password.charAt(5)  == '4' &&
               password.charAt(9)  == '3' &&
               password.charAt(11) == 't' &&
               password.charAt(15) == 'c' &&
               password.charAt(8)  == 'l' &&
               password.charAt(12) == 'H' &&
               password.charAt(20) == 'c' &&
               password.charAt(14) == '_' &&
               password.charAt(6)  == 'm' &&
               password.charAt(24) == '5' &&
               password.charAt(18) == 'r' &&
               password.charAt(13) == '3' &&
               password.charAt(19) == '4' &&
               password.charAt(21) == 'T' &&
               password.charAt(16) == 'H' &&
               password.charAt(27) == 'f' &&
               password.charAt(30) == 'b' &&
               password.charAt(25) == '_' &&
               password.charAt(22) == '3' &&
               password.charAt(28) == '6' &&
               password.charAt(26) == 'f' &&
               password.charAt(31) == '0';
    }
}
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ nano flag   
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ nano flag
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ cat flag           
password.length() == 32 &&
               password.charAt(00)  == 'd' &&
               password.charAt(29) == '3' &&
               password.charAt(04)  == 'r' &&
               password.charAt(02)  == '5' &&
               password.charAt(23) == 'r' &&
               password.charAt(03)  == 'c' &&
               password.charAt(17) == '4' &&
               password.charAt(01)  == '3' &&
               password.charAt(07)  == 'b' &&
               password.charAt(10) == '_' &&
               password.charAt(05)  == '4' &&
               password.charAt(09)  == '3' &&
               password.charAt(11) == 't' &&
               password.charAt(15) == 'c' &&
               password.charAt(08)  == 'l' &&
               password.charAt(12) == 'H' &&
               password.charAt(20) == 'c' &&
               password.charAt(14) == '_' &&
               password.charAt(06)  == 'm' &&
               password.charAt(24) == '5' &&
               password.charAt(18) == 'r' &&
               password.charAt(13) == '3' &&
               password.charAt(19) == '4' &&
               password.charAt(21) == 'T' &&
               password.charAt(16) == 'H' &&
               password.charAt(27) == 'f' &&
               password.charAt(30) == 'b' &&
               password.charAt(25) == '_' &&
               password.charAt(22) == '3' &&
               password.charAt(28) == '6' &&
               password.charAt(26) == 'f' &&
               password.charAt(31) == '0'
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ cat flag | sort | awk '{print($3)}'
'd'
'3'
'5'
'c'
'r'
'4'
'm'
'b'
'l'
'3'
'_'
't'
'H'
'3'
'_'
'c'
'H'
'4'
'r'
'4'
'c'
'T'
'3'
'r'
'5'
'_'
'f'
'f'
'6'
'3'
'b'
'0'
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ cat flag | sort | awk '{print($3)}' | tr -d "'"
d
3
5
c
r
4
m
b
l
3
_
t
H
3
_
c
H
4
r
4
c
T
3
r
5
_
f
f
6
3
b
0
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ cat flag | sort | awk '{print($3)}' | tr -d "'" | tr -d "\n"
d35cr4mbl3_tH3_cH4r4cT3r5_ff63b0                                                                                                                                                          
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ ls                    
flag  VaultDoor1.java
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ javac  VaultDoor1.java                                   
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ java VaultDoor1       
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_ff63b0}
Access granted.
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ 


``` 

## Bandera 
picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_ff63b0}

