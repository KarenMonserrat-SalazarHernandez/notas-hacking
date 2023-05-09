# Safe Opener 2  - picoCTF 2023





## Descripción
What can you do with this file?I forgot the key to my safe but this [file](https://artifacts.picoctf.net/c/288/SafeOpener.class) is supposed to help me with retrieving the lost key. Can you help me unlock my safe?

## Pistas
- Download and try to decompile the file.

## Solución

``` bash
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ ls
SafeOpener.class  SafeOpener.class_source_from_Procyon.zip
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ file SafeOpener.class
SafeOpener.class: compiled Java class data, version 52.0 (Java 1.8)
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ cat SafeOpener.class   
����4�
CDE     FG
H
I
JL      FN
OP
Q
RS
.T
OU
VW
X
Y
[
]
R`ab<init>()VCodeLineNumberTableLocalVariableTablethis
                                                      LSafeOpener;main([Ljava/lang/String;)VisOpenZargs[Ljava/lang/Stringkeyboard▒Ljava/io/BufferedReader;encodercEncoder
              InnerClasses▒Ljava/util/Base64$Encoder;
StackMapTable*Dcdang/String;keyiI
ExceptionsopenSafe(Ljava/lang/String;)password
SourceFileSafeOpener.java
                         java/io/BufferedReaderjava/io/InputStreamReaderf
                                                                         gh
                                                                           i
                                                                            jk
                                                                              lm
                                                                                noEnter password for the safe: p
                                                                                                                qr
                                                                                                                  std
                                                                                                                     uv
                                                                                                                       wx
                                                                                                                         yr
                                                                                                                           >?java/lang/StringBuilder
You have  
          z{
            z| attempt(s) left
                              }t,picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_5bfbd6f1}
                                                                             ~
                                                                              Sesame openPassword is incorrect

SafeOpenerjava/lang/Object▒java/util/Base64$Encoderjava/lang/Stringjava/io/IOExceptionjava/lang/SysteminLjava/io/InputStream;▒(Ljava/io/InputStream;)V(Ljava/io/Reader;)Vjava/util/Base64
getEncoder()Ljava/util/Base64$Encoder;outLjava/io/PrintStream;java/io/PrintStreamprint(Ljava/lang/String;)readLine()Ljava/lang/StringgetBytes()[BencodeToString([B)Ljava/lang/String;printlnappend-(Ljava/lang/String;)Ljava/lang/StringBuilder;(I)Ljava/lang/StringBuildertoStringequals(Ljava/lang/Object;)Z! /*��!"
#$      %& <x�Y�Y���L�:6�T�
�
 +�
�.4>EKPq▒���HK,'�!▒!f+,b-1_23[43 X567� 89:;;�V<=        >? u▒L*+��
                    "#&'"@323�;AB0
.J/                                                                                                                                                                
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ 


``` 

``` bash
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ ls
SafeOpener.class  SafeOpener.class_source_from_Procyon  SafeOpener.class_source_from_Procyon.zip
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing]
└─$ cd SafeOpener.class_source_from_Procyon
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing/SafeOpener.class_source_from_Procyon]
└─$ ls
SafeOpener.java
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing/SafeOpener.class_source_from_Procyon]
└─$ cat SafeOpener.java                    
import java.io.IOException;
import java.util.Base64;
import java.io.Reader;
import java.io.BufferedReader;
import java.io.InputStreamReader;

// 
// Decompiled by Procyon v0.5.36
// 

public class SafeOpener
{
    public static void main(final String[] args) throws IOException {
        final BufferedReader keyboard = new BufferedReader(new InputStreamReader(System.in));
        final Base64.Encoder encoder = Base64.getEncoder();
        String encodedkey = "";
        String key = "";
        for (int i = 0; i < 3; ++i) {
            System.out.print("Enter password for the safe: ");
            key = keyboard.readLine();
            encodedkey = encoder.encodeToString(key.getBytes());
            System.out.println(encodedkey);
            final boolean isOpen = openSafe(encodedkey);
            if (isOpen) {
                break;
            }
            System.out.println("You have  " + (2 - i) + " attempt(s) left");
        }
    }
    
    public static boolean openSafe(final String password) {
        final String encodedkey = "picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_5bfbd6f1}";
        if (password.equals(encodedkey)) {
            System.out.println("Sesame open");
            return true;
        }
        System.out.println("Password is incorrect\n");
        return false;
    }
}
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Reversing/SafeOpener.class_source_from_Procyon]
└─$ 

```

## Bandera 
picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_5bfbd6f1}

## Referencias
-   [Decompiles](http://www.javadecompilers.com/#)]