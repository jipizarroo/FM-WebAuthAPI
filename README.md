# Authentication

Authentication: It validates the identity of a user or a system.

Authorization: What permissions and privileges you give to a user. ( This has to do with tokens, etc. )

## Concepts

* Credentials: Whatever is needed to identify the user server side. ( Ex: User and PW ).
* Single Sign On (SSO): To sign the user with the same credentials but on different websites.
* 2FA ( Two-factor authentication): More credentials so that the user can log in. ( Ex: User and PW ( One factor ), SMS ( Second factor ).
* OAuth 2.0: How can we keep the user authenticated in the logged website, it's a login flow where you can log in to a 3rd party server. ( EX: You wanna get into your GitHub acc, but you go to google to do the authorization )&#x20;
* OTP ( One time password ): When you receive an email or sms with one password to confirm it's you.
* Public key Cryptography: Will create two keys, one public and one private.

### &#x20; Implementing Authentication

Custom Auth: User/Password || WebAuthn

Identity Providers: OpenID || SAML 2.0 => Sign in with...

Identity As a Service IDaaS: Auth0, Firebase, anything where you pay for the service.

### Authentication on the Web.

Security Risks:

* Man-in-the-middle attacks: No one is attacking the server, and No one is attacking the user, they are attacking something in the middle.
* Keyloggers
* Easy-to-guess passwords
* Web servers and DBs attacks
* Phishing and social engineering attacks

### HTTP Auth / Login Forms

You type your secret in a Form, in the native HTTP form that the browser offers =>&#x20;

From the browser, it goes from HTTP to the Web server and into the DB.

We have two points of failure here:&#x20;

* The keyboard: The problem here is the user, we don't know if he DL something.
* HTTP: Everything goes in plain text => This is where the man in the middle shines. => Easy fix, it should move into HTTPS, where the data from the browser to the server is encrypted.

We need to be careful where we put our credentials in.

Manager passwords still offer problems. That's why we need to offer a solution where UX does not get too crazy because we need to be safer, we need to find a balance.

### Multi-factor Authentication.

We add a new credential to keep things even safer.

Browser form + SMS, WhatsApp, Email => they both go to the server.

Still not safe => easy to get an SMS chip with the same number or WhatsApp number.&#x20;

But not just that, there is a problem where we are asking the user to do too many things.

### Passwordless

Public & Private key&#x20;

Private => Will be stored in your device ( USB Keys or FaceID ( even tho it's not 100% )).

Public => This one will travel everywhere.

If an attacker gets to the DB, he will get the public key.

If the attacker gets to the user, he does not know the private key => The key will not work on a different website, it is meant for that thing only.

{% hint style="info" %}
Remember that nothing is 100% safe, there is still breaches in security.
{% endhint %}

<figure><img src=".gitbook/assets/Screen Shot 2023-03-27 at 21.13.40.png" alt=""><figcaption><p>Red = Bad, Green = Good.</p></figcaption></figure>

{% hint style="info" %}
There is a new type of world that's coming to a bunch of browsers => passkeys

In simple terms, private keys will be saved in your cloud provider, and that will make it so that you can use it across multiple devices and not just one browser.
{% endhint %}
