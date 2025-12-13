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
  * Download this email unsubscription HTML [template file from here](http://static.clevertap.com/docs/email-unsubscribe.html). You can edit and brand this template file if required. Following is the Javascript code to be embedded on your page:
[block:code]
{
  "codes": [
    {
      "code": " <div> \n        <h4>I want to unsubscribe from future emails</h4>\n        <input type=\"text\" id=\"email\" readonly=\"readonly\" />\n        <br/><br/>\n        <button onclick=\"unsubscribe()\">Unsubscribe me</button><br/><br/>\n        <!-- button onclick=\"resubscribe()\">Resubscribe</button -->\n    </div>\n\n\n   <script> //Javascript\n// Should be true only if your server is url encoding the URL on unsubscribe landing page\n    var isReEncode = false\n    // on  page load, fetch the email id of the user.\n    window.onload = function() {\n        $WZRK_WR.getEmail(isReEncode);\n    };\n    // will be called after the email id of the user has been fetched\n    function wzrk_email_fetched(emailStr) {\n        document.getElementById(\"email\").value = emailStr;\n    }\n    // will be called after the subscription preferences for the user have been updated\n    function wzrk_email_subscription(status) {\n        //status 0 : unsubscribed, status 1 : subscribed\n        // todo - you can show a success message to the user from here\n        var statusLabel = 'subscribed';\n        if (status == 0) {\n            statusLabel = 'unsubscribed';\n        }\n        alert(\"You've been \" + statusLabel);\n    }\n    // call this function to unsubscribe the user\n    function unsubscribe(isReEncode) {\n        $WZRK_WR.unSubEmail(isReEncode);\n    }\n    // call this function to resubscribe the user\n    function resubscribe(isReEncode) {\n        $WZRK_WR.subEmail(isReEncode);\n    }\n</script>\n\n\n\n\n",
      "language": "html"
    }
  ]
}
[/block]


Just ensure that the original JavaScript functions are retained.
  * Host that file at a publicly-accessible server. The extension of the file could be anything, even PHP if you want some backend logic of yours to go in there.
  * Integrate the CleverTap JavaScript (JS) embed code, which is optimized for integration on both desktop and mobile web sites. Replace CLEVERTAP_ACCOUNT_ID with your actual Account ID in the JS. 
[block:code]
{
  "codes": [
    {
      "code": "// Copy and paste the below code snippet inside the <head></head> section of your website\n\n<script type=\"text/javascript\">\n     var clevertap = {event:[], profile:[], account:[], onUserLogin:[], notifications:[]};\n // replace with the CLEVERTAP_ACCOUNT_ID with the actual ACCOUNT ID value from your Dashboard -> Settings page\n clevertap.account.push({\"id\": \"CLEVERTAP_ACCOUNT_ID\"});\n (function () {\n\t\t var wzrk = document.createElement('script');\n\t\t wzrk.type = 'text/javascript';\n\t\t wzrk.async = true;\n\t\t wzrk.src = ('https:' == document.location.protocol ? 'https://d2r1yp2w7bby2u.cloudfront.net' : 'http://static.clevertap.com') + '/js/a.js';\n\t\t var s = document.getElementsByTagName('script')[0];\n\t\t s.parentNode.insertBefore(wzrk, s);\n  })();\n</script>",
      "language": "javascript"
    }
  ]
}
[/block]
  * Go to the CleverTap Dashboard → Settings → Amazon SES/Generic SMTP. Now fill in the URL of the unsubscribe page – no parameters, just the URL. e.g. http://foobar.com/unsubscribe.html.
  * Now when you’re composing the email, in the body, put the unsubscribe link as shown below. CleverTap will replace  " *|UNSUBSCRIBE|* " with the actual URL of the unsubscribe page at the time of sending out the email.
[block:code]
{
  "codes": [
    {
      "code": "<a href=\"*|UNSUBSCRIBE|*\">Unsubscribe</a>",
      "language": "html"
    }
  ]
}
[/block]
# Step 2: Understanding the Unsubscription Flow
  * When an email notification campaign is sent out, CleverTap will automatically replace the *|UNSUBSCRIBE|* link in the body of the email with the location of your page.
  * When a user clicks on the unsubscribe link in your email, the user will be taken to the unsubscribe page.
  * On body load call the $WZRK_WR.getEmail() method, which will call the wzrk_email_fetched(emailStr) method on that page when the email is fetched from the server.
  * Call the unsubscribe() method when the user confirms that they want to unsubscribe.
  * You can call the resubscribe() method when the user wants to resubscribe to the email (this is only valid if the user first unsubscribed, and is still on that page from the earlier link).

# Step 3: Troubleshooting
  * The unsubscription link will not work for test emails sent from the notification creation page.
  * Make sure that when a user lands on the unsubscription page, the URL has these params:
  * e: this contains some meta data about the user.
  * wzrk_ex: this is a CleverTap internal parameter.