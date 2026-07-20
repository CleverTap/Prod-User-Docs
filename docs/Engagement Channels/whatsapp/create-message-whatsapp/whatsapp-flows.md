---
title: WhatsApp Flows
excerpt: Create, configure, and launch WhatsApp Flows in CleverTap.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

WhatsApp Flows enable form-based customer workflow using **WhatsApp Direct** for CleverTap users. Users can complete tasks such as product feedback, restaurant reservations, or data capture in a structured manner without leaving WhatsApp. Flows are created at the *WABA (WhatsApp Business Account)* level and are available to every number attached to that WABA. A Flow appears as a CTA button in a WhatsApp message to end users. Tapping the CTA launches the Flow that follows [Meta’s Flows specification](https://developers.facebook.com/docs/whatsapp/flows).

For example, a hotel that requests post-stay feedback from its guests. The hotel sends a WhatsApp message with the CTA **“Share Feedback”**. Tapping this CTA opens a Flow with rating and comments. When the guest submits, CleverTap ingests the response as an event and, if configured, updates the user profile.

Flows apply broadly: *E-commerce* for reviews and purchase intent, *Food & Delivery* for table booking and order feedback, *Fintech* for lead capture and health checks, *Gaming* for tournament registration and reminders, and *Subscriptions* for show recommendations and feedback.

> 📘 Private Beta
>
> WhatsApp Flows is currently in Private Beta. Contact your Customer Success Manager for access.

To help you get started, here’s the high-level flow of tasks you’ll perform:

1. [Choose the correct Setup](#choosing-the-right-setup): Decide how to handle encryption, decryption, and data exchange.
2. [Review Flow Configurations](#flow-configurations): Learn the four available configuration types.
3. [Create a Flow](#create-a-flow): Build a new Flow in the dashboard and import the JSON provided by Meta’s builder.
4. [Manage Flows](#manage-flows): View, validate, and control the Flow lifecycle on the listing page.
5. [Understand Flow Statuses](#flow-statuses): Check what actions are possible in each lifecycle state.
6. [Use a Flow in a Template](#use-a-flow-in-a-template): Attach a Flow to a WhatsApp template and configure personalization.
7. [Publish Flows in Campaigns](#publishing-flows-in-campaigns): Deliver Flows to users by sending them WhatsApp campaigns.

## Select the Correct Setup

Since Flows collect user input directly inside WhatsApp, this input data must travel securely between Meta, CleverTap, and, in some cases, your own systems. Every Flow interaction is exchanged as a JSON payload. Because WhatsApp operates on an end-to-end encrypted channel, each payload is encrypted on the user’s device. The payload must be decrypted before CleverTap or your system can process it, and any responses must be re-encrypted before being sent back to the user.

Because of this encryption layer, there are multiple ways to set up how encryption, decryption, and data relay are handled. The right choice depends on whether you want CleverTap to manage encryption and relay, or if your business needs complete control over operations. Some setups are static (every screen is predefined in JSON and does not call a server), while others are dynamic (screens can change based on real-time data returned by your endpoint).\
Before choosing an approach, consider the following setup options:

* You can allow CleverTap to manage encryption and decryption. In this case, CleverTap receives the encrypted payload from Meta, decrypts it, ingests the event or profile data, and re-encrypts any outbound payload before sending it back to Meta. Your system only needs to provide the business logic at the *Customer endpoint*.
* You can choose to implement encryption and decryption yourself. In this case, you configure your own endpoint with Meta. CleverTap will not be involved in the encryption and decryption. You only receive the data you choose to post back to Meta.

| Setup                                  | Description                                                                                                                                                                                                                                                                                                               | Example Use Case                                                                                                                                                                                                     |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Static / No-endpoint flows             | Predefined JSON screens where responses are captured and stored directly in CleverTap as events. No callbacks or endpoints are required. Static flows transition screens using `navigate`; no server call or decryption round-trip occurs between screens.                                                                | A hotel survey form where responses (ratings, comments, and so on) are captured and saved as events in CleverTap.                                                                                                    |
| CleverTap endpoint + Customer endpoint | CleverTap decrypts payloads, ingests events or profiles, and relays decrypted data to your Customer endpoint. Each screen interaction generates a payload that contains user input and context, which your endpoint can use to define the next screen. CleverTap then encrypts the response before forwarding it to Meta. | A weather check flow: user enters *London*, CleverTap ingests the event and simultaneously relays the data to your endpoint, which queries a weather API and returns a payload showing “Rain expected this morning.” |
| Customer endpoint only                 | You register your own endpoint directly with Meta. You handle the encryption or decryption and business logic. CleverTap only ingests what you choose to forward.                                                                                                                                                         | A ticket booking system where your backend directly manages seat availability and payload exchanges.                                                                                                                 |
| Profile ingestion flows                | Payload responses map directly to CleverTap profile properties.                                                                                                                                                                                                                                                           | A sign-up form flow that collects *email* and *phone number* and updates the user’s CleverTap profile when those fields are added to the profile payload in the JSON.                                                |

Once you choose a setup, you can build the Flow JSON and configure endpoints accordingly. Use Meta’s builder to author and validate JSON and refer to the endpoint contract when you plan dynamic screens using data exchange. For more details, refer to [Create Flow JSON in Meta’s builder](https://developers.facebook.com/docs/whatsapp/flows/gettingstarted/creatingaflow#step-2--build-your-flow-json) and [Implement your endpoint for data exchange and encryption](https://developers.facebook.com/docs/whatsapp/flows/guides/implementingyourflowendpoint).

## Flow Configurations

This section defines each configuration and shows the payloads you can copy and adapt. The following JSON is illustrative. Author and validate with Meta’s builder, and follow the encryption and relay contract when you use data exchange.

**Flow actions at a glance**

* `navigate`: Transition to the next screen using only local JSON; no server call.
* `data_exchange`: Call an endpoint (Meta, your Customer endpoint, or CleverTap relay) and use the response to render the next screen.
* `complete`: Terminate the flow and submit the final payload back into the chat/thread.

**Ingestion keys reference:** From any screen’s `on-click-action`, you can include `ct-evt` to log a CleverTap event and `ct-up` to update profile attributes. Refer to [Profile ingestion flows](#profile-ingestion-flows) for details and examples.

You can choose from four types of Flow configurations:

* [Static / No-endpoint flows](#static-or-no-endpoint-flows): Predefined JSON screens where responses are captured as events in CleverTap; no server calls are required.
* [CleverTap endpoint + Customer endpoint](#clevertap-endpoint--customer-endpoint): CleverTap decrypts payloads, ingests data, and relays to your system, which returns the next screen.
* [Customer endpoint only](#customer-endpoint-only): You manage encryption, decryption, and orchestration end-to-end; CleverTap ingests only what you send back.
* [Profile ingestion flows](#profile-ingestion-flows): Collect user attributes (name, email, city, and so on) directly into CleverTap profiles.

### Static or No-endpoint flows

Use this setup for static, self-contained forms where no server calls are required; typical scenarios include NPS, CSAT, reviews, quick feedback, lead generation, and intent capture. User answers are returned as submitted responses (not a status), and CleverTap ingests them as an event and can also update profile properties if you map these fields. In CleverTap, an event such as `WAF_NPS_Submitted` appears in *Segments > Find People > Activities* with properties such as score, comment, and flow identifier. Static flows typically move between screens with `navigate` and `terminate `with complete.

**Hotel feedback — static Flow JSON** 

```json
{
    "screens": [
        {
            "data": {},
            "id": "RECOMMEND",
            "layout": {
                "children": [
                    {
                        "children": [
                            {
                                "type": "TextSubheading",
                                "text": "Would you recommend us to a friend?"
                            },
                            {
                                "type": "RadioButtonsGroup",
                                "label": "Choose one",
                                "name": "recommend",
                                "data-source": [
                                    {
                                        "id": "0_Yes",
                                        "title": "Yes"
                                    },
                                    {
                                        "id": "1_No",
                                        "title": "No"
                                    }
                                ],
                                "required": true
                            },
                            {
                                "type": "TextSubheading",
                                "text": "How could we do better?"
                            },
                            {
                                "type": "TextArea",
                                "label": "Leave a comment",
                                "required": false,
                                "name": "comment"
                            },
                            {
                                "label": "Continue",
                                "on-click-action": {
                                    "name": "navigate",
                                    "next": {
                                        "name": "RATE",
                                        "type": "screen"
                                    },
                                    "payload": {
                                        "recommend": "${form.recommend}",
                                        "comment": "${form.comment}"
                                    }
                                },
                                "type": "Footer"
                            }
                        ],
                        "name": "flow_path",
                        "type": "Form"
                    }
                ],
                "type": "SingleColumnLayout"
            },
            "title": "Feedback 1 of 2"
        },
        {
            "data": {
                "recommend": {
                    "__example__": "Example",
                    "type": "string"
                },
                "comment": {
                    "__example__": "Example",
                    "type": "string"
                }
            },
            "id": "RATE",
            "layout": {
                "children": [
                    {
                        "children": [
                            {
                                "type": "TextSubheading",
                                "text": "Rate the following: "
                            },
                            {
                                "type": "Dropdown",
                                "label": "Stay Experience",
                                "required": true,
                                "name": "Stay_Experience_f2b4e8",
                                "data-source": [
                                    {
                                        "id": "0_★★★★★_•_Excellent_(5/5)",
                                        "title": "★★★★★ • Excellent (5/5)"
                                    },
                                    {
                                        "id": "1_★★★★☆_•_Good_(4/5)",
                                        "title": "★★★★☆ • Good (4/5)"
                                    },
                                    {
                                        "id": "2_★★★☆☆_•_Average_(3/5)",
                                        "title": "★★★☆☆ • Average (3/5)"
                                    },
                                    {
                                        "id": "3_★★☆☆☆_•_Poor_(2/5)",
                                        "title": "★★☆☆☆ • Poor (2/5)"
                                    },
                                    {
                                        "id": "4_★☆☆☆☆_•_Very_Poor_(1/5)",
                                        "title": "★☆☆☆☆ • Very Poor (1/5)"
                                    }
                                ]
                            },
                            {
                                "type": "Dropdown",
                                "label": "Food Experience",
                                "required": true,
                                "name": "Food_Experience_bf1842",
                                "data-source": [
                                    {
                                        "id": "0_★★★★★_•_Excellent_(5/5)",
                                        "title": "★★★★★ • Excellent (5/5)"
                                    },
                                    {
                                        "id": "1_★★★★☆_•_Good_(4/5)",
                                        "title": "★★★★☆ • Good (4/5)"
                                    },
                                    {
                                        "id": "2_★★★☆☆_•_Average_(3/5)",
                                        "title": "★★★☆☆ • Average (3/5)"
                                    },
                                    {
                                        "id": "3_★★☆☆☆_•_Poor_(2/5)",
                                        "title": "★★☆☆☆ • Poor (2/5)"
                                    },
                                    {
                                        "id": "4_★☆☆☆☆_•_Very_Poor_(1/5)",
                                        "title": "★☆☆☆☆ • Very Poor (1/5)"
                                    }
                                ]
                            },
                            {
                                "type": "Dropdown",
                                "label": "Customer service",
                                "required": true,
                                "name": "Customer_service",
                                "data-source": [
                                    {
                                        "id": "0_Excellent",
                                        "title": "★★★★★ • Excellent (5/5)"
                                    },
                                    {
                                        "id": "1_Good",
                                        "title": "★★★★☆ • Good (4/5)"
                                    },
                                    {
                                        "id": "2_Average",
                                        "title": "★★★☆☆ • Average (3/5)"
                                    },
                                    {
                                        "id": "3_Poor",
                                        "title": "★★☆☆☆ • Poor (2/5)"
                                    },
                                    {
                                        "id": "4_Very_Poor",
                                        "title": "★☆☆☆☆ • Very Poor (1/5)"
                                    }
                                ]
                            },
                            {
                                "label": "Done",
                                "on-click-action": {
                                    "name": "complete",
                                    "payload": {
                                        "ct-evt": {
                                            "evtName": "Stay Feedback",
                                            "evtData": {
                                                "stay_experience": "${form.Stay_Experience_f2b4e8}",
                                                "food_experience": "${form.Food_Experience_bf1842}",
                                                "customer_service_experience": "${form.Customer_service}",
                                                "recommend": "${data.recommend}",
                                                "comment": "${data.comment}"
                                            }
                                        }
                                    }
                                },
                                "type": "Footer"
                            }
                        ],
                        "name": "flow_path",
                        "type": "Form"
                    }
                ],
                "type": "SingleColumnLayout"
            },
            "terminal": true,
            "title": "Feedback 2 of 2"
        }
    ],
    "version": "7.2"
}
```

**Ingested data example**

```json
Event: WAF_HotelFeedback_Submitted
Props: { "rating": "5", "comments": "Room was spotless", "flow_id": "hotel_feedback" }
```

#### Static navigation using CleverTap endpoint

When you choose the CleverTap endpoint and leave the Customer endpoint URL empty, the flow behaves like a static flow. Define the next screen directly in the Flow JSON using the target screen ID and required data. Upon submission, CleverTap ingests the payload and renders the specified next screen without making an external server call.

**Clevertap endpoint only: Example payload**

```json
{
  "version": "7.2",
  "routing_model": {
    "welcome_screen": [
      "seat_selection"
    ],
    "seat_selection": [
      "booking_confirmation"
    ]
  },
  "data_api_version": "3.0",
  "screens": [
    {
      "id": "welcome_screen",
      "title": "Book a trip",
      "data": {},
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "TextHeading",
            "text": "Book your journey"
          },
          {
            "type": "TextSubheading",
            "text": "Travel comfortably with Zoomture"
          },
          {
            "type": "Form",
            "name": "booking_form",
            "children": [
              {
                "type": "TextInput",
                "name": "depart_from",
                "label": "Depart from",
                "input-type": "text",
                "required": true,
                "helper-text": "Enter departure city"
              },
              {
                "type": "TextInput",
                "name": "arrive_in",
                "label": "Arrive in",
                "input-type": "text",
                "required": true,
                "helper-text": "Enter destination city"
              },
              {
                "type": "DatePicker",
                "name": "depart_date",
                "label": "Depart date",
                "required": true,
                "helper-text": "Select departure date",
                "min-date": "2025-05-25",
                "max-date": "2026-05-25"
              },
              {
                "type": "DatePicker",
                "name": "return_date",
                "label": "Return date",
                "required": false,
                "helper-text": "Select return date (optional)",
                "min-date": "2025-05-25",
                "max-date": "2026-05-25"
              },
              {
                "type": "Footer",
                "label": "Continue",
                "on-click-action": {
                  "name": "data_exchange",
                  "payload": {
                    "next_screen": "seat_selection",
                    "depart_from": "${form.depart_from}",
                    "arrive_in": "${form.arrive_in}",
                    "depart_date": "${form.depart_date}",
                    "return_date": "${form.return_date}",
                    "ct-evt": {
                      "evtName": "Date Selected",
                      "evtData": {
                        "depart_from": "${form.depart_from}",
                        "arrive_in": "${form.arrive_in}",
                        "depart_date": "${form.depart_date}",
                        "return_date": "${form.return_date}"
                      }
                    }
                  }
                }
              }
            ]
          },
          {
            "type": "TextCaption",
            "text": "Managed by Zoomture"
          }
        ]
      }
    },
    {
      "id": "seat_selection",
      "title": "Select seats",
      "data": {
        "selected_seats": {
          "type": "object",
          "__example__": {
            "name": "Jay"
          }
        },
        "depart_from": {
          "type": "string",
          "__example__": "Pune"
        },
        "arrive_in": {
          "type": "string",
          "__example__": "Pune"
        },
        "depart_date": {
          "type": "string",
          "__example__": "20250520"
        },
        "return_date": {
          "type": "string",
          "__example__": "20250520"
        }
      },
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "TextHeading",
            "text": "Select your seats"
          },
          {
            "type": "TextSubheading",
            "text": "Choose your preferred seats"
          },
          {
            "type": "TextBody",
            "text": "Left side"
          },
          {
            "type": "RadioButtonsGroup",
            "name": "left_seats",
            "label": "Left Seats",
            "data-source": [
              {
                "id": "1A",
                "title": "Seat 1A",
                "description": "Window seat"
              },
              {
                "id": "2A",
                "title": "Seat 2A",
                "description": "Window seat"
              },
              {
                "id": "3A",
                "title": "Seat 3A",
                "description": "Window seat - Unavailable",
                "enabled": false
              },
              {
                "id": "4A",
                "title": "Seat 4A",
                "description": "Window seat"
              }
            ]
          },
          {
            "type": "TextBody",
            "text": "Right side"
          },
          {
            "type": "RadioButtonsGroup",
            "name": "right_seats",
            "label": "Right Seats",
            "data-source": [
              {
                "id": "1B",
                "title": "Seat 1B",
                "description": "Aisle seat"
              },
              {
                "id": "1C",
                "title": "Seat 1C",
                "description": "Window seat - Unavailable",
                "enabled": false
              },
              {
                "id": "2B",
                "title": "Seat 2B",
                "description": "Aisle seat"
              },
              {
                "id": "2C",
                "title": "Seat 2C",
                "description": "Window seat"
              },
              {
                "id": "3B",
                "title": "Seat 3B",
                "description": "Aisle seat"
              },
              {
                "id": "3C",
                "title": "Seat 3C",
                "description": "Window seat"
              },
              {
                "id": "4B",
                "title": "Seat 4B",
                "description": "Aisle seat"
              },
              {
                "id": "4C",
                "title": "Seat 4C",
                "description": "Window seat"
              }
            ]
          },
          {
            "type": "Footer",
            "label": "Confirm selection",
            "on-click-action": {
              "name": "data_exchange",
              "payload": {
                "next_screen": "booking_confirmation",
                "ct-evt": {
                  "evtName": "Seat Selected",
                  "evtData": {
                    "depart_from": "${data.depart_from}",
                    "arrive_in": "${data.arrive_in}",
                    "depart_date": "${data.depart_date}",
                    "return_date": "${data.return_date}",
                    "selected_left_seat": "${form.left_seats}",
                    "selected_right_seat": "${form.right_seats}"
                  }
                },
                "depart_from": "${data.depart_from}",
                "arrive_in": "${data.arrive_in}",
                "depart_date": "${data.depart_date}",
                "return_date": "${data.return_date}",
                "selected_left_seat": "${form.left_seats}",
                "selected_right_seat": "${form.right_seats}"
              }
            }
          },
          {
            "type": "TextCaption",
            "text": "Managed by Zoomture"
          }
        ]
      }
    },
    {
      "id": "booking_confirmation",
      "title": "Booking Confirmation",
      "terminal": true,
      "data": {
        "selected_seats": {
          "type": "object",
          "__example__": {
            "name": "Jay"
          }
        },
        "depart_from": {
          "type": "string",
          "__example__": "Pune"
        },
        "arrive_in": {
          "type": "string",
          "__example__": "Pune"
        },
        "depart_date": {
          "type": "string",
          "__example__": "20250520"
        },
        "return_date": {
          "type": "string",
          "__example__": "20250520"
        },
        "selected_left_seat": {
          "type": "string",
          "__example__": "1A"
        },
        "selected_right_seat": {
          "type": "string",
          "__example__": "1B"
        }
      },
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "TextHeading",
            "text": "Booking Confirmed!"
          },
          {
            "type": "TextSubheading",
            "text": "Your trip has been successfully booked"
          },
          {
            "type": "TextBody",
            "text": "Journey Details:"
          },
          {
            "type": "TextBody",
            "text": "${data.depart_from}"
          },
          {
            "type": "TextBody",
            "text": "${data.arrive_in}"
          },
          {
            "type": "TextBody",
            "text": "${data.depart_date}"
          },
          {
            "type": "TextBody",
            "text": "${data.return_date}"
          },
          {
            "type": "TextBody",
            "text": "${data.selected_left_seat}"
          },
          {
            "type": "TextCaption",
            "text": "You will receive a confirmation message shortly with your ticket details."
          },
          {
            "type": "TextCaption",
            "text": "Managed by Zoomture"
          },
          {
            "label": "Done",
            "on-click-action": {
              "name": "complete",
              "payload": {
                "ct-evt": {
                  "evtName": "Bus booking Done",
                  "evtData": {
                    "depart_from": "${data.depart_from}",
                    "arrive_in": "${data.arrive_in}",
                    "depart_date": "${data.depart_date}",
                    "return_date": "${data.return_date}",
                    "selected_left_seat": "${data.selected_left_seat}",
                    "selected_right_seat": "${data.selected_right_seat}"
                  }
                }
              }
            },
            "type": "Footer"
          }
        ]
      }
    }
  ]
}
```

### CleverTap endpoint + Customer endpoint

Use this setup for dynamic screens with real-time data while having CleverTap handle encryption, decryption, and relays. Common cases include slot lookups, inventory checks, dynamic pricing, and eligibility checks. Meta calls the CleverTap Meta endpoint, which decrypts the payload, ingests analytics, forwards clean JSON to your customer endpoint, receives the next-screen response, re-encrypts, and replies to Meta. Events and profile updates included in the `analytics` block are ingested before CleverTap relays the new screen.

**Dynamic Flow based Customer input**

```json
{
  "version": "6.0",
  "data_api_version": "3.0",
  "routing_model": {
    "WELCOME": [
      "WEATHER",
      "YOUR_AGE"
    ],
    "WEATHER": [
      "TODAYS_WEATHER"
    ]
  },
  "screens": [
    {
      "id": "WELCOME",
      "data": {
        "name": {
          "type": "string",
          "__example__": "Jay"
        },
        "city": {
          "type": "string",
          "__example__": "Mumbai"
        },
        "age": {
          "type": "string",
          "__example__": "20"
        },
        "next_screen": {
          "type": "string",
          "__example__": "WELCOME"
        },
        "toDisplay": {
          "type": "string",
          "__example__": "Text to be displayed"
        }
      },
      "title": "${data.toDisplay}",
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "Form",
            "name": "flow_path",
            "children": [
              {
                "type": "Dropdown",
                "label": "What would you like",
                "required": true,
                "name": "What_would_you_like_24dfd1",
                "data-source": [
                  {
                    "id": "0_Check_weather_of_the_city",
                    "title": "Check weather of the city"
                  },
                  {
                    "id": "1_Check_my_age",
                    "title": "Check my age"
                  }
                ]
              },
              {
                "type": "Footer",
                "label": "Continue",
                "on-click-action": {
                  "name": "data_exchange",
                  "payload": {
                    "option": "${form.What_would_you_like_24dfd1}",
                    "name": "${data.name}",
                    "next_screen": "WEATHER"
                  }
                }
              }
            ]
          }
        ]
      }
    },
    {
      "id": "WEATHER",
      "title": "Weather Today",
      "data": {
        "name": {
          "type": "string",
          "__example__": "Jay"
        },
        "city": {
          "type": "string",
          "__example__": "Mumbai"
        },
        "next_screen": {
          "type": "string",
          "__example__": "WELCOME"
        },
        "toDisplay": {
          "type": "string",
          "__example__": "Text to be displayed"
        }
      },
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "Form",
            "name": "flow_path",
            "children": [
              {
                "type": "TextInput",
                "label": "City",
                "name": "Mumbai_c78cb7",
                "required": true,
                "input-type": "text",
                "helper-text": "Please enter city name"
              },
              {
                "type": "Footer",
                "label": "Continue",
                "on-click-action": {
                  "name": "data_exchange",
                  "payload": {
                    "city": "${form.Mumbai_c78cb7}",
                    "name": "${data.name}"
                  }
                }
              }
            ]
          }
        ]
      }
    },
    {
      "id": "YOUR_AGE",
      "title": "Your Age Prediction Is",
      "data": {
        "name": {
          "type": "string",
          "__example__": "Jay"
        },
        "age": {
          "type": "string",
          "__example__": "20"
        },
        "toDisplay": {
          "type": "string",
          "__example__": "Text to be displayed"
        }
      },
      "terminal": true,
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "Form",
            "name": "flow_path",
            "children": [
              {
                "type": "TextHeading",
                "text": "${data.toDisplay}"
              },
              {
                "type": "Footer",
                "label": "Continue",
                "on-click-action": {
                  "name": "complete",
                  "payload": {
                    "age": "${data.age}",
                    "name": "${data.name}"
                  }
                }
              }
            ]
          }
        ]
      }
    },
    {
      "id": "TODAYS_WEATHER",
      "title": "Todays Weather",
      "data": {
        "name": {
          "type": "string",
          "__example__": "Jay"
        },
        "city": {
          "type": "string",
          "__example__": "Mumbai"
        },
        "weather": {
          "type": "string",
          "__example__": "Good"
        },
        "toDisplay": {
          "type": "string",
          "__example__": "Text to be displayed"
        }
      },
      "terminal": true,
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "Form",
            "name": "flow_path",
            "children": [
              {
                "type": "TextHeading",
                "text": "${data.toDisplay}"
              },
              {
                "type": "Footer",
                "label": "Continue",
                "on-click-action": {
                  "name": "complete",
                  "payload": {
                    "name": "${data.name}",
                    "city": "${data.city}",
                    "weather": "${data.weather}"
                  }
                }
              }
            ]
          }
        ]
      }
    }
  ]
}
```

**Forwarded decrypted payload to customer endpoint**

```json
{
  data: { option: '1_Check_my_age'},
  flow_token: '1_2388541_2388541_1655455488_4393817507571773_1761636502',
  screen: 'WELCOME',
  action: 'data_exchange',
  version: '3.0'
}
```

**Customer endpoint response (next screen)**

```json
{
"data": {...}, //Data to be forwarded to next screen
"screen": "YOUR_AGE", //Id of the next screen of the flow
}
```

### Customer endpoint only

Use this setup when you want complete control over encryption and orchestration. This approach suits custom booking engines, latency-sensitive systems, or teams. In this setup, Meta calls your endpoint directly. Your system decrypts the payloads, computes results, encrypts responses, and returns them to Meta. CleverTap only receives the data you select to post (typically a summary at final submission). 

```json
{
    "label": "Done",
    "on-click-action": {
        "name": "complete",
        "payload": {
            "ct-evt": {
                "evtName": "Bus booking Done",
                "evtData": {
                    "depart_from": "${data.depart_from}",
                    "arrive_in": "${data.arrive_in}",
                    "depart_date": "${data.depart_date}",
                    "return_date": "${data.return_date}",
                    "selected_left_seat": "${data.selected_left_seat}",
                    "selected_right_seat": "${data.selected_right_seat}"
                }
            }
        }
    },
    "type": "Footer"
}
```

### Profile ingestion flows

Use this configuration to collect or update profile attributes such as name, email, city, and preferences directly inside WhatsApp. Typical uses include onboarding, preference centers, and consent capture. Decide which fields should be stored as event properties and which should update profile attributes. Use stable identifiers—unique, persistent user keys that do not change across sessions—such as the WhatsApp wa\_id to keep updates consistent. In CleverTap, you will see both an event (for example, `WAF_ProfileUpdated`) and the updated profile attributes tied to the same user identity.

#### How it works

* From any screen’s `on-click-action`, include `ct-up` to update profile attributes and `ct-evt` to log an event in CleverTap.
* These keys are available in all configurations.
* Use `navigate` for local screen transitions. Use `data_exchange` when calling an endpoint and `complete` to end the flow and submit the final payload.

#### Keys

* `ct-up` updates profile attributes with key value pairs.
* `ct-evt` records an event with `evtName` and `evtData`.

> 📘 Note
>
> Meta supports string data types only in Flow payloads. Event (`ct-evt`) and profile (`ct-up`) ingestion is processed only when triggered from an `on-click-action` of type `data_exchange` or `complete`. Using `navigate` moves between screens locally and does not trigger ingestion.

**Profile update: Flow JSON**

```json
{
    "on-click-action": {
        "name": "data_exchange",
        "payload": {
            "ct-up": {
                "Name": "${form.name}", //Captured from User input
                "Email": "${form.email}",
                "Phone": "${form.Phone}",
                "Gender": "${form.gender}"
            }
        }
    }
}
```

**Event data: Flow JSON**

```json
{
    "label": "Done",
    "on-click-action": {
        "name": "complete",
        "payload": {
            "ct-evt": {
                "evtName": "Bus booking Done",
                "evtData": {
                    "depart_from": "${data.depart_from}",
                    "arrive_in": "${data.arrive_in}",
                    "depart_date": "${data.depart_date}",
                    "return_date": "${data.return_date}",
                    "selected_left_seat": "${data.selected_left_seat}",
                    "selected_right_seat": "${data.selected_right_seat}"
                }
            }
        }
    },
    "type": "Footer"
}
```

### Notes on endpoints, keys, and encryption

This section explains when to use an endpoint and how CleverTap helps manage encryption.

* If you select **CleverTap Provided URL** under *Meta endpoint*, CleverTap registers and manages the required public keys for your WABA, handles encryption and decryption, ingests events on the fly, and forwards decrypted payloads to your *Customer endpoint* when configured. Encryption formats and relay behavior follow Meta’s contract. For more information, refer to [Implement your endpoint](https://developers.facebook.com/docs/whatsapp/flows/guides/implementingyourflowendpoint).
* If you select **Custom URL** under *Meta endpoint*, Meta calls your URL directly, and you must implement the contract, including health checks, public-key upload, and encrypted payload handling, as defined by Meta. Select this when you need full control or cannot route requests through CleverTap.
* If you want to author and validate Flow JSON before pasting it into the dashboard, use Meta’s builder and follow Meta’s delivery guidance when sending flows in template messages. For more information, refer to [Create Flow JSON](https://developers.facebook.com/docs/whatsapp/flows/gettingstarted/creatingaflow#step-2--build-your-flow-json) and [Send a Flow](https://developers.facebook.com/docs/whatsapp/flows/gettingstarted/sendingaflow).

## Create a Flow

This section explains how to create a Flow on the dashboard.

1. Go to *Settings > Channels > WhatsApp > WhatsApp Direct* > *WABA*.
2. Click **Flows**, then click **Create Flow**. 

   <Image alt="Create Flow" align="center" border={true} src="https://files.readme.io/436ddc977c3c8a536fd63894ce6f3abc5ad98902bdee15b5b76a92f5f8731f13-create_flow.png">
     Create Flow
   </Image>
3. Enter a *Name*.
4. Select a *Category* such as *Sign-up*, *Sign-in*, *Appointment Booking*, *Lead Generation*, *Contact Us*, *Customer Support Survey*, *Survey*, or *Other*.
5. Under *Meta endpoint*, select one option. Select **CleverTap Provided URL** if you want CleverTap to handle encryption, decryption, and relays. Select **Custom URL** if you will host and operate your own Meta endpoint. For the contract, keys, and health checks required by Meta, refer to [Implement your endpoint](https://developers.facebook.com/docs/whatsapp/flows/guides/implementingyourflowendpoint).
6. If you want CleverTap to forward decrypted payloads to your system and receive next-screen data in response, provide a *Customer endpoint*.
7. Click **Open Meta Playground** to preview and compose screens. Copy the Flow JSON and paste it into *JSON*. You can author and validate the JSON in Meta’s builder as described in [Create Flow JSON](https://developers.facebook.com/docs/whatsapp/flows/gettingstarted/creatingaflow#step-2--build-your-flow-json).
8. Click **Save** to keep the Flow in *Draft*.
9. Click **Publish** to make the Flow available for templates. 

   <Image alt="Flow Details - WhatsApp Direct" align="center" border={true} src="https://files.readme.io/4cafbe140ed78ad73726894dca2cca66caaba9bae5b2c25d20c909eb09dea9b6-new_flow_created.png">
     Flow Details - WhatsApp Direct
   </Image>

## Manage Flows

Once a flow is created, it appears on the listing page where you can view and manage its lifecycle. The listing provides a quick overview of all flows under a WhatsApp Business Account. 

<Image alt="Manage Flows" align="center" border={true} src="https://files.readme.io/7b955bf5bdacfca08d2772c54a1f31fbb164d94479976fa0cd72c20bd9ad6679-manage_flows.png">
  Manage Flows
</Image>

### Listing Page Columns

| Column                      | Description                                                                                                       |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| *Flow Name*                 | The name assigned while creating the flow.                                                                        |
| *Flow ID*                   | A unique identifier for the flow, generated by Meta.                                                              |
| *Flow Status*               | Lifecycle status of the flow. Possible values are *Draft*, *Published*, *Deprecated*, *Throttled*, and *Blocked*. |
| *Validation Errors*         | Indicates whether the flow has validation errors (*True* or *False*).                                             |
| *Mapped/Data Exchange URLs* | The *Meta Data Exchange URL* and *Customer Data Exchange URL* associated with the flow.                           |
| *Last Updated*              | The most recent update timestamp.                                                                                 |
| *Created By*                | The user who created the flow.                                                                                    |

### Encryption Keys

At the top of the page, you can view the private and public keys generated for secure data exchange. These keys are generated per WABA account, registered with Meta, and remain unchanged once created. For more information about Meta’s key and endpoint requirements, refer to  [Implement your endpoint](https://developers.facebook.com/docs/whatsapp/flows/guides/implementingyourflowendpoint). 

<Image alt="Encryption Keys" align="center" width="65% " border={true} src="https://files.readme.io/5da52efab9c58a54660fb7503ba724787b1449c7f961adfc46c14800d878d4e2-enecryption_keys_-_flows.png">
  Encryption Keys
</Image>

## Flow Statuses

Each flow goes through a lifecycle stage that defines what you can do with it. The table below combines the status descriptions and the actions allowed in each state.

| *Flow Status*           | Description                                                                                                   | Allowed Actions                                                                                                                                                                                                                                    |
| ----------------------- | ------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| *Draft*                 | Editable state before publishing.                                                                             | **Preview flow**, update flow JSON, update *Customer Data Exchange URL* (only if using the CleverTap Meta endpoint), **Delete**, **Refresh** to fetch validation results.                                                                          |
| *Published*             | Active and usable in templates.                                                                               | **Preview flow**, update *Customer Data Exchange URL*, **Refresh** details, **Deprecate flow**. Deprecation is irreversible — once a flow is deprecated, users cannot access it, and it will automatically be removed from any templates using it. |
| *Deprecated*            | Retired and read-only for audit. Cannot be used in campaigns or templates.                                    | **Preview flow**, **Refresh** for audit purposes. No edits are allowed.                                                                                                                                                                            |
| *Throttled* / *Blocked* | Restricted by Meta due to policy or rate limits. Requires review and possibly remediation before further use. | **Preview flow**, update *Customer Data Exchange URL*, **Refresh** to check error details, **Deprecate flow**. As with published flows, deprecation is irreversible.                                                                               |

## Use a Flow in a Template

This section explains how to attach a Flow to a WhatsApp template and apply optional personalization.

1. Go to *Settings > Channels > WhatsApp > WhatsApp Direct*.
2. Click **Templates**, then click **+ Template**. 

   <Image alt="Create Template with Flows" align="center" border={true} src="https://files.readme.io/e573c07ab3a3a58fddd4cfc316d5af34422a072e114003bdf60eed8897367605-create_template_flows.png">
     Create Template with Flows
   </Image>
3. Select the *Category* Marketing or Utility.
4. Choose **Flows** as the template type. 

   <Image alt="Template Type - Flows" align="center" border={true} src="https://files.readme.io/a1055de418c543cd5072d81265e0d1ad50235d60622bc02fb5c607e0b8a4875c-template_type_-_flows.png">
     Template Type - Flows
   </Image>
5. Enter *Name* and *Message*. You can add a footer. Personalization is optional. If you want to customize user-facing content, you can use CleverTap variables such as `{{user.name}}` in the message body, footer, and button text.

   * Under *Header* (optional), set *Type* to *Media* and choose *Image*, *Video*, *Document*, or *Location*.
   * For *Image*: supported formats `png, jpeg, jpg`, max file size 5 MB, recommended aspect ratio 3:2.
   * For *Video*: format `mp4`, max file size 16 MB, recommended aspect ratio 3:2.
   * For *Document*: format `pdf`, max file size 16 MB.
   * For *Image*, *Video*, or *Document*, upload a *Sample Media File* for Meta review.
   * *Body*: enter message content (variables allowed).
   * *Footer* (optional): add a short line of text.
6. Add the button text under *Buttons* > *Complete Flow*.
7. Select *Navigation* for static flows where the first screen is predefined or *Data Exchange* for dynamic flows where the first screen is fetched after tap.
8. During campaign setup, you can pass parameters into *Flow Action (Data Exchange)* to pre-fill values such as city, booking ID, or order reference. This is also optional.
9. Click **Browse Flows**, select a published Flow, and choose the landing screen when you use Navigation.
10. Click **Submit** to finish. Meta’s guidance in [Send a Flow via template messages](https://developers.facebook.com/docs/whatsapp/flows/gettingstarted/sendingaflow) explains message delivery for flows sent via templates.

## Publishing Flows in Campaigns

After a Flow has been created, published, and attached to a template, you can use it in a WhatsApp campaign. This ensures that end users receive the message with the Flow CTA button and can complete the journey without leaving the chat.

1. Go to *Campaigns* and click **Create Campaign**.
2. Select **WhatsApp** as the channel.
3. In the *Template* step, select a Flow Template. For the Flow Template:

   * Input fields are the same as for basic templates.
   * Flow buttons are preconfigured and cannot be edited.
4. Review the *Campaign preview*. The Flow CTA button is displayed with details such as *button type*, *Flow name*, *Flow ID*, *Flow Action*, and *Landing Screen*.
5. Add targeting, scheduling, and delivery preferences as required.
6. Click **Publish Campaign**.

CleverTap automatically attaches the correct Flow ID to the WhatsApp message when the campaign is live. When the user taps the Flow CTA, Meta launches the corresponding Flow.

* **Personalization (Optional):** You can personalize the message body with CleverTap variables at this stage. The Flow JSON and button configurations remain static and cannot be personalized.
* **Error handling:** If no published Flows are available, the system prompts you to create or publish one before proceeding.