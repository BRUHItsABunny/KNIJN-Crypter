# KNIJN Crypter

KNIJN Crypter is a text crypter to sollidify and offload E2EE (end-2-end encryption) and aid privacy.

### Motivation

Always being interested in secrecy, I built crypters in the past but none of them were any as secure as this one, from using character dictionaries to hashed up messages to even AES+base64 encoded messages, they all seemed insecure on one or more vectors.

Lately I heard about messengers being attacked with MITM attacks and social media not encrypting data well enough or at all to begin with, this lead to me doublling down on another crypter but this time more secure than ever.

### Features

Currently these features are supported:

* Negotiate symmetric crypto keys (Diffie-Hellman style)
	Using the following methods of transportation:
	* UDP Hole punching
	* IRC Chat servers
	* QR codes
	* LAN serving
	* Manual KNIJN:// links
* Encrypt and decrypt text (NaCL, saltbox style)
* Group encryption instances
* Automatic decryption of copied messages
* Variable popup duration based on reading speed settings
* Importing and exporting installations across devices

### Security

The app uses the Diffie-Hellman key exchange (poorly named, it is not an exchange rather a negotiation) technique to negotiate symmetric keys for each instance. That means that the actual key is never transmitted anywhere, making it almost impossible to figure out if done right, which I hope I did.

After the key negotiation it uses the NaCL libSodium libaries to encrypt and decrypt messages securely and then turned into a base64 message for easy transimission with some added signatures to prevent tampering and spoofing.

### Future

Given this current release is an open beta, there are bugs and a very distinct lack of documentation is clearly visible.

In the future I plan to add GIF's and videos and actual documentation as well as more features and bugfixes.

### Known issues

There are a few known issues present as of now:
* The automatic decryption doesn't work when dealing with chat bubble messengers like FB messenger.
* The toast message pop up timing control flashes and on Android 10 straight up fails to do what it's supposed to do.

If you find any new issues feel free to open an issue in the Issues tab on GitHub and port it there, don't forget to take screenshot and/or screen recordings for the easiest problem solving (logcat from rooted users is welcome too!).
