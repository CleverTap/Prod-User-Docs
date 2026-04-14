---
title: Technology Partners
excerpt: Learn about CleverTap's third-party integration.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Analytics

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
  <a href="https://docs.clevertap.com/docs/amplitude">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/f4f59df2070156a00d549967bcdd67c7fad4157253db4fd1d512a38738a16e98-Amplitude_idlx3byNUU_0.svg" alt="Amplitude" class="logo">
        </div>
        <div class="content">
            <div class="name">Amplitude</div>
            <div class="category">Analytics</div>
        </div>
    </div>
</a>
<a href="https://docs.clevertap.com/docs/mixpanel">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/cd97b5982cb3408405a2b6999592b7a5ed386a73b807ed53577149ba173cc245-Mixpanel_Symbol_0.svg" alt="Mixpanel" class="logo">
        </div>
        <div class="content">
            <div class="name">Mixpanel</div>
            <div class="category">Analytics</div>
        </div>
    </div>
</a> 
  <a href="https://docs.clevertap.com/docs/posthog">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/db2a486044cfc17b42cf7642fac3aadf360ed7e022d8da623086d491eaee5291-posthog_logo.jpeg" alt="PostHog" class="logo">
        </div>
        <div class="content">
            <div class="name">PostHog</div>
            <div class="category">Analytics</div>
        </div>
    </div>
</a> 
    </div>
</body>
</html>
`}</HTMLBlock>

# Attribution

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
  <a href="https://developer.clevertap.com/docs/adjust">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/487110869d01e0f2e506e9748d03217555ba50b6fc30f24fcd22ceeee65047a4-Adjust_idZed2gUTA_0.svg" alt="Adjust" class="logo">
        </div>
        <div class="content">
            <div class="name">Adjust</div>
            <div class="category">Attribution</div>
        </div>
    </div>
</a>

<a href="https://developer.clevertap.com/docs/airbridge">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/93bb344627f1bd8a4d187ff5ebc1da06604fb3a7805ea6fdae208089fb6c5b6b-Airbnb_Symbol_0.svg" alt="Airbridge" class="logo">
        </div>
        <div class="content">
            <div class="name">Airbridge</div>
            <div class="category">Attribution</div>
        </div>
    </div>
</a>

<a href="https://developer.clevertap.com/docs/appsflyer">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/fe763ec13f8c9d9a6a85e13a0f1ac9b8e352c8dee2887f25025a728f94204499-AppsFlyer_idZaZLy7nj_0.svg" alt="AppsFlyer" class="logo">
        </div>
        <div class="content">
            <div class="name">AppsFlyer</div>
            <div class="category">Attribution</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/apptrove">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/1d84909a84cbc1303083f451b01b6345f8329ac4a8bc8a0bf675153453cea99c-Apptrove.webp" alt="AppTrove" class="logo">
        </div>
        <div class="content">
            <div class="name">AppTrove</div>
            <div class="category">Attribution</div>
        </div>
    </div>
</a>

<a href="https://developer.clevertap.com/docs/branch">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/311972c7da6cd9956e8110911d763cb514aa30b6354505c4f6a38aea2f011ef6-Branch_idSRMs7jP1_0.svg" alt="Branch" class="logo">
        </div>
        <div class="content">
            <div class="name">Branch</div>
            <div class="category">Attribution</div>
        </div>
    </div>
</a>

<a href="https://developer.clevertap.com/docs/singular-apsalar">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/6865a95b6399b793b628eba0eec9b1a5ee851bea5b0f3eea31acf796042b599b-Singular_id1QD_LCjD_0.svg" alt="Singular" class="logo">
        </div>
        <div class="content">
            <div class="name">Singular</div>
            <div class="category">Attribution</div>
        </div>
    </div>
</a>
    </div>
</body>
</html>
`}</HTMLBlock>

# Contextual Location

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
  <a href="https://docs.clevertap.com/docs/accuweather">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/dd51ed2f15933921eda0c2864841cb0761d382c16e9715810a7491edd363768c-accuweather_.jpg" alt="AccuWeather" class="logo">
        </div>
        <div class="content">
            <div class="name">AccuWeather</div>
            <div class="category">Contextual Location</div>
        </div>
    </div>
</a>      
  <a href="https://docs.clevertap.com/docs/open-weather">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/63fbf8519497c134c05abb9fdb75b7367cdfe1634c5055db6511772fffceae8f-Unknown.png" alt="OpenWeather" class="logo">
        </div>
        <div class="content">
            <div class="name">OpenWeather</div>
            <div class="category">Contextual Location</div>
        </div>
    </div>
</a>
 <a href="https://docs.clevertap.com/docs/radar">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/19d8b16869e0287a1ecda26d4da7b1464c53f72d28e3c43b7d6bbd082e411cbf-radarlabs_logo.jpeg" alt="Radar" class="logo">
        </div>
        <div class="content">
            <div class="name">Radar</div>
            <div class="category">Contextual Location</div>
        </div>
    </div>
</a>  
  <a href="https://docs.clevertap.com/docs/weather-api">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/2ae1b1dd0ae34c6cea66554dbe3c632d0e2b08c5ff2cce0965133184cdc5d45d-WeatherAPIsmall.thumb.png.a0e7c28dff2a10c21458e22d5a9a4cb7.png" alt="Weather API" class="logo">
        </div>
        <div class="content">
            <div class="name">Weather API</div>
            <div class="category">Contextual Location</div>
        </div>
    </div>
</a> 
  </div>
</body>
</html>
`}</HTMLBlock>

# Crash Analytics

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
   <a href="https://docs.clevertap.com/docs/apteligent">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/70fbc5c82ff59badd58a4faad563c59fd734cfdfda1f55ed55f6916c474c75f8-Apteligent.jpeg" alt="Apteligent" class="logo">
        </div>
        <div class="content">
            <div class="name">Apteligent</div>
            <div class="category">Crash Analytics</div>
        </div>
    </div>
</a>
      
    </div>
</body>
</html>
`}</HTMLBlock>

# Customer Relationship Management

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
 <a href="https://docs.clevertap.com/docs/formsuite">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/b852d6ec66c2d59ecb376321311042169c153fcbe140577a8bbf7d5b3a282e57-formsuits.jpeg" alt="Formsuite" class="logo">
        </div>
        <div class="content">
            <div class="name">Formsuite</div>
            <div class="category">Customer Relationship Management</div>
        </div>
    </div>
</a>
 <a href="https://docs.clevertap.com/docs/freshsales">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/f71d2f977d36fc3059891a3cf01ea6d152d791eab6119856ec1daf8e1d1871e9-freshworks_inc_logo.jpeg" alt="FreshSales" class="logo">
        </div>
        <div class="content">
            <div class="name">FreshSales</div>
            <div class="category">Customer Relationship Management</div>
        </div>
    </div>
</a>
<a href="https://docs.clevertap.com/docs/hubspot-via-zapier">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/45ba67395af4a7d6bed73d2f35e5e99218b9d0500c965f63073886e7f64c431c-id_J1lk9xr_1740630488966_1.png" alt="HubSpot" class="logo">
        </div>
        <div class="content">
            <div class="name">HubSpot</div>
            <div class="category">Customer Relationship Management</div>
        </div>
    </div>
</a>
 <a href="https://docs.clevertap.com/docs/iterate">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/e4ffd2a21dae88c03ff2431e1d9995ec0bc2548e39114d7607838a99318337de-iteratehq_logo.jpeg" alt="Iterate" class="logo">
        </div>
        <div class="content">
            <div class="name">Iterate</div>
            <div class="category">Customer Relationship Management</div>
        </div>
    </div>
</a>
    <a href="https://docs.clevertap.com/docs/instapage-via-zapier">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/0030bcf479f2edb3403a127109064855bbd2e89f137202cb4ede64d7c959ca0a-idbj7tYkMJ_1740630514139.png" alt="Instapage" class="logo">
        </div>
        <div class="content">
            <div class="name">Instapage</div>
            <div class="category">Customer Relationship Management</div>
        </div>
    </div>
</a>
    <a href="https://docs.clevertap.com/docs/leadsquared">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/80aef4bde3273cf4c6b40d5507f8ebf10db31dd73fa242146674aad49d9a48ee-leadsquared_logo.jpeg" alt="LeadSquared" class="logo">
        </div>
        <div class="content">
            <div class="name">LeadSquared</div>
            <div class="category">Customer Relationship Management</div>
        </div>
    </div>
</a>
    <a href="https://docs.clevertap.com/docs/pipedrive-via-zapier">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/a935283a4c39eb9f0f372615f4a9e744f6ff0b7500e3468219ccc5c9a910ec57-pipedrive_logo.jpeg" alt="Pipedrive" class="logo">
        </div>
        <div class="content">
            <div class="name">Pipedrive</div>
            <div class="category">Customer Relationship Management</div>
        </div>
    </div>
</a> 
    <a href="https://docs.clevertap.com/docs/salesforce-via-zapier">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/182f0d5e0bd94dfa620de3a37f1796225bf374c8c28e897824595944ecb299e2-salesforce-logo.webp" alt="Salesforce CRM" class="logo">
        </div>
        <div class="content">
            <div class="name">Salesforce CRM</div>
            <div class="category">Customer Relationship Management</div>
        </div>
    </div>
</a>   
    <a href="https://docs.clevertap.com/docs/swipe-pages">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/8350ba1a2b9d505475589a006cdaf87dd89758e86e7b0d89f1b811f55109bf80-Swipe_pages_.jpeg" alt="Swipe Pages" class="logo">
        </div>
        <div class="content">
            <div class="name">Swipe Pages</div>
            <div class="category">Customer Relationship Management</div>
        </div>
      </div>
</a> 
     <a href="https://docs.clevertap.com/docs/zoho-form-via-zapier">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/f2a740fc65ddfd062d764e81df32348c10f6d2bd6046bdabca1e2ac098b3ba5e-zoho_logo.jpeg" alt="Zoho Form" class="logo">
        </div>
        <div class="content">
            <div class="name">Zoho Form</div>
            <div class="category">Customer Relationship Management</div>
        </div>
    </div>
      </a>
  </div>
</body>
</html>      
`}</HTMLBlock>

# Customer Data Platform

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
   <a href="https://docs.clevertap.com/docs/boltic">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/73eb8e105854e65661befef9bcf2ce62621cb451bb895ca3eee0ee5599a8e7f1-boltic_logo.webp" alt="Boltic" class="logo">
        </div>
        <div class="content">
            <div class="name">Boltic</div>
            <div class="category">Customer Data Platform</div>
        </div>
    </div>
</a>      
  <a href="https://docs.clevertap.com/docs/census">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/716b768699d89bfcd39f879b5177c056e37cfd7b44d8c01debd34bd78d6bf736-Census.jpeg" alt="Census" class="logo">
        </div>
        <div class="content">
            <div class="name">Census</div>
            <div class="category">Customer Data Platform</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/hightouch">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/0d223308a7381e461315d3e21a6298699ad3cd135b060ae328c9593852fc1154-Hightouch.jpeg" alt="Hightouch" class="logo">
        </div>
        <div class="content">
            <div class="name">Hightouch</div>
            <div class="category">Customer Data Platform</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/mparticle-2">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/937f6e9417ec3511d650a487fbb499984e6c162c0b8e3def342dadd343e2e46d-mParticle.png" alt="mParticle" class="logo">
        </div>
        <div class="content">
            <div class="name">mParticle</div>
            <div class="category">Customer Data Platform</div>
        </div>
    </div>
</a>

<a href="https://developer.clevertap.com/docs/rudderstack">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/64575102b5ccac664d6757f23bcae33e7f1eed6d264061fdfa0bbb97528c8e84-RudderStack_Symbol_0.svg" alt="RudderStack" class="logo">
        </div>
        <div class="content">
            <div class="name">RudderStack</div>
            <div class="category">Customer Data Platform</div>
        </div>
    </div>
</a>

<a href="https://developer.clevertap.com/docs/segment">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/23acd4b1d664a001eb0d7212381744cb5a959237c6e64c9f25eb7a2c3c6497e2-Segment_Symbol_0.svg" alt="Segment" class="logo">
        </div>
        <div class="content">
            <div class="name">Segment</div>
            <div class="category">Customer Data Platform</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/treasuredata-cdp">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/ecd32ffc1a6936da60649274cf5dab0cdee6fe58ea6d33334f67e143c4a479e9-Treasure_Data_idr5-pui94_1.png" alt="Treasure Data" class="logo">
        </div>
        <div class="content">
            <div class="name">Treasure Data</div>
            <div class="category">Customer Data Platform</div>
        </div>
    </div>
</a>
    </div>
</body>
</html>
`}</HTMLBlock>

# Data Warehouse

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
   <a href="https://docs.clevertap.com/docs/amazon-eventbridge">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/93783ddfa75cf49849085df73055ed5648715c6e5986cda3a2a1c5713ef79b5d-AWS_S3_Eventbridge.jpeg" alt="Amazon EventBridge" class="logo">
        </div>
        <div class="content">
            <div class="name">Amazon EventBridge</div>
            <div class="category">Data Warehouse</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/data-export-to-aws-s3">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/93783ddfa75cf49849085df73055ed5648715c6e5986cda3a2a1c5713ef79b5d-AWS_S3_Eventbridge.jpeg" alt="AWS S3 Export" class="logo">
        </div>
        <div class="content">
            <div class="name">AWS S3 Export</div>
            <div class="category">Data Warehouse</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/bigquery">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/64b5008bd247a0d67e3d8a777a71cc40542c23ff8a2f9baf10a417ff94dad2f7-BigQuery.png" alt="BigQuery" class="logo">
        </div>
        <div class="content">
            <div class="name">BigQuery</div>
            <div class="category">Data Warehousing</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/data-export-to-gcp">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/5d8f65d75d9cfaa7c388beb52805563d3ac83b071eee9ad0138afd672d275577-Google_Cloud_Platform.webp" alt="Google Cloud Platform" class="logo">
        </div>
        <div class="content">
            <div class="name">Google Cloud Platform (GCP)</div>
            <div class="category">Data Warehouse</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/microsoft-azure">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/8507d14dd44a824a548d802a530aafde484834cb5f7ccaac3fdbae692fccdaa6-Microsoft_Azure_Portal_idc8nWN0hO_0.svg" alt="Microsoft Azure" class="logo">
        </div>
        <div class="content">
            <div class="name">Microsoft Azure</div>
            <div class="category">Data Warehouse</div>
        </div>
    </div>
</a>
<a href="https://docs.clevertap.com/docs/nexla">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/0f370a30b8470d070aa47d30196b63c70a24a56dfd23c5d8cecd0d2bc367ddcb-nexla_logo_1.jpeg" alt="Nexla" class="logo">
        </div>
        <div class="content">
            <div class="name">Nexla</div>
            <div class="category">Data Warehouse</div>
        </div>
    </div>
</a>
    </div>
</body>
</html>
`}</HTMLBlock>

# Direct Mail

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
<a href="https://docs.clevertap.com/docs/inkit">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/dfb2f5e69b57bbb3696d1ba796f4211501cc7a0647b8806542f89fbd7f546c75-inkit_logo.jpeg" alt="Inkit" class="logo">
        </div>
        <div class="content">
            <div class="name">Inkit</div>
            <div class="category">Direct Mail</div>
        </div>
    </div>
</a>
    <a href="https://docs.clevertap.com/docs/optilyz">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/0ebd7107a2d691d9c0986fb1926f56b24734523ce9a3df4d47d779dc095dd9ec-optilyz_logo.jpeg" alt="Optilyz" class="logo">
        </div>
        <div class="content">
            <div class="name">Optilyz</div>
            <div class="category">Direct Mail</div>
        </div>
    </div>
 </a>
    <a href="https://docs.clevertap.com/docs/poplar">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/ddb7de4000c3ebfe126dd906ea5a783f1b5fe67ea1a0eca6e2c4a1132e7b7412-Poplar.jpeg" alt="Poplar" class="logo">
        </div>
        <div class="content">
            <div class="name">Poplar</div>
            <div class="category">Direct Mail</div>
        </div>
    </div>
</a>
    </div>
</body>
</html>
`}</HTMLBlock>

# Dynamic Content

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
 </a>            
   <a href="https://docs.clevertap.com/docs/blayer">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/f59dbfaee0df1c37839315b78cba238c61e22dac450916e6434f85c33c68a8b2-blayerrr.png" alt="blayer" class="logo">
        </div>
        <div class="content">
            <div class="name">B.Layer</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>
  </a>  
   <a href="https://docs.clevertap.com/docs/blitzllama">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/0725c003f234442a3b12e072bd053a2235c66d38d0a4bcf6e1e41fe5b80a7895-blitz_llama_logo.jpeg" alt="Blitzllama" class="logo">
        </div>
        <div class="content">
            <div class="name">Blitzllama</div>
            <div class="category">Dynamic Content</div>
        </div>
     </div>    
 </a>     
 <a href="https://docs.clevertap.com/docs/contentful">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/ede8e689e31bb2cd9c3572905df1012f4be29d9f1742cd1ea852823a03b2edb8-contentful_logo.jpeg" alt="Contentful" class="logo">
        </div>
        <div class="content">
            <div class="name">Contentful</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>  
 </a>    
   <a href="https://docs.clevertap.com/docs/delighted">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/1a227765cad4f5f276b85ac7fa197e41a98b3f481a8f4691615a9e8730cea99e-delighted-logo-png_seeklogo-273029.png" alt="Delighted" class="logo">
        </div>
        <div class="content">
            <div class="name">Delighted</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>  
 </a>  
   <a href="https://docs.clevertap.com/docs/jasper-ai">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/81bd765584235c518081a163da731d67f41be31480397e37535d8657d01752e9-Jasper_idA3cdDJZy_1.png" alt="Jasper AI" class="logo">
        </div>
        <div class="content">
            <div class="name">Jasper AI</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>
</a>      
   <a href="https://docs.clevertap.com/docs/litmus">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/a03b1a6fa2c872846bcec48a5e30ef62efde09806be36154064e6464249c92f1-litmus.png" alt="Litmus" class="logo">
        </div>
        <div class="content">
            <div class="name">Litmus</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>
 </a>       
   <a href="https://docs.clevertap.com/docs/typeform">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/c04730d8c62f34e618d9520c6a540cc8f96cd344ebb5e424a57c2537436da1c7-Typeform.png" alt="Typeform" class="logo">
        </div>
        <div class="content">
            <div class="name">Typeform</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>
 </a>       
   <a href="https://docs.clevertap.com/docs/movable-ink">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/72127c0fe4129e7befc081c092c166e4534978800e30ae56486c15112a86ec67-movable_ink_logo.jpeg" alt="Movable Ink" class="logo">
        </div>
        <div class="content">
            <div class="name">Movable Ink</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>
  </a>                              
   <a href="https://docs.clevertap.com/docs/niftyimages">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/4e3ac1309abb5449bbfa59cc44e08d38a2f258ae439217f129f8a6cb41dc3b73-niftimages_logo.jpeg" alt="NiftyImages" class="logo">
        </div>
        <div class="content">
            <div class="name">NiftyImages</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>
  </a>             
   <a href="https://docs.clevertap.com/docs/playable">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/5895d2c0a6711ae3ab9f101be28bf9182d82b29d24fe73ec6e94dcb589a3c8de-1631337387371.jpeg" alt="Playable" class="logo">
        </div>
        <div class="content">
            <div class="name">Playable</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>
 </a>
     <a href="https://docs.clevertap.com/docs/qualtrics">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/6944c53ee9595f51c84ea8014ab2988822104b10fccab89c4536c07d32a28dfc-qualtrics_logo.jpeg" alt="Qualtrics" class="logo">
        </div>
        <div class="content">
            <div class="name">Qualtrics</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>
</a>                    
   <a href="https://docs.clevertap.com/docs/quickads">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/bd7b312321f8ee5116429ff099f10001113f4350235a5861f8dd16b58dfcb266-Quickads.png.avif" alt="Quickads" class="logo">
        </div>
        <div class="content">
            <div class="name">Quickads</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div> 
</a>    
  <a href="https://docs.clevertap.com/docs/reignite">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/0b10fdf0e16e488b7654dc3aebc7a4b2951d7a1b3663678924adb2fe188fdd98-Reignite.jpeg" alt="Reignite" class="logo">
        </div>
        <div class="content">
            <div class="name">Reignite</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>
</a>      
   <a href="https://docs.clevertap.com/docs/rocketium">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/90a1d2728b8ebe972fc5aaf1be64ef17722234c336bbae843cf801fc919c1da3-Rocketium_Logo_2023.png" alt="rocketium" class="logo">
        </div>
        <div class="content">
            <div class="name">Rocketium</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>
</a>      
   <a href="https://docs.clevertap.com/docs/sendtric">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/375a1b7c88c379fb82a44b45ad331b21e37c24c15a74fb38efb2fd7304216b85-idxIcP7ufY_logos.jpeg" alt="Sendtric" class="logo">
        </div>
        <div class="content">
            <div class="name">Sendtric</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>
 </a> 
   <a href="https://docs.clevertap.com/docs/squarespace">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/909c405190a2d2403b146595b05d5ecb90b734b244200ce188488cd435736fa6-squarespace_logo.jpeg" alt="SquareSpace" class="logo">
        </div>
        <div class="content">
            <div class="name">SquareSpace</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>
</a>
     <a href="https://docs.clevertap.com/docs/storylane">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/9eb14129191cfd3f3a65ffd2a7e854d487dfdf1b4af88f157c8d1321a23c84aa-Storylane.png" alt="Storylane" class="logo">
        </div>
        <div class="content">
            <div class="name">Storylane</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>
</a>      
   <a href="https://docs.clevertap.com/docs/storyly">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/e03ffe21e4cb257fa8239401afb55a0107b184f71794d4a9f97445a8d133e704-Storyly.jpeg" alt="Storyly" class="logo">
        </div>
        <div class="content">
            <div class="name">Storyly</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>
 </a>
    <a href="https://docs.clevertap.com/docs/surveymonkey">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/c938d864e846eb62aa7ab50ad8c31c58598ccfd373f7a768a7a296f0b2310e91-unnamed.png" alt="SurveyMonkey" class="logo">
        </div>
        <div class="content">
            <div class="name">SurveyMonkey</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>
  </a>
</a>
    <a href="https://docs.clevertap.com/docs/surveysparrow">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/0b14518af5a6b7efe174e7717401d23e2e83b89efb91860cfa37c31c94a49b11-surveysparrow_logo.jpeg" alt="SurveySparrow" class="logo">
        </div>
        <div class="content">
            <div class="name">SurveySparrow</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>
</a>
    <a href="https://docs.clevertap.com/docs/wove">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/48f0b4f943c7a80740bfc408e0595683982ec73a843c028912536514d8b58415-with_wove_logo.jpeg" alt="Wove" class="logo">
        </div>
        <div class="content">
            <div class="name">Wove</div>
            <div class="category">Dynamic Content</div>
        </div>
    </div>
</a>
    </div>
</body>
</html>
`}</HTMLBlock>

# E-Commerce

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
   <a href="https://docs.clevertap.com/docs/shopify">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/5bed2229829e9411ff820f536a100b9592c2eb0d6136109dba98561115e0fb69-Shopify.com_Symbol_0.svg" alt="Shopify" class="logo">
        </div>
        <div class="content">
            <div class="name">Shopify</div>
            <div class="category">E-Commerce</div>
        </div>
    </div>
</a>
    </div>
</body>
</html>
`}</HTMLBlock>

# Email

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
   <a href="https://docs.clevertap.com/docs/amazon-simple-email-service">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/f7b8c289ace53bf772fc0a8b13ad3a47470e9800bda44e6c1aab9ac9b8e13f1f-Simple_Email_Service.png" alt="Amazon Simple Email Service" class="logo">
        </div>
        <div class="content">
            <div class="name">Amazon Simple Email Service</div>
            <div class="category">Email</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/mandrill">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/f025167126f2b07919e65afb6a72c9c0ade83a75c6190384aded79d3343d1654-Mandrill.jpeg" alt="Mandrill" class="logo">
        </div>
        <div class="content">
            <div class="name">Mandrill</div>
            <div class="category">Email</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/postmark">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/572f6c80eb6165130396b72959d420323abe3017ab6f3f7a3994f7221de0cb93-Postmark.png" alt="Postmark" class="logo">
        </div>
        <div class="content">
            <div class="name">Postmark</div>
            <div class="category">Email</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/sendgrid">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/50520ec5a42cc4331d440fd5a33ad0247585ae414c75871f118eb87d0b8ba3bb-SendGrid_Symbol_0.svg" alt="SendGrid" class="logo">
        </div>
        <div class="content">
            <div class="name">SendGrid</div>
            <div class="category">Email</div>
        </div>
    </div>
</a>
<a href="https://docs.clevertap.com/docs/deeplinking-with-branch">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/311972c7da6cd9956e8110911d763cb514aa30b6354505c4f6a38aea2f011ef6-Branch_idSRMs7jP1_0.svg" alt="Deeplinking with Branch" class="logo">
        </div>
        <div class="content">
            <div class="name">Deeplinking with Branch</div>
            <div class="category">Email</div>
        </div>
    </div>
</a>
    </div>
</body>
</html>
`}</HTMLBlock>

# Email Validator

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
   <a href="https://docs.clevertap.com/docs/clearout">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/f53513e04b71ff3c0aa016155ecf437f136140cfd060a87c7af6359df8f4b6eb-Clearout.png" alt="Clearout" class="logo">
        </div>
        <div class="content">
            <div class="name">Clearout</div>
            <div class="category">Email Validator</div>
        </div>
    </div>
</a>
   <a href="https://docs.clevertap.com/docs/kickbox">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/fa95947d06d3fbcd09511b0c59fea7546fd26918e45bf5e3c23d14e8c3d1c977-Kickbox.jpeg" alt="KickBox" class="logo">
        </div>
        <div class="content">
            <div class="name">KickBox</div>
            <div class="category">Email Validator</div>
        </div>
    </div>
</a>
    </div>
</body>
</html>
`}</HTMLBlock>

# Email Template

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
        <a href="https://docs.clevertap.com/docs/alpaco">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/cba5ecc0e9daae8fc9d67eeac84db611c442f677905ad89f7a97870c12074922-contact_3qovrm0f_1.jpg" alt="Alpaco" class="logo">
        </div>
        <div class="content">
            <div class="name">Alpaco</div>
            <div class="category">Email Template</div>
        </div>
    </div>
 </a>
        <a href="https://docs.clevertap.com/docs/email-love">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/b4d0bd4826523fb395d8c516d26a8d22ef0f5c95d2f127a31d11a62f02b07e0f-email_love_logo.jpeg" alt="Email Love" class="logo">
        </div>
        <div class="content">
            <div class="name">Email Love</div>
            <div class="category">Email Template</div>
        </div>
    </div>
</a>
   <a href="https://docs.clevertap.com/docs/stripo">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/5ff9d0c27b076734f3b800277a4cb104730f07c6d4181265170fe917666a08dd-Stripo.jpeg" alt="stripo" class="logo">
        </div>
        <div class="content">
            <div class="name">Stripo</div>
            <div class="category">Email Template</div>
        </div>
    </div>
</a>
      <a href="https://docs.clevertap.com/docs/taxi-for-email">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/dde396ef5ccd49f3346ade3aaf754d65e751938a12c463bd24b14e9d034a247a-Taxi_for_Email.jpeg" alt="Taxi for Email" class="logo">
        </div>
        <div class="content">
            <div class="name">Taxi for Email</div>
            <div class="category">Email Template</div>
        </div>
    </div>
</a>
    </div>
</body>
</html>
`}</HTMLBlock>

# Localization

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
   <a href="https://docs.clevertap.com/docs/crowdin">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/0b8af82f6aa48ed325357cd7b7ac6106a0a43563407d10dede8abc62d02cba55-Crowdin.jpeg" alt="Crowdin" class="logo">
        </div>
        <div class="content">
            <div class="name">Crowdin</div>
            <div class="category">Localization</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/lokalise">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/a80f7428262717774b0bfe20148e67fc42e5e56a1d2e7b0afc9d536249dcb34d-Lokalise_idlLZ8_ln3_0.svg" alt="Lokalise" class="logo">
        </div>
        <div class="content">
            <div class="name">Lokalise</div>
            <div class="category">Localization</div>
        </div>
    </div>
</a>
    </div>
</body>
</html>
`}</HTMLBlock>

# Loyalty

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
   <a href="https://docs.clevertap.com/docs/loyalty-lion">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/4a3ae6b11f703250eb6a26a0e6bc0db8cd7712365185dda30ddd1250e5d91a92-loyaltylion_logo.jpeg" alt="Loyalty Lion" class="logo">
        </div>
        <div class="content">
            <div class="name">Loyalty Lion</div>
            <div class="category">Loyalty</div>
        </div>
    </div>
</a>      
   <a href="https://docs.clevertap.com/docs/talonone">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/0b8dabb5155d5a9d9d9901a1236fc3691cf193f580643f1759fb89142900168a-Talon.One.png" alt="Talon.One" class="logo">
        </div>
        <div class="content">
            <div class="name">Talon.One</div>
            <div class="category">Loyalty</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/voucherify">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/fd42cbb0b92d6ae2159e0707bdf740f903e1d0bb07215b2ae38d172b0dea7f0d-Voucherify.jpeg" alt="Voucherify" class="logo">
        </div>
        <div class="content">
            <div class="name">Voucherify</div>
            <div class="category">Loyalty</div>
        </div>
    </div>
</a>
      
<a href="https://docs.clevertap.com/docs/yotpo">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/f5b3186e92f79896cd7af4d46a4d044791a2a9950fb17cc139f44845bfd313f3-images_2.png" alt="Yotpo" class="logo">
        </div>
        <div class="content">
            <div class="name">Yotpo</div>
            <div class="category">Loyalty</div>
        </div>
    </div>
</a>        
    </div>
</body>
</html>
`}</HTMLBlock>

# Messenger

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
   <a href="https://docs.clevertap.com/docs/discord">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/c365e9317b6d60c493d0cf7ca6f651fa4d542309f551740056d422d1a8c62631-discord_logo.jpeg" alt="Discord" class="logo">
        </div>
        <div class="content">
            <div class="name">Discord</div>
            <div class="category">Messenger</div>
        </div>
    </div>
</a>
<a href="https://docs.clevertap.com/docs/line-messenger">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/0ec3dc2ff75c076e12f5969e4f47bd9c193f9914ff8989a29e89cf7dadba1951-line.png" alt="LINE" class="logo">
        </div>
        <div class="content">
            <div class="name">LINE</div>
            <div class="category">Messenger</div>
        </div>
    </div>
</a>
<a href="https://docs.clevertap.com/docs/slack">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/75472ff3623453c9f15e3a9c9abfca5f9548b7dece4c70f4a5818a55161e79d7-Slack_icon_2019.svg.png" alt="Slack" class="logo">
        </div>
        <div class="content">
            <div class="name">Slack</div>
            <div class="category">Messenger</div>
        </div>
    </div>
</a>
      <a href="https://docs.clevertap.com/docs/sendbird-business-messaging">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/b9304e06560e5b56147bc6ab80e2711386f1dfa56a63a1edd70f248adb931a7b-Sendbird.jpeg" alt="Sendbird" class="logo">
        </div>
        <div class="content">
            <div class="name">Sendbird</div>
            <div class="category">Messenger</div>
        </div>
    </div>
 </a>
   <a href="https://docs.clevertap.com/docs/telegram-messenger">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/dd930dccf4b0b105a8c946452a34382d946658d5b4562f0ed3ce3ef90ab15e75-LRDASku7_400x400.jpg" alt="Telegram Messenger" class="logo">
        </div>
        <div class="content">
            <div class="name">Telegram Messenger</div>
            <div class="category">Messenger</div>
        </div>
    </div>
</a>
    </div>
</body>
</html>
`}</HTMLBlock>

# Payments

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
   <a href="https://docs.clevertap.com/docs/purchasely">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/0ccd4b6dbcdae6d85df14e72b18248f4e8d2147821ea479589657e38f7c19d7b-Purchesly.png" alt="Purchasely" class="logo">
        </div>
        <div class="content">
            <div class="name">Purchasely</div>
            <div class="category">Payments</div>
        </div>
    </div>
 </a> 
   <a href="https://docs.clevertap.com/docs/qonversion">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/cfd39d9ccadfb9a7045e4807e1fb3658e8174ce8605cfea1ec4a8e73e926d23d-qonversion_logo.jpeg" alt="Qonversion" class="logo">
        </div>
        <div class="content">
            <div class="name">Qonversion</div>
            <div class="category">Payments</div>
        </div>
    </div>
</a>     
   <a href="https://docs.clevertap.com/docs/revenuecat">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/0c64232782e0973162f1b629425b5fafee30b3aafc2e5566ff125a2b8e6665e0-RevenueCat.jpeg" alt="RevenueCat" class="logo">
        </div>
        <div class="content">
            <div class="name">RevenueCat</div>
            <div class="category">Payments</div>
        </div>
    </div>
</a>
    </div>
</body>
</html>
`}</HTMLBlock>

# Remarketing

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
   <a href="https://docs.clevertap.com/docs/facebook-audience-network-1">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/ce9618bf8a67a2eb1cb026cb8603318b81b8218562fa805c333c531403a2a4c9-Facebook_Symbol_0.svg" alt="Facebook Audience Network" class="logo">
        </div>
        <div class="content">
            <div class="name">Facebook Audience Network</div>
            <div class="category">Remarketing</div>
        </div>
    </div>
</a>
      <a href="https://docs.clevertap.com/docs/facebook-lead-ads-via-zapier">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/ce9618bf8a67a2eb1cb026cb8603318b81b8218562fa805c333c531403a2a4c9-Facebook_Symbol_0.svg" alt="Facebook Lead Ads" class="logo">
        </div>
        <div class="content">
            <div class="name">Facebook Lead Ads</div>
            <div class="category">Remarketing</div>
        </div>
    </div>
</a>
<a href="https://docs.clevertap.com/docs/google-adwords-remarketing">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/80939fd90693533ee04dc1c06c9fe653386a05712a689ca2aad26fd52b9263ee-Google_Ads.jpeg" alt="Google Ads Remarketing" class="logo">
        </div>
        <div class="content">
            <div class="name">Google Ads</div>
            <div class="category">Remarketing</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/tiktok-remarketing-1">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/14ea9f0f2d1b3edd08dc3ee8df7592acce126e6db2121b7c29e8f72cc5a8b409-TikTok_Logo_Alternative_0.svg" alt="TikTok Remarketing" class="logo">
        </div>
        <div class="content">
            <div class="name">TikTok Remarketing</div>
            <div class="category">Remarketing</div>
        </div>
    </div>
</a>
    </div>
</body>
</html>
`}</HTMLBlock>

# SMS

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
<a href="https://docs.clevertap.com/docs/8x8-sms">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/dc09a5f5d7e04d537513a570343b5037be5c293b103dffb3ae3146c8851e3090-8x8-logo-01.png" alt="8x8" class="logo">
        </div>
        <div class="content">
            <div class="name">8x8</div>
            <div class="category">SMS</div>
        </div>
    </div>
      </a>
   <a href="https://docs.clevertap.com/docs/azmarq">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/a78a5c7b07a35c7f2a30ff78d6375445af4bd1634f8425a95a44772d9c309607-Azmarq.jpeg" class="logo">
        </div>
        <div class="content">
            <div class="name">Azmarq</div>
            <div class="category">SMS</div>
        </div>
    </div>
</a>      
   <a href="https://docs.clevertap.com/docs/generic-sms">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/c75a975ae4ba728b9d8f80ea1fd710f1d69f33bb2e9d0b0b373226c5044c9762-BulkSMS.jpeg" alt="BulkSMS" class="logo">
        </div>
        <div class="content">
            <div class="name">BulkSMS</div>
            <div class="category">SMS</div>
        </div>
    </div>
      </a>
<a href="https://docs.clevertap.com/docs/enablex">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/e22bd74cd415e63cdd6e09a8d196b1406acac9989b040d0973d183d7020ed045-EnableX.png" alt="EnableX" class="logo">
        </div>
        <div class="content">
            <div class="name">EnableX</div>
            <div class="category">SMS</div>
        </div>
    </div>
</a>
<a href="https://docs.clevertap.com/docs/exotel">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/89a86c79cf4fe27f746a979545dffce12dc4292a2e42cfc3607aba2cf1315b02-Exotel.jpeg" alt="Exotel" class="logo">
        </div>
        <div class="content">
            <div class="name">Exotel</div>
            <div class="category">SMS</div>
        </div>
    </div>
</a>
<a href="https://docs.clevertap.com/docs/ics-mobile">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/3efc20521ab132c9038b5a687fa7a29edef7d065ef3134f7bdb5ca56852a33ea-ics_logo.webp" alt="ICS Mobile" class="logo">
        </div>
        <div class="content">
            <div class="name">ICS Mobile</div>
            <div class="category">SMS</div>
        </div>
    </div>
</a>   
<a href="https://docs.clevertap.com/docs/infobip-sms">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/8f8fb96c455eedc6728f420f2b1aba195a148bbfc07cc20f4721a4e3fbc1a802-Infobip_id8JKsF2ld_0.svg" alt="Infobip" class="logo">
        </div>
        <div class="content">
            <div class="name">Infobip</div>
            <div class="category">SMS</div>
        </div>
    </div>
      </a>
      </a>
<a href="https://docs.clevertap.com/docs/kaleyra-sms">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/5c1d4b35de4b78d5cf5e97bd7bea915847e9507f8d24486c377c7ea590b5adaa-Kaleyra.jpeg" alt="Kaleyra SMS" class="logo">
        </div>
        <div class="content">
            <div class="name">Kaleyra</div>
            <div class="category">SMS</div>
        </div>
    </div>
  </a>
<a href="https://docs.clevertap.com/docs/message-central">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/f6285129192afda457981b3134fb5bf7f0bcc9d6c81e84979fc81ca0a9caddb8-Message_Central_.jpeg" alt="Infobip" class="logo">
        </div>
        <div class="content">
            <div class="name">Message Central</div>
            <div class="category">SMS</div>
        </div>
    </div>
<a href="https://docs.clevertap.com/docs/msg91">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/4c7f4dfa7b7e264c616f1ebf7ddbd6da15238eb1585e12287eef47a70070bd94-MSG91.png" alt="MSG91" class="logo">
        </div>
        <div class="content">
            <div class="name">MSG91</div>
            <div class="category">SMS</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/netcore">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/17b93b939ba0a468beb925a169a371cd811f55f415aa5a7828f126c03a912dc9-Netcore_Cloud_idB8rkalPb_0.svg" alt="Netcore" class="logo">
        </div>
        <div class="content">
            <div class="name">Netcore</div>
            <div class="category">SMS</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/nexmo">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/dfed8a138edd91e7da9627c3c45a7c15968897031e15a4125c80457aea0be73d-Nexmo.png" alt="Nexmo/Vonage" class="logo">
        </div>
        <div class="content">
            <div class="name">Nexmo/Vonage</div>
            <div class="category">SMS</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/generic-sms">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/f114f9b46a74e7753c5be56aac3c04634e8ce62c8c03731686a6d162cdba5db4-Nimbus_SMS.jpeg" alt="Nimbus SMS" class="logo">
        </div>
        <div class="content">
            <div class="name">Nimbus</div>
            <div class="category">SMS</div>
        </div>
    </div>
</a>
<a href="https://docs.clevertap.com/docs/onextel-sms">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/0c2d7328403509990400bdc186f722f9cf30bcaf481cb29576b6c88defb6f4ce-OneXtel_logo.jpg" alt="OneXtel" class="logo">
        </div>
        <div class="content">
            <div class="name">OneXtel</div>
            <div class="category">SMS</div>
        </div>
    </div>
</a>
<a href="https://docs.clevertap.com/docs/generic-sms">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/eba88cb6c54c161ff4e417acdd71e75413d9f33eab53bd02add25c1b3e23b944-Plivo.jpeg" alt="Plivo" class="logo">
        </div>
        <div class="content">
            <div class="name">Plivo</div>
            <div class="category">SMS</div>
        </div>
    </div>
 </a>
<a href="https://docs.clevertap.com/docs/route-mobile-sms">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/fa59938b06ba7bbb7c9c7cf07d9639da4bfe63b6c0b9b4f27808322a714851f9-images.jpeg" alt="Route Mobile" class="logo">
        </div>
        <div class="content">
            <div class="name">Route Mobile</div>
            <div class="category">SMS</div>
        </div>
    </div>
</a>      
<a href="https://docs.clevertap.com/docs/sinch-sms">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/3cac1aa682ee81cadb4f38660b5af36a8df8328e2ac03e08c8c6cdc4b1d14a13-sinch_logomark_black.svg" alt="Sinch SMS" class="logo">
        </div>
        <div class="content">
            <div class="name">Sinch</div>
            <div class="category">SMS</div>
        </div>
    </div>
      </a>
   <a href="https://docs.clevertap.com/docs/sms-gateway-center">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/f434ff3e5b9327c141dd3e8f9f0951ed054c938e77923005eb53f36a293bb83b-sms_gateway_center.png" alt="SMS Gateway Center" class="logo">
        </div>
        <div class="content">
            <div class="name">SMS Gateway Center</div>
            <div class="category">SMS</div>
        </div>
    </div>
</a>   
<a href="https://docs.clevertap.com/docs/generic-sms">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/c0d1e9a5f1f7f36f807a2c27bf1ed65435730e321e61a33e758a1f93a52fe9a5-SMSINDIAHUB.png" alt="SMSINDIAHUB" class="logo">
        </div>
        <div class="content">
            <div class="name">SMSINDIAHUB</div>
            <div class="category">SMS</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/generic-sms">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/1f2a9cbaa50afb424a71f3a29df3e5ddcbbcd1baf65aac6270622d8b271481f1-TextLocal.jpeg" alt="TextLocal" class="logo">
        </div>
        <div class="content">
            <div class="name">TextLocal</div>
            <div class="category">SMS</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/times-mobile">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/e8484000bcf1c84dbf071c91110c800b9125dee65d53b06a8871465672aa7b2d-TimesMobile.webp" alt="Times Mobile" class="logo">
        </div>
        <div class="content">
            <div class="name">Times Mobile</div>
            <div class="category">SMS</div>
        </div>
    </div>
</a>

<a href="https://docs.clevertap.com/docs/twilio">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/fff6322c139e023770b83e4c0e7d8660178446edf62c842683f2f86877a74152-Twilio_idseuPD28S_0.svg" alt="Twilio" class="logo">
        </div>
        <div class="content">
            <div class="name">Twilio</div>
            <div class="category">SMS</div>
        </div>
    </div>
      </a> 
  <a href="https://docs.clevertap.com/docs/valuefirst">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/30a62a4262cb44c4627f25f62d6a39a458469b0c2ae1721091d9ddc5d9935323-VFirst.jpeg" alt="ValueFirst" class="logo">
        </div>
        <div class="content">
            <div class="name">ValueFirst</div>
            <div class="category">SMS</div>
        </div>
    </div>
</a>
    </div>
</body>
</html>
`}</HTMLBlock>

# Support

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
   <a href="https://docs.clevertap.com/docs/zendesk">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/9222da2a1de0404917acf81a88b05ab8e56881e630ce139976d73eaab562aa7f-Zendesk_Symbol_0.svg" alt="Zendesk" class="logo">
        </div>
        <div class="content">
            <div class="name">Zendesk</div>
            <div class="category">Support</div>
        </div>
    </div>
</a>
  </div>
</body>
</html>
`}</HTMLBlock>

# WhatsApp

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
<a href="https://docs.clevertap.com/docs/8x8-whatsapp">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/dc09a5f5d7e04d537513a570343b5037be5c293b103dffb3ae3146c8851e3090-8x8-logo-01.png" alt="8x8" class="logo">
        </div>
        <div class="content">
            <div class="name">8x8</div>
            <div class="category">WhatsApp</div>
        </div>
    </div>
 </a>
<a href="https://docs.clevertap.com/docs/aisensy">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/2196859b649c96a58cb566b43e81c2f9a8dd0ff02906db88af67aac167b10d23-aisensyofficial_logo.jpeg" alt="AiSensy" class="logo">
        </div>
        <div class="content">
            <div class="name">AiSensy</div>
            <div class="category">WhatsApp</div>
        </div>
    </div>
</a>
 <a href="https://docs.clevertap.com/docs/exotel-whatsapp">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/89a86c79cf4fe27f746a979545dffce12dc4292a2e42cfc3607aba2cf1315b02-Exotel.jpeg" alt="Exotel" class="logo">
        </div>
        <div class="content">
            <div class="name">Exotel</div>
            <div class="category">WhatsApp</div>
        </div>
    </div>
</a> 
<a href="https://docs.clevertap.com/docs/gupshup">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/4139ddd02258c0a239367f32365c632040dd4bdcb0fe0743f9f4eec15fb5d828-Gupshup_copy.jpeg" alt="Gupshup" class="logo">
        </div>
        <div class="content">
            <div class="name">Gupshup</div>
            <div class="category">WhatsApp</div>
        </div>
    </div>
</a>
<a href="https://docs.clevertap.com/docs/haptik">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/dc37a22c8905842aa0548a7d6d37a0d0b776e9733a642a47ed914d3dc9bf03df-handlogo-1-2.png.webp" alt="Haptik" class="logo">
        </div>
        <div class="content">
            <div class="name">Haptik</div>
            <div class="category">WhatsApp</div>
        </div>
    </div>
</a>     
<a href="https://docs.clevertap.com/docs/infobip">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/8f8fb96c455eedc6728f420f2b1aba195a148bbfc07cc20f4721a4e3fbc1a802-Infobip_id8JKsF2ld_0.svg" alt="Infobip" class="logo">
        </div>
        <div class="content">
            <div class="name">Infobip</div>
            <div class="category">WhatsApp</div>
        </div>
    </div>
</a>
<a href="https://docs.clevertap.com/docs/interakt">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/54812352e5866d1fbc65d8b3e16c3d3bdb754742e2cb7f537c15ecff9626ffcb-Interakt.png" alt="Interakt" class="logo">
        </div>
        <div class="content">
            <div class="name">Interakt</div>
            <div class="category">WhatsApp</div>
        </div>
    </div>
</a>     
<a href="https://docs.clevertap.com/docs/kaleyra">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/5c1d4b35de4b78d5cf5e97bd7bea915847e9507f8d24486c377c7ea590b5adaa-Kaleyra.jpeg" alt="Kaleyra" class="logo">
        </div>
        <div class="content">
            <div class="name">Kaleyra</div>
            <div class="category">WhatsApp</div>
        </div>
    </div>
</a>
   <a href="https://docs.clevertap.com/docs/msg91-whatsapp">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/4c7f4dfa7b7e264c616f1ebf7ddbd6da15238eb1585e12287eef47a70070bd94-MSG91.png" alt="MSG91" class="logo">
        </div>
        <div class="content">
            <div class="name">MSG91</div>
            <div class="category">WhatsApp</div>
        </div>
    </div>
</a>      
<a href="https://docs.clevertap.com/docs/nexmo-whatsapp">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/dfed8a138edd91e7da9627c3c45a7c15968897031e15a4125c80457aea0be73d-Nexmo.png" alt="Nexmo" class="logo">
        </div>
        <div class="content">
            <div class="name">Nexmo</div>
            <div class="category">WhatsApp</div>
        </div>
    </div>
</a>     
   <a href="https://docs.clevertap.com/docs/onextel-whatsapp">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/0c2d7328403509990400bdc186f722f9cf30bcaf481cb29576b6c88defb6f4ce-OneXtel_logo.jpg" alt="OneXtel" class="logo">
        </div>
        <div class="content">
            <div class="name">OneXtel</div>
            <div class="category">WhatsApp</div>
        </div>
    </div>
 </a>  
   <a href="https://docs.clevertap.com/docs/pingbix">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/e8f75344f0c6bc2a194f11308363a215ffb93456b404e4f5a375cc9021714d20-image_9.png" alt="Pingbix" class="logo">
        </div>
        <div class="content">
            <div class="name">Pingbix</div>
            <div class="category">WhatsApp</div>
        </div>
    </div>
 </a>  
     <a href="https://docs.clevertap.com/docs/quickreply">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/1f6f55d5ef53dea3a01e715abedab16db017935cf7de4b15731f02e3d0636155-quickreply_ai_logo.jpeg" alt="QuickReply" class="logo">
        </div>
        <div class="content">
            <div class="name">QuickReply</div>
            <div class="category">WhatsApp</div>
        </div>
      </div>  
</a>   
   <a href="https://docs.clevertap.com/docs/route-mobile">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/fa59938b06ba7bbb7c9c7cf07d9639da4bfe63b6c0b9b4f27808322a714851f9-images.jpeg" alt="Route Mobile" class="logo">
        </div>
        <div class="content">
            <div class="name">Route Mobile</div>
            <div class="category">WhatsApp</div>
        </div>
      </div>  
</a>
   <a href="https://docs.clevertap.com/docs/sinch">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/3cac1aa682ee81cadb4f38660b5af36a8df8328e2ac03e08c8c6cdc4b1d14a13-sinch_logomark_black.svg" alt="Sinch India" class="logo">
        </div>
        <div class="content">
            <div class="name">Sinch</div>
            <div class="category">WhatsApp</div>
        </div>    
                </div>
            </div>
        </a>
    </div>
</body>
</html>
`}</HTMLBlock>

# Workflow Automation

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Integration Grid</title>
    <style>
        * {am
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

       .content-toc.grid-25{
      	display:None;
      }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
       

        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, minmax(350px, 1fr)); /* made the value 350px to make grid 3x3 */
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .integration-card { /* styling for the cards */
            display: flex;
            align-items: center;
            padding: 1.5rem;
            #background: #F5F5F5;
          	background: white;
            border-radius: 12px;
          	min-width:200px;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        .integration-card:hover {
            
            box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.1);
           
        }

        .logo-container {
            display: flex;
            align-items: center;
            padding-right: 1rem;
            border-right: 1px solid rgba(0, 0, 0, 0.1);
            margin-right: 1rem;
            height: 100%;
        }

        .logo { /* logo sizing */
            width: 50px;
            height: 50px;
            object-fit:fill;
            flex-shrink: 0;
            border-radius: 5px;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-width: 0;
            height: 100%;
        }

        .name {
            font-size: 1rem;
            font-weight: 500;
            color: #000;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            margin-bottom: 0.5rem;
        }

        .category {
            font-size: 0.8rem;
            color: #92969f;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

       
/* responsive elements */
        @media (max-width: 768px) {
            .grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    

        @media (max-width: 480px) {
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="grid">
      <!-- use this card below for replication and change the link to the desired one -->
  <a href="https://docs.clevertap.com/docs/airtable">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/188ca5ed90d7628340704344432b9df335b3af85f4d07083f078bbad728286aa-airtable_logo.jpeg" alt="Airtable" class="logo">
        </div>
        <div class="content">
            <div class="name">Airtable</div>
            <div class="category">Workflow Automation</div>
        </div>
    </div>
 </a> 
   <a href="https://docs.clevertap.com/docs/apxor">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/66b6a87819f6f7077af71083824cb52a15330fc20cfd71a283dd094be0f8c297-Apxor.jpeg" alt="Apxor" class="logo">
        </div>
        <div class="content">
            <div class="name">Apxor</div>
            <div class="category">Workflow Automation</div>
        </div>
  </div>
</a>   
 <a href="https://docs.clevertap.com/docs/datachannel">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/b10ff964a41c014c7d6466c815626e09eb30693413cecab4b0b0a3e676392362-mydatachannel_logo.jpeg" alt="DataChannel" class="logo">
        </div>
        <div class="content">
            <div class="name">DataChannel</div>
            <div class="category">Workflow Automation</div>
        </div>
    </div>
</a>
 <a href="https://docs.clevertap.com/docs/n8n">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/870f58ee89caf9207bfd447ca51e300d116d6822cde87e06141668ed6a6fc648-n8n-icon-logo-brandlogos.net_fxs0a1ltj.svg" alt="n8n" class="logo">
        </div>
        <div class="content">
            <div class="name">n8n</div>
            <div class="category">Workflow Automation</div>
        </div>
    </div>
 </a>
<a href="https://docs.clevertap.com/docs/pipedream">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/2461ba9e6b5233e3221e04cdaa86a894857d231d2c6cef10e60f22e09dab1d80-Pipedream.jpeg" alt="Pipedream" class="logo">
        </div>
        <div class="content">
            <div class="name">Pipedream</div>
            <div class="category">Workflow Automation</div>
        </div>
    </div>
</a>
 <a href="https://docs.clevertap.com/docs/sheetdb">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/f5fe97a86c27e955081ae67da59024d0282370f2ee7cf6a6f4708e431de6240d-sheetdb.io.png" alt="SheetDB" class="logo">
        </div>
        <div class="content">
            <div class="name">SheetDB</div>
            <div class="category">Workflow Automation</div>
         </div>
    </div>
</a>
<a href="https://docs.clevertap.com/docs/sheetlabs">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/c255a4d7e0783e426b1bf01eb7cd5f167d905e3f7d83614db18751ae2a788700-sheetlabs.png" alt="Sheetlabs" class="logo">
        </div>
        <div class="content">
            <div class="name">Sheetlabs</div>
            <div class="category">Workflow Automation</div>
         </div>
    </div>
</a>
<a href="https://docs.clevertap.com/docs/smashpops">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/cb48640086300861d82b9aa9cca212d5a5522f3ad858b21865b9d750972e63c4-smashpops_logo.png" alt="Smashpops" class="logo">
        </div>
        <div class="content">
            <div class="name">Smashpops</div>
            <div class="category">Workflow Automation</div>
         </div>
    </div>
</a>
<a href="https://docs.clevertap.com/docs/zapier">
    <div class="integration-card">
        <div class="logo-container">
            <img src="https://files.readme.io/9986166ddfb29f93a834963deb0c216be7c1c20b896a77e06fc2531d4d038b08-Zapier.jpeg" alt="Zapier" class="logo">
        </div>
        <div class="content">
            <div class="name">Zapier</div>
            <div class="category">Workflow Automation</div>
        </div>
    </div>
  </div>
</body>
</html>
`}</HTMLBlock>
