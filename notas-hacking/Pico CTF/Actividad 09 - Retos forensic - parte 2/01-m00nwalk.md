# m00nwalk



## Descripción
Decode this [message](https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav) from the moon.

## Pistas
- How did pictures from the moon landing get sent back to Earth?
- What is the CMU mascot?, that might help select a RX option

## Solución

- El reto nos da un audio el cual tenemos que decodificar la bandera
- Se clona un repositorio de git para poder decodificar 
- Se Instala la herrameinta python3 setup.py
- Entramos al las carpetas donde se encuentra el audio
- Se convierte de audio a .png
- Se abre el nuevo archivo .png
- Se  obtiene la bandera:
``` bash
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ ls
message.wav  
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ file message.wav  
message.wav: RIFF (little-endian) data, WAVE audio, Microsoft PCM, 16 bit, mono 48000 Hz
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ open message.wav  
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ cd /opt                
                                                                                                                                                            
┌──(kali㉿kali)-[/opt]
└─$ sudo git clone https://github.com/colaclanth/sstv.git
Clonando en 'sstv'...
remote: Enumerating objects: 221, done.
remote: Total 221 (delta 0), reused 0 (delta 0), pack-reused 221
Recibiendo objetos: 100% (221/221), 1.01 MiB | 1.29 MiB/s, listo.
Resolviendo deltas: 100% (140/140), listo.
                                                                                                                                                            
┌──(kali㉿kali)-[/opt]
└─$ cd sstv/                                             
                                                                                                                                                            
┌──(kali㉿kali)-[/opt/sstv]
└─$ python3 setup.py install
running install
/usr/lib/python3/dist-packages/setuptools/command/install.py:34: SetuptoolsDeprecationWarning: setup.py install is deprecated. Use build and pip and other standards-based tools.
  warnings.warn(
/usr/lib/python3/dist-packages/setuptools/command/easy_install.py:146: EasyInstallDeprecationWarning: easy_install command is deprecated. Use build and pip and other standards-based tools.
  warnings.warn(
error: can't create or remove files in install directory

The following error occurred while trying to add or remove files in the
installation directory:

    [Errno 13] Permission denied: '/usr/local/lib/python3.10/dist-packages/test-easy-install-66409.write-test'

The installation directory you specified (via --install-dir, --prefix, or
the distutils default setting) was:

    /usr/local/lib/python3.10/dist-packages/

Perhaps your account does not have write access to this directory?  If the
installation directory is a system-owned directory, you may need to sign in
as the administrator or "root" account.  If you do not have administrative
access to this machine, you may wish to choose a different installation
directory, preferably one that is listed in your PYTHONPATH environment
variable.

For information on other options, you may wish to consult the
documentation at:

  https://setuptools.pypa.io/en/latest/deprecated/easy_install.html

Please make the appropriate changes for your system and try again.

                                                                                                                                                            
┌──(kali㉿kali)-[/opt/sstv]
└─$ sudo python3 setup.py install                        
running install
/usr/lib/python3/dist-packages/setuptools/command/install.py:34: SetuptoolsDeprecationWarning: setup.py install is deprecated. Use build and pip and other standards-based tools.
  warnings.warn(
/usr/lib/python3/dist-packages/setuptools/command/easy_install.py:146: EasyInstallDeprecationWarning: easy_install command is deprecated. Use build and pip and other standards-based tools.
  warnings.warn(
/usr/lib/python3/dist-packages/pkg_resources/__init__.py:123: PkgResourcesDeprecationWarning: 2.3.0-nmu1-b1 is an invalid version and will not be supported in a future release
  warnings.warn(
running bdist_egg
running egg_info
creating sstv.egg-info
writing sstv.egg-info/PKG-INFO
writing dependency_links to sstv.egg-info/dependency_links.txt
writing entry points to sstv.egg-info/entry_points.txt
writing requirements to sstv.egg-info/requires.txt
writing top-level names to sstv.egg-info/top_level.txt
writing manifest file 'sstv.egg-info/SOURCES.txt'
reading manifest file 'sstv.egg-info/SOURCES.txt'
adding license file 'LICENSE'
writing manifest file 'sstv.egg-info/SOURCES.txt'
installing library code to build/bdist.linux-x86_64/egg
running install_lib
running build_py
creating build
creating build/lib
creating build/lib/sstv
copying sstv/spec.py -> build/lib/sstv
copying sstv/decode.py -> build/lib/sstv
copying sstv/__init__.py -> build/lib/sstv
copying sstv/__main__.py -> build/lib/sstv
copying sstv/common.py -> build/lib/sstv
copying sstv/command.py -> build/lib/sstv
creating build/bdist.linux-x86_64
creating build/bdist.linux-x86_64/egg
creating build/bdist.linux-x86_64/egg/sstv
copying build/lib/sstv/spec.py -> build/bdist.linux-x86_64/egg/sstv
copying build/lib/sstv/decode.py -> build/bdist.linux-x86_64/egg/sstv
copying build/lib/sstv/__init__.py -> build/bdist.linux-x86_64/egg/sstv
copying build/lib/sstv/__main__.py -> build/bdist.linux-x86_64/egg/sstv
copying build/lib/sstv/common.py -> build/bdist.linux-x86_64/egg/sstv
copying build/lib/sstv/command.py -> build/bdist.linux-x86_64/egg/sstv
byte-compiling build/bdist.linux-x86_64/egg/sstv/spec.py to spec.cpython-310.pyc
byte-compiling build/bdist.linux-x86_64/egg/sstv/decode.py to decode.cpython-310.pyc
byte-compiling build/bdist.linux-x86_64/egg/sstv/__init__.py to __init__.cpython-310.pyc
byte-compiling build/bdist.linux-x86_64/egg/sstv/__main__.py to __main__.cpython-310.pyc
byte-compiling build/bdist.linux-x86_64/egg/sstv/common.py to common.cpython-310.pyc
byte-compiling build/bdist.linux-x86_64/egg/sstv/command.py to command.cpython-310.pyc
creating build/bdist.linux-x86_64/egg/EGG-INFO
copying sstv.egg-info/PKG-INFO -> build/bdist.linux-x86_64/egg/EGG-INFO
copying sstv.egg-info/SOURCES.txt -> build/bdist.linux-x86_64/egg/EGG-INFO
copying sstv.egg-info/dependency_links.txt -> build/bdist.linux-x86_64/egg/EGG-INFO
copying sstv.egg-info/entry_points.txt -> build/bdist.linux-x86_64/egg/EGG-INFO
copying sstv.egg-info/requires.txt -> build/bdist.linux-x86_64/egg/EGG-INFO
copying sstv.egg-info/top_level.txt -> build/bdist.linux-x86_64/egg/EGG-INFO
zip_safe flag not set; analyzing archive contents...
creating dist
creating 'dist/sstv-0.1-py3.10.egg' and adding 'build/bdist.linux-x86_64/egg' to it
removing 'build/bdist.linux-x86_64/egg' (and everything under it)
Processing sstv-0.1-py3.10.egg
Copying sstv-0.1-py3.10.egg to /usr/local/lib/python3.10/dist-packages
Adding sstv 0.1 to easy-install.pth file
Installing sstv script to /usr/local/bin

Installed /usr/local/lib/python3.10/dist-packages/sstv-0.1-py3.10.egg
Processing dependencies for sstv==0.1
Searching for PySoundFile
Reading https://pypi.org/simple/PySoundFile/
/usr/lib/python3/dist-packages/pkg_resources/__init__.py:123: PkgResourcesDeprecationWarning:  is an invalid version and will not be supported in a future release
  warnings.warn(
Downloading https://files.pythonhosted.org/packages/2a/b3/0b871e5fd31b9a8e54b4ee359384e705a1ca1e2870706d2f081dc7cc1693/PySoundFile-0.9.0.post1-py2.py3-none-any.whl#sha256=db14f84f4af1910f54766cf0c0f19d52414fa80aa0e11cb338b5614946f39947
Best match: PySoundFile 0.9.0.post1
Processing PySoundFile-0.9.0.post1-py2.py3-none-any.whl
Installing PySoundFile-0.9.0.post1-py2.py3-none-any.whl to /usr/local/lib/python3.10/dist-packages
Adding PySoundFile 0.9.0.post1 to easy-install.pth file

Installed /usr/local/lib/python3.10/dist-packages/PySoundFile-0.9.0.post1-py3.10.egg
Searching for SciPy==1.8.1
Best match: SciPy 1.8.1
Adding SciPy 1.8.1 to easy-install.pth file

Using /usr/lib/python3/dist-packages
Searching for numpy==1.21.5
Best match: numpy 1.21.5
Adding numpy 1.21.5 to easy-install.pth file
Installing f2py script to /usr/local/bin
Installing f2py3 script to /usr/local/bin
Installing f2py3.10 script to /usr/local/bin

Using /usr/lib/python3/dist-packages
Searching for Pillow==9.2.0
Best match: Pillow 9.2.0
Adding Pillow 9.2.0 to easy-install.pth file

Using /usr/lib/python3/dist-packages
Searching for cffi==1.15.1
Best match: cffi 1.15.1
Adding cffi 1.15.1 to easy-install.pth file

Using /usr/lib/python3/dist-packages
Finished processing dependencies for sstv==0.1
                                                                                                                                                            
┌──(kali㉿kali)-[/opt/sstv]
└─$ cd sstv 
                                                                                                                                                            
┌──(kali㉿kali)-[/opt/sstv/sstv]
└─$ sstv --help
usage: sstv [-h] [-d AUDIO_FILE] [-o OUTPUT_FILE] [-s SKIP] [-V] [--list-modes] [--list-audio-formats] [--list-image-formats]

options:
  -h, --help            show this help message and exit
  -d AUDIO_FILE, --decode AUDIO_FILE
                        decode SSTV audio file
  -o OUTPUT_FILE, --output OUTPUT_FILE
                        save output image to custom location
  -s SKIP, --skip SKIP  time in seconds to start decoding signal at
  -V, --version         show program's version number and exit
  --list-modes          list supported SSTV modes
  --list-audio-formats  list supported audio file formats
  --list-image-formats  list supported image file formats

examples:
  Decode local SSTV audio file named 'audio.ogg' to 'result.png':
    $ sstv -d audio.ogg

  Decode SSTV audio file in /tmp to './image.jpg':
    $ sstv -d /tmp/signal.wav -o ./image.jpg

  Start decoding SSTV signal at 50.5 seconds into the audio
    $ sstv -d audio.ogg -s 50.50
                                                                                                                                                            
┌──(kali㉿kali)-[/opt/sstv/sstv]
└─$ cd -                
/opt/sstv
                                                                                                                                                            
┌──(kali㉿kali)-[/opt/sstv]
└─$ cd  
                                                                                                                                                            
┌──(kali㉿kali)-[~]
└─$ cd 
                                                                                                                                                            
┌──(kali㉿kali)-[~]
└─$ cd Descargas 
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas]
└─$ cd Forensic 
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ sstv -d message.wav -o result.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...                         [####################################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ ls
buildings.png  capture.pcap  flag.png  garden.jpg  message.wav  pico_img.png  result.png
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ open result.png 
                                                                                                                                                            
┌──(kali㉿kali)-[~/Descargas/Forensic]
└─$ 

```

## Bandera
picoCTF{beep_boop_im_in_space}

## Notas adicionales
| Comando | Descripción |
|------ | -------------- |
| sstv |decodifica audios a formato .png |


## Referencias
- [SSTV Decoder](https://github.com/colaclanth/sstv)

