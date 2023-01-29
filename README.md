# Password Generator

## Purpose

Build a password generator capable of deriving strong, random (and reproducible!) passwords from easy to remember hints.

## Rationale

One way to securely store and share passwords is by using a password manager.
It is a recommended and widely used solution, but not without problems.
See for example:
* [LastPass vault breach (2022-12-28)](
https://www.theverge.com/2022/12/28/23529547/lastpass-vault-breach-disclosure-encryption-cybersecurity-rebuttal)

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

## Useful tools

1. bootstrap - JavaScript module (npm install bootstrap)
1. [workbox](https://developer.chrome.com/docs/workbox/) - Production-ready service worker libraries and tooling
1. https://web.dev/progressive-web-apps/ - 
1. https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps
1. https://jakearchibald.github.io/isserviceworkerready/
1. https://hnpwa.com/ - a lot of examples with code
1. https://www.pwabuilder.com

## TODO

* web browser plugin and PWA (progressive web app) -
  these probably can use [content scripts](https://developer.chrome.com/docs/extensions/mv3/content_scripts/)
  to detect that pointer is in the password input box... some related Stackoverlow items:
    * [How to access the webpage DOM/HTML from an extension popup or background script?](https://stackoverflow.com/questions/4532236/how-to-access-the-webpage-dom-html-from-an-extension-popup-or-background-script)
    * [How to determine which html page element has focus?](https://stackoverflow.com/questions/483741/how-to-determine-which-html-page-element-has-focus)
* native smartphone apps (Android, iOS)
* [progressive web application](https://en.wikipedia.org/wiki/Progressive_web_app)
* add logo e.g. ``icons/logo.png`` generated with [DALL-E](https://openai.com/dall-e-2/)
* compile node js to byte-code
* run local server for testing e.g.: python -m http.server 8080
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
1. https://www.udemy.com/course/progressive-web-apps/learn/lecture/7171264


## Password generators

I could not find any password generators which would generate reproducible password given
a hint, and possibly some other parameters.

1. https://passgen.io/
1. https://passgen.co/
1. https://www.avast.com/en-us/random-password-generator
1. https://www.nexcess.net/web-tools/secure-password-generator/
1. https://www.dashlane.com/features/password-generator
1. https://www.grc.com/passwords.htm

## Password testers

1. https://www.security.org/how-secure-is-my-password/
1. https://www.passwordmonster.com

## JavaScript: Create reproducible UUIDs within a name space

This can be useful to hash user emails e.g.

```
const { v5: uuidv5 } = require('uuid');
const EMAIL_NAMESPACE = '1b671a64-40d5-491e-99b0-da01ff1f3341';
uuidv5('alice@gmail.com', EMAILS_NAMESPACE); // -> '28e0fb10-e6ba-5663-9eb4-54e0b9607643'
uuidv5('bob@gmail.com', EMAILS_NAMESPACE); // -> '5337ff34-e3d4-5234-bc8a-0baa84a4fb48'
```

This way we can check if user (i.e. email) is in the system without actually storing emails

## Password managers (bad) press

1. [Norton LifeLock Accounts Targeted (2023-01-19)](https://www.cnet.com/tech/services-and-software/norton-lifelock-accounts-targeted-what-to-know-and-how-to-protect-your-passwords/)
1. [Lastpass: Hackers stole customer vault data in cloud storage breach (2022-12-22)](https://www.bleepingcomputer.com/news/security/lastpass-hackers-stole-customer-vault-data-in-cloud-storage-breach/)


## Notes

* `document.querySelectorAll('input[type="password"]')` can be used to select input box (or boxes?) for password in the _active_ page (see [this](https://stackoverflow.com/questions/75238386/is-there-a-way-to-find-html-element-by-type/75238590#75238590) stackoverflow entry)
* [Element.getClientRects()](https://developer.mozilla.org/en-US/docs/Web/API/Element/getClientRects) - might be useful to get coords of input box,
maybe also jQuery [.position()](https://api.jquery.com/position/)?
* [How to get access to DOM elements?](https://stackoverflow.com/questions/19758028/chrome-extension-get-dom-content) from popup?


