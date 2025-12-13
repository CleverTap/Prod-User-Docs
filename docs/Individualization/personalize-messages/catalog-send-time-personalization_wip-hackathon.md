---
title: Catalog Send-Time Personalization_WIP hackathon
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
REVIEW EXISTING LIVE PAGE AND ASSESS WHAT INFO CAN BE INCORPORATED FROM THE HACKATHON COPY.

Catalog Send Time Personalisation\
Use Case 1: Price changes at send time.\
A grocery app with delivery in New York, Boston, and Washington D.C. would like to dynamically change prices daily to account for fluctuating prices in each market.

Use Case 2: Dynamic images personalization on browse abandonment\
Earlier we were required to pass the dynamic image URL in the event properties of the action event which would need an app update if the properties were not passed. However, we can achieve dynamic images with every message via send time personalization. For PBS campaigns the latest instance of the event will be considered.\
If a user views a product but does not charge in the same product within X minutes, dynamically send the image of the viewed product. You can also pick up the current price to personalize.

Stepwise how-to (Use Case 2, holding the property constant recommended):\
Holding property (product ID) constant ensures that the same product, if dropped off from, is sent as the communication.

Step 1:\
Upload a catalog (Sample available under Account settings-> Catalogs):\
[https://docs.clevertap.com/docs/catalog](https://docs.clevertap.com/docs/catalog)

Identity\
Name\
ImageURL\
Test123\
Adidas Shoes\
[https://images-na.ssl-images-amazon.com/images/I/71rR1V%2B9FqL.\_UY500\_.jpg](https://images-na.ssl-images-amazon.com/images/I/71rR1V%2B9FqL._UY500_.jpg)\
Test456\
Nike Shoes\
[https://s3.amazonaws.com/nikeinc/assets/84925/Sp19\_BB\_Nike\_Adapt\_20181218\_NIKE0538\_Detail5\_rectangle\_1600.jpg?1547068102](https://s3.amazonaws.com/nikeinc/assets/84925/Sp19_BB_Nike_Adapt_20181218_NIKE0538_Detail5_rectangle_1600.jpg?1547068102)\
Test789\
Nike Shirt\
[https://static.nike.com/a/images/t\_default/c456dcbc-203c-4d12-a3f2-b17c408ff5c4/sportswear-t-shirt-0P32gc.jpg](https://static.nike.com/a/images/t_default/c456dcbc-203c-4d12-a3f2-b17c408ff5c4/sportswear-t-shirt-0P32gc.jpg)

You can upload identity as the product ID or any Id that you pass with Add to Cart, name and image URL (this will be the dynamic image URL for every Image)

Step 2:\
Map the property Product ID or any primary unique key with the catalogs identity.

Step 3:\
Create a drop off (inaction) campaign (product viewed but did not do charged) and under image URL, please make use of the following liquid script. Before this, click on ‘personalization setup’ and map the event property. Holding the property constant is recommended.

When you type ' \{\{ ', it will automatically give you a drop-down, select catalog and the name (Our catalog’s name is CSTPTesting\_PA):

Step 4:\
Liquid script for personalization:\
We shall personalize the image here with the image of the product that was abandoned from the cart. Add any default value of an image (pulled out in case that catalog doesn't have the image of that particular item.\
Note: You will need to replace the catalogs regularly for new items.

\{\{ Catalog.CSTPTesting\_PA.ImageURL | default:"[https://static.scientificamerican.com/sciam/cache/file/92E141F8-36E4-4331-BB2EE42AC8674DD3\_source.jpg"](https://static.scientificamerican.com/sciam/cache/file/92E141F8-36E4-4331-BB2EE42AC8674DD3_source.jpg") }}

Step 5:\
Firing the events via API or SDK (done via API here)

Firing product Viewed event.\
\{\
    "d": \[\
        \{\
            "identity": 8926,\
            "type": "event",\
            "evtName":"Product Viewed",\
            "evtData": \{\
                "Name": "Adidas Shoes",\
                "Category":"Footwear",\
                "Product\_ID":"Test123"

```
        }
    }
]
```

}

```
            "d": [
    {
        "identity": 8926,
        "type": "event",
        "evtName":"Product Viewed",
        "evtData": {
            "Name": "Nike Shoes",
            "Category":"Footwear",
            "Product_ID":"Test456"
         
          
        }
    }
]
```

}

Firing Charged event\
\{\
    "d": \[\
        \{\
            "identity": 8926,\
            "type": "event",\
            "evtName":"Charged",\
            "evtData": \{\
                "Name": "Adidas Shoes",\
                "Category":"Footwear",\
                "Product\_ID":"Test123",\
                "Amount":3500

```
        }
    }
]
```

}

Step 6:\
Once this campaign is set, you can test your drop off and you shall receive the image for the product that was dropped off from. (the product ID will be picked up and checked in the catalog and the corresponding image will be shown.)\
How this works: We added two products, nike and adidas, but charged only in adidas within the time. Since property has been held constant, Nike will be shown. 

Adding an example below:
