# Lag-and-Crash-Interpoly-CTF-2022
Writeups on some of the challenges I solved in Lag and Crash Interpoly CTF 2022

# Table of Contents
* [Forensics](https://github.com/ZYChua02/Lag-and-Crash-Interpoly-CTF-2022#forensics)
  * [Found Disk](https://github.com/ZYChua02/Lag-and-Crash-Interpoly-CTF-2022#found-disk)
* [Crypto](https://github.com/ZYChua02/Lag-and-Crash-Interpoly-CTF-2022#crypto)
  * [Lines, Lines, LINES](https://github.com/ZYChua02/Lag-and-Crash-Interpoly-CTF-2022#lines-lines-lines)
* [OSINT](https://github.com/ZYChua02/Lag-and-Crash-Interpoly-CTF-2022#osint)
  * [Div0](https://github.com/ZYChua02/Lag-and-Crash-Interpoly-CTF-2022#div0)
* [Personal thoughts on the CTF](https://github.com/ZYChua02/Lag-and-Crash-Interpoly-CTF-2022#personal-thoughts-on-the-ctf)
# Forensics
## Found Disk
## Challenge Description
A group of citizens were kidnapped, with only a file left behind... could you find out who did it?
</br>
</br>
File: [disk.docx](https://github.com/ZYChua02/Lag-and-Crash-Interpoly-CTF-2022/blob/main/Files%20for%20challenges/disk.docx)
## Approach
To start the challenge, I opened the file that was provided in Microsoft Word but was met with an error.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/160783819-62ff5404-756a-4412-8276-606bfaaf4b02.png)
</br>
</br>
I reliased that the file might not be a word file, hence I used the file command to determine what file it was. Turns out it was actually an audio file.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/160784883-ffd1320d-4598-4743-94e3-933a4836bde8.png)
</br>
</br>
I changed the file extension from .docx to .wav, and then used dcode spectral analysis to see if I could find anything. When using spectral anlaysis, I managed to find a bitly link.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/160786715-9c0b74a0-578b-4484-849b-b30b892e90c2.png)
</br>
</br>
I entered bitly link that was found and was led to an image file named miXtapefORmusic.jpg.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/160787650-d0cffe09-fb41-4855-9c27-8e4433f19ed5.png)
</br>
</br>
I downloaded the image and use cyberchef to extract the exif data and found Artist and Ownername.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/160788067-abe7bfdc-414c-40db-9a3a-70d452e1cfd6.png)
</br>
</br>
I was not sure how to continue on from there, so I took a short break and came back to the challenge after I realised that the naming of the image file miXtapefORmusic.jpg was actually a hint to XOR the Artist and Ownername. I decided to use a XOR calculator online to quickly derive the value.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/160788705-331a6f6b-b457-43cc-86c6-dd9816698190.png)
</br>
</br>
Knowing that it was a hex value, I decided to use cyberchef again and managed to find the flag by converting the hex value.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/160789183-fd83ff48-45c5-4bed-8836-982b741f6d1d.png)
## The flag
`LNC2022{Mu5icM4n1sB4ck}`
# Crypto
## Lines, Lines, LINES
## Challenge Description
Commisoner Gordon sent me this weird picture found at the scene of a crime. What does it even mean?
</br>
</br>
Submit flag in all lowercase e.g. LNC2022{flagoeshere}
</br>
</br>
File: [lines.png](https://github.com/ZYChua02/Lag-and-Crash-Interpoly-CTF-2022/blob/main/Files%20for%20challenges/lines.png)
## Approach
As I did not know what cipher it was, I decided to just google "lines cipher" first to see what I could find. While scrolling through the google image results, I came across this image which seemed like it was the key to the cipher.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/160790120-fccda95c-13b4-46f7-8563-087e17217563.png)
</br>
</br>
I did further research on it and found that it was actually the Ogham Alphabet. I use the image that I found previously and decoded it by hand. I also used an Ogham Transliterator to compare whether I decoded it correctly because on my first few attempts, I got the flag wrong.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/160792175-1d36aebe-2c3a-4526-9309-740af10d9e63.png)
## The flag
`LNC2022{orangengreen}`
# OSINT
## Div0
## Challenge Description
NOTE: Flag may not be in flag format, input flag as LNC2022{FLAG}
## Approach
I attended the sharing session by div0 but initially was also unable to get the flag. Then I remembered during the sharing, there was actually a flag icon in the slides.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/160793290-0971bbfc-8708-40cf-b4c0-8e4f9367450a.png)
</br>
</br>
After thinking about it for a while, I reliased that the flag could be actually the link of the cyberleague website. I proceeded to do a google search to find the link and input it as the flag as a good guess. To my surprise however it was actually the flag.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/160794405-6f0f7216-7342-43c7-a212-0d9a2b9477ae.png)
## The flag
`LNC2022{cyberleague.co}`
# Personal thoughts on the CTF
It has been an fun CTF I would say, just doing my challenges in my own time actually allowed me to solve more challenges. This allowed me to really explore and just use the tools and knowledge that I had from participating in other CTFs and applying it to the various challenges. Overall, I would say that this CTF was actually easier than the first Interpoly CTF and the difficulty level was what I expected for a CTF meant for tertiary students.
</br>
</br>
Challenges that I solved:
</br>
</br>
<img width="748" alt="image" src="https://user-images.githubusercontent.com/65858555/160087060-e073f635-8ebc-4737-a269-2ffa7cb265a6.png">

