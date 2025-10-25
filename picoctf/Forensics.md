# 1. Trivial Flag Transfer Protocol

> use of wireshark software

## Solution:

- we analyze the network and find that there is TFTP files. we extract this files since it was also a hint from the challenge name. from the extracted files there is a .deb file from which we find out there is steghide being used since that is also present in the network. we decypher the text content using ROT13 and find the key phrase. we then use steghide to extract data from the three pictures

```bash
rishi@Rishi-omen-linux:~/Downloads$ steghide extract -sf picture1.bmp
Enter passphrase: 
steghide: could not extract any data with that passphrase!
rishi@Rishi-omen-linux:~/Downloads$ steghide extract -sf picture2.bmp
Enter passphrase: 
steghide: could not extract any data with that passphrase!
rishi@Rishi-omen-linux:~/Downloads$ steghide extract -sf picture3.bmp
Enter passphrase: 
wrote extracted data to "flag.txt".
rishi@Rishi-omen-linux:~/Downloads$ cat flag.txt
picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}

```

## Flag:

```
picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}
```

## Concepts learnt:

- we can use wireshark to analyze network traffic of a particular file. Steghide is a command-line program used for steganography (which is hiding data in form of image)

## Notes:

- TFTP is one of many protocol and wireshark has feature to extract data from a particular protocol. we use this feature to extract our data from TFTP particularly

## Resources:

- google for steghide commands


***

# 2.  tunn3l v1s10n

> HexEditor software

## Solution:

- since the file does not open normally, we open it in a hex editor to find its type. from there we find it is a bitmap and change its extension to a .bmp file. the file still does not open because it seems to be corrupted. we compare the hexmapping with a normal image and fix the values in our file which seems to be different from normal. this lets us open the image but its not in the correct size and therefore hides the flag. to solve this we find out which hex value controls the dimension of the image and change that to increase the image length and find out the flag which was hidden on top of the image.

## Flag:

```
picoCTF{qu1t3_a_v13w_2020}
```

## Concepts learnt:

- we can use HexEditors to analyze a file type and change its values to try to uncorrupt it

## Notes:

- when hex mapping of a file starts with BM it means its a bit map and the extension for those files are .bmp

## Resources:

- googled ways to interact with a corrupted file and used a hex editor to uncorrupt the files


***

# 3. m00nwalk

> picture in audio

## Solution:

- we use sonic visualizer to analyse the audio and see that it is an SSTV image broadcasting (which is also what the hint says)

```
$ git clone https://github.com/colaclanth/sstv.git
$ python setup.py install
$ sstv -d audio_file.wav -o result.png
```

## Flag:

```
picoCTF{beep_boop_im_in_Space}
```

## Concepts learnt:

- Pictures can be hidden in form of audio

## Notes:

- sonic visualizer to analyse audio and online decryption tools

## Resources:

- online sstv decoder (https://github.com/colaclanth/sstv)

***