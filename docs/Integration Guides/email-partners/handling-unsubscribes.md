---
title: Handling Unsubscribes
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
# Step 1: Handling Unsubscribes

If you’re using Amazon SES or your own SMTP gateway, you’ll have to follow these steps to enable your users to unsubscribe from your email notifications:

* Download this email unsubscription HTML [template file from here](http://static.clevertap.com/docs/email-unsubscribe.html). You can brand this template file if needed. Just ensure that the original JavaScript functions are retained.
* Host that file at a publicly-accessible server. The extension of the file could be anything, even PHP if you want some backend logic of yours to go in there.
* Integrate the CleverTap JavaScript (JS) embed code, which is optimized for integration on both desktop and mobile web sites. Replace CLEVERTAP\_ACCOUNT\_ID with your actual Account ID in the JS. 

```javascript
// Copy and paste the below code snippet inside the <head></head> section of your website

<script type="text/javascript">
     var clevertap = {event:[], profile:[], account:[], onUserLogin:[], notifications:[]};
 // replace with the CLEVERTAP_ACCOUNT_ID with the actual ACCOUNT ID value from your Dashboard -> Settings page
 clevertap.account.push({"id": "CLEVERTAP_ACCOUNT_ID"});
 (function () {
		 var wzrk = document.createElement('script');
		 wzrk.type = 'text/javascript';
		 wzrk.async = true;
		 wzrk.src = ('https:' == document.location.protocol ? 'https://d2r1yp2w7bby2u.cloudfront.net' : 'http://static.clevertap.com') + '/js/a.js';
		 var s = document.getElementsByTagName('script')[0];
		 s.parentNode.insertBefore(wzrk, s);
  })();
</script>
```

* Go to the CleverTap Dashboard → Settings → Amazon SES/Generic SMTP. Now fill in the URL of the unsubscribe page – no parameters, just the URL. e.g. [http://foobar.com/unsubscribe.html](http://foobar.com/unsubscribe.html).
* Now when you’re composing the email, in the body, put the unsubscribe link as shown below. CleverTap will replace  " *|UNSUBSCRIBE|* " with the actual URL of the unsubscribe page at the time of sending out the email.

```html
<a href="*|UNSUBSCRIBE|*">Unsubscribe</a>
```

# Step 2: Understanding the Unsubscription Flow

* When an email notification campaign is sent out, CleverTap will automatically replace the *|UNSUBSCRIBE|* link in the body of the email with the location of your page.
* When a user clicks on the unsubscribe link in your email, the user will be taken to the unsubscribe page.
* On body load call the $WZRK\_WR.getEmail() method, which will call the wzrk\_email\_fetched(emailStr) method on that page when the email is fetched from the server.
* Call the unsubscribe() method when the user confirms that they want to unsubscribe.
* You can call the resubscribe() method when the user wants to resubscribe to the email (this is only valid if the user first unsubscribed, and is still on that page from the earlier link).

# Step 3: Troubleshooting

* The unsubscription link will not work for test emails sent from the notification creation page.
* Make sure that when a user lands on the unsubscription page, the URL has these params:
* e: this contains some meta data about the user.
* wzrk\_ex: this is a CleverTap internal parameter.
