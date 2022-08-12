---
description: >-
  10 Aug 2022 - 12 Aug 2022 | Rank 116th out of 954th | 1500 Points | Solved 10
  Questions
---

# T3N4CI0US CTF 2022

## Crypto

<details>

<summary>french</summary>

**Points: 100**

{% code title="Description" %}
```
French Ciper

V3Y4GK0FW{EccrEs_Xpvtj_Icdc}
```
{% endcode %}

First we use [https://www.dcode.fr/cipher-identifier](https://www.dcode.fr/cipher-identifier) to identified what cipher is that

![](https://lh3.googleusercontent.com/9A-5\_vJGA-qfLw-RCYK3xQhmEO5NW96qhIRABjyxa45MNPUCP8PQ9W3Vi1Nm1EEWLM0R2ptD0sG4X36yNMF3L0NuMotHD98Xd7BzHcCS0CfMe9PAPqBlnx-RIw98YKBqZ0yatm-3S0GHqkPrB62Ccjs)

The highest result show that it is **Vignere Ciphere** so we use [https://www.dcode.fr/vigenere-cipher](https://www.dcode.fr/vigenere-cipher) to decrypt it.

Knowing that the first word before curly bracket is <mark style="color:yellow;">`V3Y4GK0FW`</mark>`{EccrEs_Xpvtj_Icdc}` is equals to <mark style="color:yellow;">`T3N4CI0US`</mark>`{EccrEs_Xpvtj_Icdc}` we already know the plain text word of the cipher.

![](https://lh3.googleusercontent.com/M5pMWbffkmjY9TEaCXqu9j9Vi341MSIYMRicFSBKCjtjGmMvuR9eBlUyPDhSpGWptqZ\_Hk2kr8X11hpmJEPWrVYM-1NlI4e7uQsXeXIY3cLha78a4fl8a5C3StFyiKqz92JvQinWhbJbOrxN9yTomP0)

So using the features in [dcode](https://www.dcode.fr/vigenere-cipher) **** we enter the plain text word that we sure know will be inside the cipher and remove the numbers because it can only accept letter.

**Flag:** <mark style="background-color:yellow;">T3N4CI0US{CrypTo\_Verry\_Easy}</mark>

</details>

<details>

<summary>Before Porta arrives at the port!</summary>

**Points: 200**

{% code title="Description" %}
```
Before Porta arrives at the port! Decryption is required to interpret this..

...-- -. ....- -.-. .. ----- ..- ... # --- .--- .- -.. .-.. -.. ..--.- ..- ..--.- .--. -.-- .--. ..--.- ...- ..--.- . ..-. --. --.. -..- --.. -..- #

key = cle
```
{% endcode %}

First we use [Morse Code Translator](https://www.boxentriq.com/code-breaking/morse-code) to translate the Morse code into text.

![](https://lh6.googleusercontent.com/tycXKby0RVLtL31N2Q9QHjfTOWqc5NZZLWvPPfbG4Vx3vdN7drMSpUQfmeZ2jWm69fNyU\_nK93wP4YK1vgTfmXotdIkRlw9\_5cP2npZU8alilPDNI3z2JNxVrCxJ211eqrxfdKJKhUcaSd07t\_OYJIM)

The result already shows the word <mark style="color:yellow;">`T3N4CI0US`</mark> so what only left is to **decrypt** the remaining word <mark style="color:yellow;">`OJADLD_U_PYP_V_EFGZXZX`</mark> using [Porta Cipher](https://md5decrypt.net/en/Porta-cipher/)

![](https://lh6.googleusercontent.com/wlbN9ZZpt54p3vGr3X-BxRGcIaWIZaIWmL-ZFAthlzcke5EWHAirLJ\_EnFwuHgQR-TysTIGXMRZyfMk\_U7oPLF\_BcZcsZGyxQ-iqWJ8AxgrYPTEBai-SW5jy-CFKVxDnUVu0CVArFaAM1RM9ZTVu6ZY)

**Flag:** <mark style="background-color:yellow;">T3N4CI0US{CRYPTO\_I\_HAD\_A\_PROBLEM}</mark>

</details>

<details>

<summary>ro</summary>

**Points: 200**

{% code title="Description" %}
```
[ W E = 360 ]
   [ S N S = 360 ]
   [ N E W S = ? ]
```
{% endcode %}

We just search the question on the internet and there's a quiz website where it already shows the answer of the equation

![](https://lh5.googleusercontent.com/xqI39SiS4rC0FgXf3oicEAnYeDFMktR2-oQajeYfWrAt9EmpusqEp0CvgLLQNz1Gz7U9Ki-n-xbZE1ZQ6PY7e\_6xQzlr7wjmWHGd\_e-Kxe5FNtKMrDVb8fZLecq-5TTSsQbaLDqHnxgN33l1AJHMzhY)

**Flag:** <mark style="background-color:yellow;">T3N4CI0US{540}</mark>

</details>

<details>

<summary>one</summary>

**Points: 300**

{% code title="Description" %}
```
26s + 8t = 2( == gcd(26,8))
+ 12345 for the correct answer
```
{% endcode %}

The first thing we did is to google the question and we found this [Korean Mathematics Website](https://www.crocus.co.kr/1232) that shows the working steps and answer for the equation above

The answer to the equation is **2** and we just need to + 12345 to get the flag.

**Flag:** <mark style="background-color:yellow;">T3N4CI0US{12347}</mark>

</details>

## Pwn

<details>

<summary>Check Check Check</summary>

**Points: 50**

{% code title="Description" %}
```
mic test one, two, three!!!
IP : 34.64.203.138
Port : 10009
```
{% endcode %}

We started with using the command <mark style="color:yellow;">`nc 34.64.203.138 10009`</mark> on the terminal.&#x20;

Once connected, We listed down the directory with the command <mark style="color:yellow;">`ls`</mark>

![](https://lh6.googleusercontent.com/4Y0qx5fTYcQLjW9umEWzHgpjwcZQe8upOVgBN8GEKfbz2n4\_IiPXN0KiNna8CL2xgrEDtrZYvUZ1AC2A10LpMKowEHMwkn4Q6qCiFxnF-wLpV9qZnls7j4h0pfVq4jRNOrLpwXsbHiZ0azQxjfTyBeA)

As seen in the screenshot above, the list shown from the command seems like a normal linux dir.&#x20;

We move into the home directory to check out the files by using the command <mark style="color:yellow;">`cd home`</mark>.&#x20;

We double checked the current directory just to make sure where we were currently with the command <mark style="color:yellow;">`pwd`</mark>.&#x20;

We listed down the directory back again and found a file named <mark style="color:red;">ctf</mark>.&#x20;

Then move into the file using <mark style="color:yellow;">`cd ctf`</mark> and listed again with <mark style="color:yellow;">`ls`</mark> and we can find 2 files inside which are <mark style="color:red;">flag</mark> and <mark style="color:red;">prob</mark>.&#x20;

Read the file content using <mark style="color:yellow;">`cat flag`</mark> command and captured our first flag.

**Flag:** <mark style="background-color:yellow;">T3N4CI0US{ZG9yb3Jvbmc/ZG9uZz9kaW5nPw}</mark>

</details>

## Reversing

<details>

<summary>Warmup</summary>



</details>

## Web

<details>

<summary>cigarrete</summary>

**Points: 250**

{% code title="Description" %}
```
IP : 34.125.194.164
Port : 49154
```
{% endcode %}

We basically just <mark style="color:yellow;">`nikto -h 34.125.194.164:49154`</mark> to get the flag

![](https://lh6.googleusercontent.com/XaQe7QOkdw5lZu4w7jju4udEUbTedIOdEPwQ6Gy-PUkxpxXfrLhvHVrBqRDo\_xvDX8u3M9y3UFMPUcrM8SzNqxJmmCzv\_ysjTgFs-SZhHxjyigLAvCu0-p29M-IcplenvGEZgx8Dcly9i352ZyOqkzU)

**Flag:** <mark style="background-color:yellow;">T3N4CI0US{bc298e7\_daf7\_b2d4b347f67\_c\_56e9d\_de34152\_9ad99b1\_7eb78}</mark>

</details>

<details>

<summary>VISKA</summary>



</details>

## MISC

<details>

<summary>Find Me</summary>



</details>

<details>

<summary>Find Us</summary>



</details>



