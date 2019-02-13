# your email is not valid

![Wrong email format validator](https://github.com/lpefferkorn/youremailisnotvalid/blob/master/invalid_email.png)
Your system is wrong, my email is valid!

When you register an account on a website, many refuse perfectly valid emails, denying you the possibility to use email **aliases** or your new fancy **username@domain.coffee** email.

# Possible issues

## 'New' TLDs

With the increase of top-level domains ([as of April 2018, the root domain contains 1543 top-level domains)](https://en.wikipedia.org/wiki/List_of_Internet_top-level_domains) some websites did not keep up, and won't accept your fancy email ending in **@domain.coffee** or **@domain.xyz** despite being perfectly valid

## Aliases/Subaddressing

Some mail services support **aliases** (e.g. *yourname+shopping@example.com*) where from your email account (*yourname@example.com*) 
you append a delimiter (here *+*) and a tag of your choice (here *shopping*)

Emails sent to **yourname+shopping@example.com** will be delivered to **yourname@example.com**

The tag is up to you, and can be whatever you want to uniquely identify the purpose of an alias.

The advantages are:
  * Ease email filtering based on the recipient (yourname+school@example.com -> school folder, yourname+tag1@example.com -> tag1 folder, ...)
  * Tracking the source of spams (spam sent to yourname+website1@example.com -> very likely that something shaddy happened with website1)
  * Creation of unique, disposable addresses

Some mail services support this feature (Wikipedia article)[https://en.wikipedia.org/wiki/Email_address#Subaddressing]:

  * Gmail [Support page](https://support.google.com/mail/answer/22370?hl=en)
  * Rackspace
  * Yahoo
  * Apple
  * Outlook.com
  * ProtonMail
  * FastMail
  * ...
  
If you handle your own email server/domain this is very likely to work out of the box, depending on your MTA configuration though.
    
# Root cause
Validating the format of an email is a [difficult known problem](https://en.wikipedia.org/wiki/Email_address#Validation_and_verification), 
and often syntactically correct emails are rejected.

One workaround if you host your own email service is to change the delimiter to something more likely to be accepted (with Postfix I changed the [recipient_delimiter](http://www.postfix.org/postconf.5.html#recipient_delimiter)) to **-**, it works pretty well.

Otherwise, contacting the website customer support is the only way to get this fixed.

# Proposition

While an isolated complain to the customer support is unlikely to change things, I would like to list **here all the websites not accepting email aliases**.

I don't mean to publicly shame them (as they may not even be aware of the issue), 
but to **raise awareness about the pain**, **get them to eventually fix their system** and **vent your spleen** :)

# Contributions

## Websites

Please create a pull request with the following information:
  * Website url
  * When you tried to register
  * The format of the email refused
  * Eventually, a screenshot of the relevant part of the form (please don't use *your* email address, but something that matches the reject format like name+tag@example.com)
  
# Okay, how should I check the email then?

As I am not a web developer, I have no clue about the possible best solutions to address this problem.
If you have experience on this matter, I would be very happy if you can share your experience.

Thank you for trying to make Internet a bit less annoying place :)

* [```<input type="email">```](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/email)
* [The 100% correct way to validate email addresses: send your users an activation email](https://hackernoon.com/the-100-correct-way-to-validate-email-addresses-7c4818f24643)

# Websites refusing valid emails

## Oracle.com
2018/08/28 ```yourname+tag@example.com```
![Wrong email format validator](https://github.com/lpefferkorn/youremailisnotvalid/blob/master/forms/oracle.png)

## AirFrance Android app
2019/02/13 Cannot update contact details via the app:
![Wrong email format validator](https://github.com/lpefferkorn/youremailisnotvalid/blob/master/forms/air_france_app.png)

