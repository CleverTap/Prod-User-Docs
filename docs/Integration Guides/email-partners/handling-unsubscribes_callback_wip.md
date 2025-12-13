---
title: Handling Unsubscribes_callback_WIP
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
If you are using Amazon SES or your own SMTP gateway, you will have to follow these steps to enable your users to unsubscribe from your email notifications:
1. Download this email unsubscription HTML template file from our [Email Unsubscribe](http://static.clevertap.com/docs/email-unsubscribe.html) page. You can edit and brand this template file if required. 

The following is the Javascript code to be embedded on your page:
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
## Subscription Groups
[block:code]
{
  "codes": [
    {
      "code": " <div>    \n    <h4>I want to unsubscribe from future emails\n    </h4>        \n    <input type=\"text\" id=\"email\" /> \n    <br/><br/>\n    <!-- Displaying unsubscribe groups in the below div once loaded -->\n    <div id=\"unsubscribe-groups\" style=\"display: none\"></div>\n    <!-- Unsubscribe groups buttont. User will click here and it should call `changeSubscriptionGroups`\n        method to send the request to CleverTap. -->\n    <button onclick=\"changeSubscriptionGroups()\">Update Subscription Groups</button>    \n </div>  \n <script> \n   window.onload = function() {\n        var isReEncode = false //Should be true only if your server is url encoding the URL on unsubscribe landing page     \n        var withGroups = true  // Should be true if the unsubscribe groups should be displayed on the landing page.\n        $WZRK_WR.getEmail(false, withGroups);\n    };\n    // will be called after the email id of the user has been fetched\n    function wzrk_email_fetched(emailStr, profile) {\n        document.getElementById(\"email\").value = emailStr;\n        if(!profile || !profile.groups || profile.groups.length === 0) {\n            console.log(\"did not recv groups in callback\");\n        }\n        var subscriptionGroups = profile.groups; // will be recvd only if withGroups passed true above\n        $WZRK_WR.setSubscriptionGroups(subscriptionGroups); // Can also be set here and can be retrieved by calling `$WZRK_WR.getSubscriptionGroups` method\n         $WZRK_WR.setUpdatedCategoryLong(profile);\n        displayGroups()\n    }\n  function displayGroups() {\n    //   Fetching groups\n      var subscriptionGroups = $WZRK_WR.getSubscriptionGroups();\n    //  Rendering groups in above html div\n      var addList = document.getElementById('unsubscribe-groups');\n            addList.style.display = 'block';\n            for(var i = 0; i < subscriptionGroups.length; i++) {\n                var obj = subscriptionGroups[i];\n                var checkBox = document.createElement(\"INPUT\");\n                var isUnsubscribed = obj.isUnsubscribed\n                checkBox.setAttribute(\"type\", \"checkbox\");\n                if(isUnsubscribed){\n                    checkBox.setAttribute(\"checked\", true);\n                }\n                checkBox.setAttribute(\"name\", obj.name)\n                checkBox.setAttribute(\"id\", obj.name)\n                checkBox.setAttribute(\"class\", \"ct-unsub-group-input-item\");\n                var label = document.createElement(\"LABEL\");\n                label.setAttribute(\"for\", obj.name)\n                label.innerHTML = \"Unsubscribe to \" + obj.name \n                addList.appendChild(label);\n                addList.appendChild(checkBox);\n                addList.append(document.createElement('br'));\n            }\n  }\n// This function is used to send groups updation request. User can directly call\n// `$WZRK_WR.changeSubscriptionGroups(isReencode, updatedGroups)` by passing updated groups in format specified.\n   function changeSubscriptionGroups(){\n    let unsubcribeGroups = [];\n        var elements = document.getElementsByClassName(\n            \"ct-unsub-group-input-item\");\n        for (var i = 0; i < elements.length; i++) {\n            var element = elements[i];\n            if(element.name) {\n                var data = {name: element.name, isUnsubscribed: element.checked}\n                unsubcribeGroups.push(data)\n            }\n        }\n        $WZRK_WR.changeSubscriptionGroups(false, unsubcribeGroups);\n     } \n    // will be called after the subscription preferences for the user have been updated\n    function wzrk_email_subscription(status) {\n        //status 0 : unsubscribed, status 1 : subscribed\n        // todo - you can show a success message to the user from here\n        var statusLabel = 'subscribed';\n        if (status == 0) {\n            statusLabel = 'unsubscribed';\n        }\n        alert(\"You've been \" + statusLabel);\n    }\n </script>\n",
      "language": "html"
    }
  ]
}
[/block]
Unsubscribe groups are handled in the format as shown below where "name" is for the name of the group and "isUnsubscribed" is for subscription status of the group.
[block:code]
{
  "codes": [
    {
      "code": "\n{\nvar groupsExample = [\n{name: \"group1\", isUnsubscribed: false}, \n{name: \"group2\", isUnsubscribed: true}\n]\n}\n",
      "language": "html"
    }
  ]
}
[/block]
Ensure that the original JavaScript functions are retained.
1. Host that file at a publicly-accessible server. The extension of the file could be anything, including PHP if you want to incorporate some of your backend logic.
2. Integrate the CleverTap JavaScript (JS) embed code, which is optimized for integration on both desktop and mobile web sites. Replace CLEVERTAP_ACCOUNT_ID with your actual Account ID in the JS. 
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
3. Go to the CleverTap Dashboard > *Settings* > *Amazon SES/Generic SMTP*. Now, only fill in the URL of the unsubscribe page with no parameters, such as http://foobar.com/unsubscribe.html.
4. When you are composing the email in the body, put the unsubscribe link as shown below. CleverTap replaces *|UNSUBSCRIBE|* with the actual URL of the unsubscribe page at the time of sending out the email.
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
# Understanding the Unsubscription Flow
1. When an email notification campaign is sent out, CleverTap will automatically replace the *|UNSUBSCRIBE|* link in the body of the email with the location of your page.
2. When a user clicks on the unsubscribe link in your email, the user will be taken to the unsubscribe page. 
3. After the body loads, call the $WZRK_WR.getEmail() method, which calls the wzrk_email_fetched(emailStr) method on that page when the email is fetched from the server.
4. Call the unsubscribe() method when the user confirms they want to unsubscribe.
5. You can call the resubscribe() method when the user wants to resubscribe to the email (this is only valid if the user first unsubscribed and is still on that page from the earlier link).

# Troubleshooting
1. The unsubscription link will not work for test emails sent from the notification creation page.
2. Make sure that when a user lands on the unsubscription page, the URL has these parameters:
 * e: This contains some metadata about the user.
 * wzrk_ex: This is a CleverTap internal parameter.
3. The subscription is in effect at the account level. It means all the users linked to the email address are unsubscribed.