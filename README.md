# Password Generator

## Purpose

Build a password generator capable of deriving strong, random (and reproducible!) passwords from easy to remember hints.

## Rationale

One way to securely store and share passwords is by using a password manager.
It is a recommended and widely used solution, but not without problems.
Proposed generator is an alternative approach with two main advantages:
(1) passwords are generated on demand and never stored - there is no danger of data breach
(2) there is no master password to remember.
Large number of sites and apps offer strong random password generation,
but despite some (not exhaustive!) search (see some links below)
I was not able to locate any which would allow to generate reproducible, hint-based passwords.

## Simple Example

The table below illustrates how from the same hint, using easily customizable options,
passwords with length defined length, etc.

| hint | generated password |
| -----|------------------- |
| mos  | JF8zuf?7 |
| mos  | 0K4jTgOsdfA7c@yW |
| mos  | nKxeTUvhXgNaN>qS6CUZmz8uSRocjbpA |

## Check it out!

1. http://hpass.net/full
1. https://ryszard314159.github.io/template.html



## TODO

* web browser plugin
* native smartphone apps (Android, iOS)
* [progressive web application](https://en.wikipedia.org/wiki/Progressive_web_app)
* add logo e.g. ``icons/logo.png`` generated with [DALL-E](https://openai.com/dall-e-2/)
* compile node js to byte-code
* run local serer for testing e.g.: python -m http.server 8080
* https://web.dev/how-to-use-local-https/
* install local https server to facilitate pwa testing: https://github.com/FiloSottile/mkcert
* https://www.arubacloud.com/tutorial/how-to-enable-https-protocol-with-apache-2-on-ubuntu-20-04.aspx
* https://www.arubacloud.com/tutorial/how-to-create-a-self-signed-ssl-certificate-on-ubuntu-18-04.aspx

```
$ ./mkcert -install
Created a new local CA 💥
Sudo password:
The local CA is now installed in the system trust store! ⚡️
The local CA is now installed in the Firefox and/or Chrome/Chromium trust store (requires browser restart)! 🦊
```


Here are pointers to some resources:

1. [Chrome extensions samples](https://github.com/GoogleChrome/chrome-extensions-samples)
1. [How to make a Chrome browser extension from scratch | Understanding Chrome extension anatomy](https://medium.com/front-end-weekly/how-to-make-a-chrome-browser-extension-from-scratch-chrome-extension-development-basics-basic-ba1daee11123)
1. https://web.dev/progressive-web-apps/
1. https://simplepwa.com/
1. https://github.com/hemanth/awesome-pwa
1. https://github.com/mdn/pwa-examples
1. https://github.com/vaadin/expense-manager-demo
1. [PWA Series: Hands-on, create your first PWA, step by step
](https://medium.com/samsung-internet-dev/pwa-series-hands-on-create-your-first-pwa-step-by-step-5bb7a6605349)
1. [Hello-pwa](https://github.com/jamesjohnson280/hello-pwa)
1. https://web.dev/install-criteria/#criteria
1. https://www.freecodecamp.org/news/publish-your-website-netlify-github/
1. [Building & Deploying your first Progressive Web App](https://link.medium.com/eUnGrg6nCvb)


## Password generators

I could not find any password generators which would generate reproducible password given
a hint, and possibly some other parameters.

1. https://passgen.io/
1. https://passgen.co/
1. https://www.avast.com/en-us/random-password-generator
1. https://www.nexcess.net/web-tools/secure-password-generator/
1. https://www.dashlane.com/features/password-generator
1. https://www.grc.com/passwords.htm



