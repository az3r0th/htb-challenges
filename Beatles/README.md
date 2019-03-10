1.Extract the beatles.zip with password "hackthebox"<br>
2.You will find two extracted <br>
	  a. m3ss@g#_f0r_pAuL.txt<br>
	  b. BAND.zip<br>
3.Use ROT13 on m3ss@g#_f0r_pAuL.txt. you will hint for password of BAND.zip.<br>
4.Use fcrackzip to crack the zip , command is given below <br>
    - fcrackzip -v -u -l 4 4 BAND.zip <br>
 	  it will take few minutes <br>
5.After You get the password for zip , extract the zip and u will found BAND.JPG<br>
6.Use stegcracker on BAND.JPG and get the BAND.JPG.out.<br>
		i created my own wordlist which contain few words which is related to "The Beatles". You can get the <a href="https://drive.google.com/file/d/1tM17c5Peg4nyna7riaNc8tTACT9wqB_q/view?usp=sharing"> wordlist</a>
	  <br>- stegcracker BAND.JPG wordlist.txt<br>
7.After getting output file from band.jpg. use the command followed below <br>
	  - strings BAND.JPG.out | awk 'length($0)> 150'
	  <br>you will get a base64 encoded string. use this command to decode or you can use online base64 decoder <br>
	  - echo "base64_encode_string_that_you_got_in_the_last_step" | base64 --decode<br>
8.You will get the flag in the format - 'HTB{*********}'



