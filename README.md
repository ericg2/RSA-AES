# RSA-AES
This Java API allows you to easily and securely encrypt/decrypt important data using RSA and AES.

# Background
I wanted to make an actual program in Java for the first time and when looking for many ways to use RSA in a Java program online, many were complicated and/or very outdated. So I made this API that lets you **easily** encrypt and decrypt information using RSA with the added bonus of having AES built-in and loading custom keys.

# Usage
This program works in a class method, meaning you can call as much instances as you want in a single program. It can either generate everything for you, or you can input your own keys such as if you are importing keys from another message or file. When you auto-generate, you can pick the length of the RSA bit to any value and the AES password is random-generated and you can pick the size too. 

Here is an example of auto-generating an RSA/AES key using this API.

```Java
RSA rsaHandler = new RSA(true, 1024, 128);

PrivateKey privateKey = rsaHandler.getPrivateKey();
PublicKey publicKey = rsaHandler.getPublicKey();
String aesKey = rsaHandler.getAESKey();

String textToEncrypt = "Hello World!"
String encryptedText = rsaHandler.encrypt(textToEncrypt);
String decryptedText = rsaHandler.decrypt(encryptedText);
```

The first parameter means to automatically generate keys, the second option was the size of the RSA key, and the third was the size of the randomly generated AES password.

# Manually Importing Keys
This program also supports manually importing keys as well as automatically generating them. To do this, you change the `true` at the beginning to `false` and the other 2 values can be any number (it doesn't matter).

```Java
RSA rsaHandler = new RSA(false, 1, 1)

rsaHandler.setPrivateKey(xyz);
rsaHandler.setPublicKey(xyz);
rsaHandler.setAESKey(xyz);

rsaHandler.encrypt("manually imported keys test");
```

# Downloads/Program Usage
You can download the source code in this GitHub repository and include this API in any of your software, however if you do please give me credit.
