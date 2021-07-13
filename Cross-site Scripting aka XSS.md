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

Its mostly finds in comment area of any website.

# Reflected XSS

In a reflected cross-site scripting attack, the malicious payload is part of the victims request to the website. The website includes this payload in response back to the user. To summarise, an attacker needs to trick a victim into clicking a URL to execute their malicious payload.

This might seem harmless as it requires the victim to send a request containing an attackers payload, and a user wouldn't attack themselves. However, attackers could trick the user into clicking their crafted link that contains their payload via social-engineering them via email..

Reflected XSS is the most common type of XSS attack.

![alt text](https://i.imgur.com/yX7zRh8.png "An Example")

An attacker crafts a URL containing a malicious payload and sends it to the victim. The victim is tricked by the attacker into clicking the URL. The request could be ` http://example.com/search?keyword=<script>...</script> `

The website then includes this malicious payload from the request in the response to the user. The victims browser will execute the payload inside the response. The data the script gathered is then sent back to the attacker (it might not necessarily be sent from the victim, but to another website where the attacker then gathers this data - this protects the attacker from directly receiving the victims data).

# DOM-Based XSS 

> What is the DOM ?

In a DOM-based XSS attack, a malicious payload is not actually parsed by the victim's browser until the website's legitimate JavaScript is executed. So what does this mean?

With reflective xss, an attackers payload will be injected directly on the website and will not matter when other Javascript on the site gets loaded.

<html>
    You searched for <em><script>...</script></em>
</html>

With DOM-Based xss, an attackers payload will only be executed when the vulnerable Javascript code is either loaded or interacted with. It goes through a Javascript function like so:

var keyword = document.querySelector('#search')
keyword.innerHTML = <script>...</script>