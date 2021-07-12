# Introduction

Cross-site scripting (XSS) is a security vulnerability typically found in web applications. Its a type of injection which can allow an attacker to execute malicious scripts and have it execute on a victims machine.

A web application is vulnerable to XSS if it uses unsanitized user input. XSS is possible in Javascript, VBScript, Flash and CSS.

The extent to the severity of this vulnerability depends on the type of XSS, which is normally split into two categories: persistent/stored and reflected. Depending on which, the following attacks are possible:

- Cookie Stealing - Stealing your cookie from an authenticated session, allowing an attacker to login as you without themselves having to provide authentication.

- Keylogging - An attacker can register a keyboard event listener and send all of your keystrokes to their own server.

- Webcam snapshot - Using HTML5 capabilities its possible to even take snapshots from a compromised computer webcam.

- Phishing - An attacker could either insert fake login forms into the page, or have you redirected to a clone of a site tricking you into revealing your sensitive data.

- Port Scanning - You read that correctly. You can use stored XSS to scan an internal network and identify other hosts on their network.

- Other browser based exploits - There are millions of possibilities with XSS.

Who knew this was all possible by just visiting a web-page. There are measures put in place to prevent this from happening by your browser and anti-virus.

# Stored XSS

Stored cross-site scripting is the most dangerous type of XSS. This is where a malicious string originates from the websites database. This often happens when a website allows user input that is not sanitised (remove the "bad parts" of a users input) when inserted into the database.

![alt text](https://i.imgur.com/LCSFUTB.png "An Example")

A attacker creates a payload in a field when signing up to a website that is stored in the websites database. If the website doesn't properly sanitise that field, when the site displays that field on the page, it will execute the payload to everyone who visits it.

The payload could be as simple as `<script>alert(1)</script>`

However, this payload wont just execute in your browser but any other browsers that display the malicious data inserted into the database.
