---
title: Troubleshooting
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
# Possible causes for  *Webhook Dispatch Failed.* error

Webhook is a request-response type format. CleverTap sends the request and waits for three seconds for a response from the endpoint. If the endpoint URL fails to respond then CleverTap retries the request. If the retry also fails, the campaign stats page is updated with the error "Webhook Dispatch Failed." 

Also, another probable cause for the error is if the webhook endpoint is temporarily unavailable or down.
