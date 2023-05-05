# Lookey here



## Descripción
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it.Download the data [here](https://artifacts.picoctf.net/c/124/anthem.flag.txt).

## Pistas
- Download the file and search for the flag based on the known prefix.

## Solución

- Vemos el contenido del archivo 
- Con el comando cat y grep filtramos la parte inicial de la bandera "picoCTF"
``` bash
                                                                                                                                                           
┌──(kali㉿kali)-[~/Descargas/Segundo Parcial]
└─$ ls
anthem.flag.txt  cat.jpg  drawing.flag.svg  shark1.pcapng
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Segundo Parcial]
└─$ cat anthem.flag.txt                                                                           
      ANTHEM

      by Ayn Rand


        CONTENTS

         PART ONE

         PART TWO

         PART THREE

         PART FOUR

         PART FIVE

         PART SIX

         PART SEVEN

         PART EIGHT

         PART NINE

         PART TEN

         PART ELEVEN

         PART TWELVE




      PART ONE

      It is a sin to write this. It is a sin to think words no others
      think and to put them down upon a paper no others are to see. It
      is base and evil. It is as if we were speaking alone to no ears
      but our own. And we know well that there is no transgression
      blacker than to do or think alone. We have broken the laws. The
      laws say that men may not write unless the Council of Vocations
      bid them so. May we be forgiven!

      But this is not the only sin upon us. We have committed a greater
      crime, and for this crime there is no name. What punishment
      awaits us if it be discovered we know not, for no such crime has
      come in the memory of men and there are no laws to provide for
      it.

      It is dark here. The flame of the candle stands still in the air.
      Nothing moves in this tunnel save our hand on the paper. We are
      alone here under the earth. It is a fearful word, alone. The laws
      say that none among men may be alone, ever and at any time, for
      this is the great transgression and the root of all evil. But we
      have broken many laws. And now there is nothing here save our one
      body, and it is strange to see only two legs stretched on the
      ground, and on the wall before us the shadow of our one head.

      The walls are cracked and water runs upon them in thin threads
      without sound, black and glistening as blood. We stole the candle
      from the larder of the Home of the Street Sweepers. We shall be
      sentenced to ten years in the Palace of Corrective Detention if
      it be discovered. But this matters not. It matters only that the
      light is precious and we should not waste it to write when we
      need it for that work which is our crime. Nothing matters save
      the work, our secret, our evil, our precious work. Still, we must
      also write, for—may the Council have mercy upon us!—we wish to
      speak for once to no ears but our own.

      Our name is Equality 7-2521, as it is written on the iron
      bracelet which all men wear on their left wrists with their names
      upon it. We are twenty-one years old. We are six feet tall, and
      this is a burden, for there are not many men who are six feet
      tall. Ever have the Teachers and the Leaders pointed to us and
      frowned and said:

      “There is evil in your bones, Equality 7-2521, for your body has
      grown beyond the bodies of your brothers.” But we cannot change
      our bones nor our body.

      We were born with a curse. It has always driven us to thoughts
      which are forbidden. It has always given us wishes which men may
      not wish. We know that we are evil, but there is no will in us
      and no power to resist it. This is our wonder and our secret
      fear, that we know and do not resist.

      We strive to be like all our brother men, for all men must be
      alike. Over the portals of the Palace of the World Council, there
      are words cut in the marble, which we repeat to ourselves
      whenever we are tempted:

  “WE ARE ONE IN ALL AND ALL IN ONE.
  THERE ARE NO MEN BUT ONLY THE GREAT _WE_,
  ONE, INDIVISIBLE AND FOREVER.”
  .
  .
  .

      These things help us in our work. We do not understand them, but
      we think that the men of picoCTF{gr3p_15_@w3s0m3_4c479940}
our
    .
    .
    .

      Here on this mountain, I and my sons and my chosen friends shall
      build our new land and our fort. And it will become as the heart
      of the earth, lost and hidden at first, but beating, beating
      louder each day. And word of it will reach every corner of the
      earth. And the roads of the world will become as veins which will
      carry the best of the world’s blood to my threshold. And all my
      brothers, and the Councils of my brothers, will hear of it, but
      they will be impotent against me. And the day will come when I
      shall break all the chains of the earth, and raze the cities of
      the enslaved, and my home will become the capital of a world
      where each man will be free to exist for his own sake.

      For the coming of that day shall I fight, I and my sons and my
      chosen friends. For the freedom of Man. For his rights. For his
      life. For his honor.

      And here, over the portals of my fort, I shall cut in the stone
      the word which is to be my beacon and my banner. The word which
      will not die, should we all perish in battle. The word which can
      never die on this earth, for it is the heart of it and the
      meaning and the glory.

      The sacred word:

      EGO



                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Segundo Parcial]
└─$ cat anthem.flag.txt | grep picoCTF
      we think that the men of picoCTF{gr3p_15_@w3s0m3_4c479940}
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Segundo Parcial]
└─$ 

```

- Con la filtración encontramos la bandera.

## Bandera
picoCTF{gr3p_15_@w3s0m3_4c479940}
