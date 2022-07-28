# Forensics

#### **Difficulty:**

****[**Easy**](forensics.md#easy)****

****[**Medium**](forensics.md#medium)****

****[**Hard**](forensics.md#undefined)****

## Easy <a href="#easy" id="easy"></a>

<details>

<summary>ILLUMINATION</summary>

**Category**: Forensic

**Difficulty**: Easy

**Challenge** **Description**:

_<mark style="background-color:yellow;">A Junior Developer just switched to a new source control platform. Can you find the secret token?</mark>_

_<mark style="background-color:yellow;"></mark>_

Download and unzip the file given.

* Illumination.zip

Using **`$ls -al`** will show if there is a hidden file.

​![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F4lw1ZFO57LLqZA6giSn1%2Fuploads%2F4NI6s3RBwKuVUxb5UaX5%2Fimage.png?alt=media\&token=3eb97ba2-6810-4280-95f0-9165838599fc)

There is a hidden file called _**'.git'**._

Since its a git folder we can use **`$git log`** to see recorded commit of the project.

<img src="../../.gitbook/assets/image (10).png" alt="" data-size="original">

Now we just need to focus on the token part and use **`$git show <commit code>`** to see the changes.

<img src="../../.gitbook/assets/image (2) (1).png" alt="" data-size="original">

Now we already get the secret token but its in the form of base64.

We can change it using **`$echo '<base64 string>' | base 64 -d`**.

<img src="../../.gitbook/assets/image (7).png" alt="" data-size="original">

**Flag:** <mark style="background-color:blue;">HTB{v3rsi0n\_c0ntr0l\_am\_I\_right?}</mark>

</details>

<details>

<summary>REMINISCENT</summary>

**Category**: Forensic

**Difficulty**: Easy

**Challenge** **Description**:

<mark style="background-color:yellow;">Suspicious traffic was detected from a recruiter's virtual PC. A memory dump of the offending VM was captured before it was removed from the network for imaging and analysis. Our recruiter mentioned he received an email from someone regarding their resume. A copy of the email was recovered and is provided for reference. Find and decode the source of the malware to find the flag.</mark>



Download and unzip the file given.

* Reminiscent.zip

Since its a memory dump situation we will be using **Volatility** tools to analyse the file.

First I displayed the output of a file called **Resume.eml**.

<img src="../../.gitbook/assets/image (3) (1).png" alt="" data-size="original">

We can see that there is a **resume.zip** file sending to Frank and with a link _**http://10.10.99.55:8080/resume.zip**_ but seems the link cant be opened directly.



Now using volatility on the file called **flounder-pc-memdump.elf** and use imageinfo to get the profile.

**`$python vol.py -f flounder-pc-memdump.elf imageinfo`**

<img src="../../.gitbook/assets/image (11).png" alt="" data-size="original">

Knowing that there is a resume zip file the first thing I did is use a **filescan** and filter anything that has **'resume'** on it.

**`$python vol.py -f flounder-pc-memdump.elf --profile=Win7SP1x64 filescan | grep resume`**

<img src="../../.gitbook/assets/image (4) (1).png" alt="" data-size="original">

Now we can see there is a file called **resume.pdf** inside the file.



We can use **dumpfiles** function to dump the **resume.pdf**.

**`$python vol.py -f flounder-pc-memdump.elf --profile=Win7SP1x64 dumpfiles -Q 0x000000001e8feb70 -D /home/db10/ctf`**

<img src="../../.gitbook/assets/image (6) (1).png" alt="" data-size="original">

After done dump the file now we can use **Strings** to display whats inside.

<img src="../../.gitbook/assets/image (15).png" alt="" data-size="original">

We can see there is is some data in **Base64**. Now lets use **Cyberchef** to decode it.

<img src="../../.gitbook/assets/image (9).png" alt="" data-size="original">

After decoding it the first time. it still showing a data in **Base64**. So we decode it again&#x20;

<img src="../../.gitbook/assets/image (5) (1).png" alt="" data-size="original">

****

</details>

## Medium

<details>

<summary></summary>



</details>

## Hard

<details>

<summary></summary>



</details>
