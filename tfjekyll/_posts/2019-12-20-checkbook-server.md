---
layout: post
title:  "Checkbook Server"
date:   2019-12-20 08:00:00 -0600
subtitle: "Checkbook remote server using AES"
thumbnail: "/img/server-key.png"
categories: java
tags: java crypto
---
[Checkbook](/java/2020/02/17/checkbook.html) used this server written in Java <img src="/img/java.png" style="width: 32px; height: 32px; display: inline-block;"/> as the API to a central MySQL <img src="/img/mysql.png" style="width: 32px; height: 32px; display: inline-block;"/> database storing transaction data. Symmetric AES and asymmetric RSA keys are used to communicate with the remote client. 
![](/img/encrypt.png "Encrypted")

### Story
My Checkbook experience evolved quickly as I went through my college classes. At the point this was successfully written, I was using the Checkbook program as a whole to store and view all the financial transactions I made. I was using a remote server (Ubuntu, at home) to house the API and database.

Checkbook was used all throughout my college days until it evolved again after graduation to an online website instead of a Java Swing UI and Java server.

### Protocol
Client and server communicated in a request->response manner. The client had thirteen, 7 byte control messages to handle all things inserting, updating, deleting, and querying transaction data. 7 bytes? No idea why I chose that back then 0_o. I used Java's switch statement to handle the incoming requests from the client. Example control messages: `GETTRAN`, `GETUSER`, and `ULOGOUT`.


### Cryptography 
Crypto experience was essentially none at the writing of this in 2019. Humbly admitting, Stack Overflow led me to a design using *two* AES keys (so, twice encrypted) message sent over the wire from my remote client to the server. The AES keys were exchanged via the public key cryptography algorithm RSA.

Considering any of my crypto practices *sound* is likely not truthy. In the least, I felt comfortable enough exchanging my financial information over the wire.

Here is where the AES keys are set having been decrypted with the private RSA key:

```java
...
// Set keys
key1 = new SecretKeySpec((byte[]) (_result.getF()) , 0, 16, "AES");
key2 = new SecretKeySpec((byte[]) (_result.getS()) , 0, 16, "AES");
...
```

And the encryption function used to encrypt the data prior to sending:
```java
...
private byte[] doEncrypt(String plainText) throws 
    ...
    {
        // encrypt //
        
        // new method
        Cipher aesCipher = Cipher.getInstance("AES");
        aesCipher.init(Cipher.ENCRYPT_MODE, key1);
        // Encrypt once with key one
        byte[] encryptedArray1 = aesCipher.doFinal(plainText.getBytes());
        
        aesCipher.init(Cipher.ENCRYPT_MODE, key2);
        // Encrypt again with key two
        byte[] encryptedArray2 = aesCipher.doFinal(encryptedArray1);
        
        return encryptedArray2;
    }
...
```

### Ending
The end of this project's era was the beginning of wanting to do more. I felt more could be done with the transactions and it was time to move away from my first ever CS project. Thus, [Checkbook Online](/django/2022/05/30/checkbook-online.html) (~2020) was started.

If you've read this far, thanks for checking it out. I'm open to questions about it or any curious prods you may have. 

Best.


##### Links
<div style="font-size: 10px;">
    <a target="_blank" href="https://icons8.com/icon/IU9BMZfRqyeY/encrypted">Encrypted</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
    <br/>
    <a target="_blank" href="https://icons8.com/icon/13679/java">Java</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
    <br/>
    <a target="_blank" href="https://icons8.com/icon/UFXRpPFebwa2/mysql-logo">MySQL Logo</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
</div>
