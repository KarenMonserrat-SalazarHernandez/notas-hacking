# vault-door-training


## Descripción
Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility. The source code for the training vault is here: [VaultDoorTraining.java](https://jupiter.challenges.picoctf.org/static/1afdf83322ee9c0040f8e3a3c047e18b/VaultDoorTraining.java)

## Pistas
- The password is revealed in the program's source code.

## Solución

- Dentro del código se encuantra la bandera, la cuál se valida con el compildor de java:
``` bash
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ ls
VaultDoorTraining.java
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ cat VaultDoorTraining.java 
import java.util.*;

class VaultDoorTraining {
    public static void main(String args[]) {
        VaultDoorTraining vaultDoor = new VaultDoorTraining();
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

    // The password is below. Is it safe to put the password in the source code?
    // What if somebody stole our source code? Then they would know what our
    // password is. Hmm... I will think of some ways to improve the security
    // on the other doors.
    //
    // -Minion #9567
    public boolean checkPassword(String password) {
        return password.equals("w4rm1ng_Up_w1tH_jAv4_eec0716b713");
    }
}
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ javac VaultDoorTraining.java 
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ ls
VaultDoorTraining.class  VaultDoorTraining.java
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ java VaultDoorTraining      
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{123}
Access denied!
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ java VaultDoorTraining      
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{w4rm1ng_Up_w1tH_jAv4_eec0716b713}
Access granted.
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ 


``` 

## Bandera 
picoCTF{w4rm1ng_Up_w1tH_jAv4_eec0716b713}

