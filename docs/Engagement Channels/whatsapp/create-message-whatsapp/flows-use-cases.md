---
title: Flows Use Cases
excerpt: Sample use cases for WhatsApp Flows
deprecated: false
hidden: false
metadata:
  robots: index
---
## Overview

[WhatsApp Flows](doc:flows-1) let you build guided, multi-step experiences inside a WhatsApp conversation. Instead of directing users to a website or asking them to reply with freeform text, you can present structured screens with inputs, selections, and navigation, all within the chat itself.

These examples cover common engagement and data capture journeys such as customer surveys, onboarding flows, product selection, quizzes, and preference collection. Each Flow is built using predefined screens, structured input components, and guided navigation to help you create seamless conversational experiences.

Before you use these examples, review [Select the Correct Setup](docs:flows-1#select-the-correct-setup) and [Flow Configurations](doc:flows-1#flow-configurations) to understand static versus endpoint-based Flows and how `navigate`, `data_exchange`, and `complete` work.

## Use Cases Covered

Whether you want to collect feedback, recommend products, or run an interactive quiz, the following ready-to-use Flow patterns give you a starting point for each scenario:

- [Health Condition-Based Exercise Recommendation](doc:flows-use-cases#health-condition-based-exercise-recommendation)
- [Multi-Step Customer Feedback Survey](doc:flows-use-cases#multi-step-customer-feedback-survey)
- [Doctor Details and Specialization Capture](doc:flows-use-cases#doctor-details-and-specialization-capture)
- [Category-Based Product Selection](doc:flows-use-cases#category-based-product-selection)
- [Interactive Quiz Flow](doc:flows-use-cases#interactive-quiz-flow)
- [Customer Satisfaction Survey With Engagement Preferences](doc:flows-use-cases#customer-satisfaction-survey-with-engagement-preferences)

To create these Flows in CleverTap and attach them to WhatsApp templates, refer to [Create a Flow](doc:flows-1#create-a-flow) and [Use a Flow in a Template](doc:flows-1#use-a-flow-in-a-template).&#x20;

## Exercise Recommendation Based on Health Condition

This use case demonstrates how to build a static WhatsApp Flow that collects condition-specific health inputs and displays predefined exercise recommendations directly within the Flow. The interaction progresses through screen navigation and does not require an external endpoint.

### Flow Overview

Think of a fitness app that wants to nudge users toward the right workout without a consultation. A user managing diabetes gets a gentle 20-minute walk and yoga routine, while someone focused on weight loss gets squats, lunges, and jumping jacks. The Flow asks a few quick questions and delivers a personalized recommendation, all without leaving WhatsApp.

A static Flow means all screens and recommendations are defined upfront. No external server is involved, and no data is fetched at runtime. What the user sees is determined entirely by the choices they make within the Flow.

Marketers can view the submitted responses, including the selected condition and health inputs, in the **User Profiles** section of CleverTap under _WhatsApp > Flow Responses_.

The Flow progresses through the following steps:

1. The user selects a health condition from a navigation list using the `navigate` action.
2. A condition-specific form captures relevant health inputs using the `navigate` action.
3. Form values are passed to the following screen through the navigation payload using the `navigate` action.
4. A recommendation screen displays predefined exercises tailored to the selected condition using the `navigate` action.
5. The user taps **Done** to finish the Flow using the `complete` action.

### Screens in this Flow

The following screens are defined in the Flow configuration.

| Screen                        | Purpose                                        |
| ----------------------------- | ---------------------------------------------- |
| `start_screen`                | Allows the user to choose a health condition   |
| `obesity_info_screen`         | Captures obesity-related health details        |
| `diabetics_info_screen`       | Captures diabetes-related health details       |
| `recommended_obesity_screen`  | Displays exercise recommendations for obesity  |
| `recommended_diabetes_screen` | Displays exercise recommendations for diabetes |

### Sample Flow JSON

The following JSON illustrates the static, condition-based recommendation structure described above.

```json
{
  "version": "7.3",
  "screens": [
    {
      "id": "start_screen",
      "title": "Choose your condition",
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "NavigationList",
            "name": "condition_list",
            "list-items": [
              {
                "id": "obesity_info_screen",
                "main-content": {
                  "title": "Obesity"
                },
                "on-click-action": {
                  "name": "navigate",
                  "next": {
                    "name": "obesity_info_screen",
                    "type": "screen"
                  }
                }
              },
              {
                "id": "diabetics_info_screen",
                "main-content": {
                  "title": "Diabetes"
                },
                "on-click-action": {
                  "name": "navigate",
                  "next": {
                    "name": "diabetics_info_screen",
                    "type": "screen"
                  }
                }
              }
            ]
          }
        ]
      }
    },
    {
      "id": "obesity_info_screen",
      "title": "Obesity Info",
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "TextBody",
            "text": "Enter your details to get exercise recommendations."
          },
          {
            "type": "Form",
            "name": "obesity_form",
            "children": [
              {
                "type": "TextInput",
                "label": "Age",
                "name": "age",
                "required": true
              },
              {
                "type": "TextInput",
                "label": "Weight (kg)",
                "name": "weight",
                "required": true
              },
              {
                "type": "TextInput",
                "label": "Height (cm)",
                "name": "height",
                "required": true
              },
              {
                "type": "Footer",
                "label": "Submit",
                "on-click-action": {
                  "name": "navigate",
                  "next": {
                    "name": "recommended_obesity_screen",
                    "type": "screen"
                  },
                  "payload": {
                    "age": "${form.age}",
                    "weight": "${form.weight}",
                    "height": "${form.height}"
                  }
                }
              }
            ]
          }
        ]
      }
    },
    {
      "id": "diabetics_info_screen",
      "title": "Diabetes Info",
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "TextBody",
            "text": "Enter your details to get exercise recommendations."
          },
          {
            "type": "Form",
            "name": "diabetes_form",
            "children": [
              {
                "type": "TextInput",
                "label": "Age",
                "name": "age",
                "required": true
              },
              {
                "type": "TextInput",
                "label": "Blood Sugar (mg/dL)",
                "name": "blood_sugar",
                "required": true
              },
              {
                "type": "Footer",
                "label": "Submit",
                "on-click-action": {
                  "name": "navigate",
                  "next": {
                    "name": "recommended_diabetes_screen",
                    "type": "screen"
                  },
                  "payload": {
                    "age": "${form.age}",
                    "blood_sugar": "${form.blood_sugar}"
                  }
                }
              }
            ]
          }
        ]
      }
    },
    {
      "id": "recommended_obesity_screen",
      "title": "Obesity Exercises",
      "terminal": true,
      "data": {
        "age": { "type": "string" },
        "weight": { "type": "string" },
        "height": { "type": "string" }
      },
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "TextHeading",
            "text": "Recommended Exercises"
          },
          {
            "type": "TextBody",
            "markdown": true,
            "text": "- Brisk walking for 30 mins\n- Jumping jacks\n- Squats\n- Lunges"
          },
          {
            "type": "Footer",
            "label": "Done",
            "on-click-action": {
              "name": "complete",
              "payload": {
                "age": "${data.age}",
                "weight": "${data.weight}",
                "height": "${data.height}"
              }
            }
          }
        ]
      }
    },
    {
      "id": "recommended_diabetes_screen",
      "title": "Diabetes Exercises",
      "terminal": true,
      "data": {
        "age": { "type": "string" },
        "blood_sugar": { "type": "string" }
      },
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "TextHeading",
            "text": "Recommended Exercises"
          },
          {
            "type": "TextBody",
            "markdown": true,
            "text": "- Walking for 20 mins\n- Cycling\n- Yoga\n- Light aerobics"
          },
          {
            "type": "Footer",
            "label": "Done",
            "on-click-action": {
              "name": "complete",
              "payload": {
                "age": "${data.age}",
                "blood_sugar": "${data.blood_sugar}"
              }
            }
          }
        ]
      }
    }
  ]
}
```

## Multi-Step Customer Feedback Survey

This use case demonstrates how to implement a multi-step static WhatsApp Flow that collects structured customer feedback across recommendation intent, qualitative comments, and service ratings. All responses are consolidated and submitted when the Flow completes.

### Flow Overview

Think of a car dealership that wants to know how a customer felt after purchasing a vehicle. Instead of sending a survey link that goes unopened, the dealership sends a WhatsApp message and the customer completes the entire feedback form without leaving the chat. They rate the purchase experience, delivery, and customer service, then choose how they want to be followed up with.

A multi-step Flow means the survey is split across several screens, each collecting a focused set of inputs. Responses from earlier screens are carried forward using the `payload` object and submitted together at the end, so nothing is lost between steps.

Marketers can view the submitted responses, including ratings, comments, and preferred contact methods, in the **User Profiles** section of CleverTap under _WhatsApp > Flow Responses_.

The Flow progresses through the following steps:

1. The user answers a recommendation question and optionally provides a comment using the `navigate` action.
2. The user rates multiple service dimensions using dropdown selections using the `navigate` action.
3. The user provides a reference and selects a preferred follow-up method using the `complete` action.

### Screens in this Flow

The following screens are defined in the Flow configuration.

| Screen      | Purpose                                                                              |
| ----------- | ------------------------------------------------------------------------------------ |
| `RECOMMEND` | Captures recommendation intent and optional feedback comment                         |
| `RATE`      | Collects ratings for purchase experience, delivery and setup, and customer service   |
| `FOLLOW_UP` | Captures reference information and preferred contact method, then completes the Flow |

### Sample Flow JSON

The following JSON illustrates the static, multi-step survey structure described above.

```json
{
  "screens": [
    {
      "data": {},
      "id": "RECOMMEND",
      "title": "Feedback 1 of 3",
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "Form",
            "name": "flow_path",
            "children": [
              {
                "type": "TextSubheading",
                "text": "Would you recommend us to a friend?"
              },
              {
                "type": "RadioButtonsGroup",
                "label": "Choose one",
                "name": "recommend",
                "required": true,
                "data-source": [
                  { "id": "0_Yes", "title": "Yes" },
                  { "id": "1_No", "title": "No" }
                ]
              },
              {
                "type": "TextSubheading",
                "text": "How could we do better?"
              },
              {
                "type": "TextArea",
                "label": "Leave a comment",
                "name": "comment",
                "required": false
              },
              {
                "type": "Footer",
                "label": "Continue",
                "on-click-action": {
                  "name": "navigate",
                  "next": { "name": "RATE", "type": "screen" },
                  "payload": {
                    "recommend": "${form.recommend}",
                    "comment": "${form.comment}"
                  }
                }
              }
            ]
          }
        ]
      }
    },
    {
      "id": "RATE",
      "title": "Feedback 2 of 3",
      "data": {
        "recommend": { "type": "string", "__example__": "Yes" },
        "comment": { "type": "string", "__example__": "Great service" }
      },
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "Form",
            "name": "flow_path",
            "children": [
              {
                "type": "TextSubheading",
                "text": "Rate the following:"
              },
              {
                "type": "Dropdown",
                "label": "Purchase experience",
                "name": "purchase_experience",
                "required": true,
                "data-source": [
                  { "id": "0_Excellent", "title": "★★★★★ • Excellent (5/5)" },
                  { "id": "1_Good", "title": "★★★★☆ • Good (4/5)" },
                  { "id": "2_Average", "title": "★★★☆☆ • Average (3/5)" },
                  { "id": "3_Poor", "title": "★★☆☆☆ • Poor (2/5)" },
                  { "id": "4_Very_Poor", "title": "★☆☆☆☆ • Very Poor (1/5)" }
                ]
              },
              {
                "type": "Dropdown",
                "label": "Delivery and setup",
                "name": "delivery_setup",
                "required": true,
                "data-source": [
                  { "id": "0_Excellent", "title": "★★★★★ • Excellent (5/5)" },
                  { "id": "1_Good", "title": "★★★★☆ • Good (4/5)" },
                  { "id": "2_Average", "title": "★★★☆☆ • Average (3/5)" },
                  { "id": "3_Poor", "title": "★★☆☆☆ • Poor (2/5)" },
                  { "id": "4_Very_Poor", "title": "★☆☆☆☆ • Very Poor (1/5)" }
                ]
              },
              {
                "type": "Dropdown",
                "label": "Customer service",
                "name": "customer_service",
                "required": true,
                "data-source": [
                  { "id": "0_Excellent", "title": "★★★★★ • Excellent (5/5)" },
                  { "id": "1_Good", "title": "★★★★☆ • Good (4/5)" },
                  { "id": "2_Average", "title": "★★★☆☆ • Average (3/5)" },
                  { "id": "3_Poor", "title": "★★☆☆☆ • Poor (2/5)" },
                  { "id": "4_Very_Poor", "title": "★☆☆☆☆ • Very Poor (1/5)" }
                ]
              },
              {
                "type": "Footer",
                "label": "Continue",
                "on-click-action": {
                  "name": "navigate",
                  "next": { "name": "FOLLOW_UP", "type": "screen" },
                  "payload": {
                    "purchase_experience": "${form.purchase_experience}",
                    "delivery_setup": "${form.delivery_setup}",
                    "customer_service": "${form.customer_service}",
                    "recommend": "${data.recommend}",
                    "comment": "${data.comment}"
                  }
                }
              }
            ]
          }
        ]
      }
    },
    {
      "id": "FOLLOW_UP",
      "title": "Follow-up preferences",
      "terminal": true,
      "data": {
        "purchase_experience": { "type": "string", "__example__": "Excellent" },
        "delivery_setup": { "type": "string", "__example__": "Good" },
        "customer_service": { "type": "string", "__example__": "Excellent" },
        "recommend": { "type": "string", "__example__": "Yes" },
        "comment": { "type": "string", "__example__": "Smooth process" }
      },
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "Form",
            "name": "flow_path",
            "children": [
              {
                "type": "TextSubheading",
                "text": "Share a reference and choose how we should follow up."
              },
              {
                "type": "TextInput",
                "label": "Vehicle listing ID or reference",
                "name": "vehicle_reference",
                "required": false
              },
              {
                "type": "RadioButtonsGroup",
                "label": "Preferred contact method",
                "name": "contact_method",
                "required": true,
                "data-source": [
                  { "id": "0_WhatsApp", "title": "WhatsApp" },
                  { "id": "1_Phone_call", "title": "Phone call" },
                  { "id": "2_Email", "title": "Email" }
                ]
              },
              {
                "type": "Footer",
                "label": "Submit",
                "on-click-action": {
                  "name": "complete",
                  "payload": {
                    "vehicle_reference": "${form.vehicle_reference}",
                    "contact_method": "${form.contact_method}",
                    "purchase_experience": "${data.purchase_experience}",
                    "delivery_setup": "${data.delivery_setup}",
                    "customer_service": "${data.customer_service}",
                    "recommend": "${data.recommend}",
                    "comment": "${data.comment}"
                  }
                }
              }
            ]
          }
        ]
      }
    }
  ],
  "version": "7.3"
}
```

## Doctor Details and Specialization Capture

A hospital network onboarding new doctors onto their patient engagement platform needs to collect each practitioner's details and area of specialization quickly and accurately. Instead of managing spreadsheets or manual forms, the onboarding team sends a WhatsApp message and the doctor fills in their name, location, and specialization without leaving the chat. If their specialization is not on the list, they can type it in directly.

A static Flow means all screens and fields are defined upfront. No external server is involved. The Flow collects inputs across two screens and submits them together as a single consolidated response at the end.

Marketers and operations teams can view the submitted practitioner details, including name, location, and specialization, in the **User Profiles** section of CleverTap under _WhatsApp > Flow Responses_.

### Flow Overview

The Flow progresses through the following steps:

1. The user enters basic doctor details such as name and location using the `navigate` action.
2. The user selects a specialization from a dropdown list using the `navigate` action.
3. If **Others** is selected, an additional input field appears to capture a custom specialization using the `navigate` action.
4. The user taps **Done** to submit the collected inputs using the `complete` action.

### Screens in this Flow

The following screens are defined in the Flow configuration.

| Screen           | Purpose                                                                                       |
| ---------------- | --------------------------------------------------------------------------------------------- |
| `DOCDETAILS`     | Captures doctor name and location                                                             |
| `SPECIALIZATION` | Collects specialization selection and optional custom specialization, then completes the Flow |

### Sample Flow JSON

The following JSON illustrates the static, two-step practitioner capture flow described above.

```json
{
  "version": "7.2",
  "screens": [
    {
      "data": {},
      "id": "DOCDETAILS",
      "title": "Doctor Information",
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "Form",
            "name": "flow_path",
            "children": [
              {
                "type": "TextSubheading",
                "text": "Doctor Details"
              },
              {
                "type": "TextInput",
                "input-type": "text",
                "label": "Name",
                "name": "Name_92baf2",
                "required": true
              },
              {
                "type": "TextInput",
                "input-type": "text",
                "label": "Location",
                "name": "Location_2eb7a9",
                "required": true
              },
              {
                "type": "Footer",
                "label": "Next",
                "on-click-action": {
                  "name": "navigate",
                  "next": {
                    "name": "SPECIALIZATION",
                    "type": "screen"
                  },
                  "payload": {
                    "screen_0_Name_0": "${form.Name_92baf2}",
                    "screen_0_Location_1": "${form.Location_2eb7a9}"
                  }
                }
              }
            ]
          }
        ]
      }
    },
    {
      "id": "SPECIALIZATION",
      "title": "Specialization",
      "terminal": true,
      "data": {
        "screen_0_Name_0": {
          "__example__": "Example",
          "type": "string"
        },
        "screen_0_Location_1": {
          "__example__": "Example",
          "type": "string"
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
                "type": "TextSubheading",
                "text": "Select your Specialization"
              },
              {
                "type": "Dropdown",
                "label": "Select",
                "required": true,
                "name": "Select_5e7ea3",
                "data-source": [
                  { "id": "0_Cardiologist", "title": "Cardiologist" },
                  { "id": "1_Neurologist", "title": "Neurologist" },
                  { "id": "2_General_Surgeon", "title": "General Surgeon" },
                  { "id": "3_Pediatrics", "title": "Pediatrics" },
                  { "id": "4_Dentist", "title": "Dentist" },
                  { "id": "5_Others", "title": "Others" }
                ]
              },
              {
                "type": "If",
                "condition": "(${form.Select_5e7ea3} == '5_Others')",
                "then": [
                  {
                    "type": "TextInput",
                    "input-type": "text",
                    "label": "Others",
                    "name": "Others_1a6f54",
                    "required": true,
                    "visible": true
                  }
                ]
              },
              {
                "type": "Footer",
                "label": "Done",
                "on-click-action": {
                  "name": "complete",
                  "payload": {
                    "doctor_name": "${data.screen_0_Name_0}",
                    "doctor_location": "${data.screen_0_Location_1}",
                    "specialization": "${form.Select_5e7ea3}",
                    "other_specialization": "${form.Others_1a6f54}"
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

## Category-Based Product Selection

A fashion retailer wants to understand what their customers are interested in before a sale goes live. Instead of sending a generic broadcast, they send a WhatsApp message that lets each customer browse categories, such as dresses, shoes, beauty, or sale items, and pick a product they like. The retailer gets clean, structured preference data and the customer gets a browsing experience without leaving the chat.

A static Flow means all categories and products are defined upfront. The Flow does not fetch live inventory or pricing. It captures interest based on a fixed list of options and submits the selection at the end.

Marketers can view the submitted selections, including the chosen category and product, in the **User Profiles** section of CleverTap under _WhatsApp > Flow Responses_. This data can be used to personalize follow-up campaigns.

### Flow Overview

The Flow progresses through the following steps:

1. The user selects a product category from a navigation list using the `navigate` action.
2. The Flow displays a category-specific selection screen using the `navigate` action.
3. The user selects one product and continues using the `navigate` action.
4. The user taps **Complete** to submit the selected category and item using the `complete` action.

### Screens in this Flow

The following screens are defined in the Flow configuration.

| Screen         | Purpose                                       |
| -------------- | --------------------------------------------- |
| `FIRST_SCREEN` | Allows the user to choose a product category  |
| `DRESS`        | Captures a dress selection                    |
| `SHOES`        | Captures a shoe selection                     |
| `BEAUTY`       | Captures a beauty product selection           |
| `SALE`         | Captures a sale item selection                |
| `THANKYOU`     | Confirms the selection and completes the Flow |

### JSON Payload

```json
{
  "version": "7.3",
  "screens": [
    {
      "id": "FIRST_SCREEN",
      "title": "Select a Category",
      "data": {},
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "NavigationList",
            "name": "category_list",
            "list-items": [
              {
                "id": "dress_category",
                "main-content": {
                  "title": "Dresses",
                  "metadata": "Explore new arrivals"
                },
                "on-click-action": {
                  "name": "navigate",
                  "next": {
                    "name": "DRESS",
                    "type": "screen"
                  }
                }
              },
              {
                "id": "shoes_category",
                "main-content": {
                  "title": "Shoes",
                  "metadata": "Browse trending styles"
                },
                "on-click-action": {
                  "name": "navigate",
                  "next": {
                    "name": "SHOES",
                    "type": "screen"
                  }
                }
              },
              {
                "id": "beauty_category",
                "main-content": {
                  "title": "Beauty",
                  "metadata": "Shop personal care picks"
                },
                "on-click-action": {
                  "name": "navigate",
                  "next": {
                    "name": "BEAUTY",
                    "type": "screen"
                  }
                }
              },
              {
                "id": "sale_category",
                "main-content": {
                  "title": "Sale",
                  "metadata": "Discounted products"
                },
                "on-click-action": {
                  "name": "navigate",
                  "next": {
                    "name": "SALE",
                    "type": "screen"
                  }
                }
              }
            ]
          }
        ]
      }
    },
    {
      "id": "DRESS",
      "title": "Select a Dress",
      "data": {},
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "TextSubheading",
            "text": "Choose one option from our dress collection."
          },
          {
            "type": "Form",
            "name": "dress_form",
            "children": [
              {
                "type": "RadioButtonsGroup",
                "name": "dress",
                "label": "Available Dresses",
                "required": true,
                "data-source": [
                  {
                    "id": "maxi_dress",
                    "title": "Maxi Dress",
                    "description": "Comfortable evening wear"
                  },
                  {
                    "id": "summer_dress",
                    "title": "Summer Dress",
                    "description": "Lightweight seasonal pick"
                  }
                ]
              },
              {
                "type": "Footer",
                "label": "Continue",
                "on-click-action": {
                  "name": "navigate",
                  "next": {
                    "name": "THANKYOU",
                    "type": "screen"
                  },
                  "payload": {
                    "selected_category": "dress",
                    "selected_item": "${form.dress}"
                  }
                }
              }
            ]
          }
        ]
      }
    },
    {
      "id": "SHOES",
      "title": "Select Shoes",
      "data": {},
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "TextSubheading",
            "text": "Choose one shoe style you are interested in."
          },
          {
            "type": "Form",
            "name": "shoes_form",
            "children": [
              {
                "type": "RadioButtonsGroup",
                "name": "shoes",
                "label": "Available Shoes",
                "required": true,
                "data-source": [
                  {
                    "id": "heels",
                    "title": "Heels",
                    "description": "Formal occasion wear"
                  },
                  {
                    "id": "sneakers",
                    "title": "Sneakers",
                    "description": "Everyday casual style"
                  }
                ]
              },
              {
                "type": "Footer",
                "label": "Continue",
                "on-click-action": {
                  "name": "navigate",
                  "next": {
                    "name": "THANKYOU",
                    "type": "screen"
                  },
                  "payload": {
                    "selected_category": "shoes",
                    "selected_item": "${form.shoes}"
                  }
                }
              }
            ]
          }
        ]
      }
    },
    {
      "id": "BEAUTY",
      "title": "Select a Beauty Product",
      "data": {},
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "TextSubheading",
            "text": "Choose a beauty product you would like to explore."
          },
          {
            "type": "Form",
            "name": "beauty_form",
            "children": [
              {
                "type": "RadioButtonsGroup",
                "name": "beauty",
                "label": "Beauty Options",
                "required": true,
                "data-source": [
                  {
                    "id": "hair_styler",
                    "title": "Hair Styler",
                    "description": "Multi-use styling tool"
                  },
                  {
                    "id": "cleansing_oil",
                    "title": "Cleansing Oil",
                    "description": "Daily skincare essential"
                  }
                ]
              },
              {
                "type": "Footer",
                "label": "Continue",
                "on-click-action": {
                  "name": "navigate",
                  "next": {
                    "name": "THANKYOU",
                    "type": "screen"
                  },
                  "payload": {
                    "selected_category": "beauty",
                    "selected_item": "${form.beauty}"
                  }
                }
              }
            ]
          }
        ]
      }
    },
    {
      "id": "SALE",
      "title": "Select a Sale Item",
      "data": {},
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "TextSubheading",
            "text": "Choose one discounted product from the sale section."
          },
          {
            "type": "Form",
            "name": "sale_form",
            "children": [
              {
                "type": "RadioButtonsGroup",
                "name": "sale_item",
                "label": "Sale Products",
                "required": true,
                "data-source": [
                  {
                    "id": "handbag",
                    "title": "Handbag",
                    "description": "Limited-time offer"
                  },
                  {
                    "id": "electronics_accessory",
                    "title": "Electronics Accessory",
                    "description": "Special seasonal discount"
                  }
                ]
              },
              {
                "type": "Footer",
                "label": "Continue",
                "on-click-action": {
                  "name": "navigate",
                  "next": {
                    "name": "THANKYOU",
                    "type": "screen"
                  },
                  "payload": {
                    "selected_category": "sale",
                    "selected_item": "${form.sale_item}"
                  }
                }
              }
            ]
          }
        ]
      }
    },
    {
      "id": "THANKYOU",
      "title": "Thank You",
      "terminal": true,
      "data": {
        "selected_category": {
          "__example__": "dress",
          "type": "string"
        },
        "selected_item": {
          "__example__": "maxi_dress",
          "type": "string"
        }
      },
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "TextHeading",
            "text": "Thank you for exploring our collection!"
          },
          {
            "type": "TextBody",
            "text": "Your selection has been recorded."
          },
          {
            "type": "Footer",
            "label": "Complete",
            "on-click-action": {
              "name": "complete",
              "payload": {
                "selected_category": "${data.selected_category}",
                "selected_item": "${data.selected_item}"
              }
            }
          }
        ]
      }
    }
  ]
}
```

## Interactive Quiz Flow

A consumer brand running a product knowledge campaign wants to engage their WhatsApp audience with a fun, interactive quiz. Instead of linking out to a third-party quiz tool, they send a WhatsApp message that walks each participant through a welcome screen, collects their details, and presents multiple-choice questions, all within the chat. The brand gets structured response data and the participant gets a seamless experience without switching apps.

A multi-step Flow means the quiz is spread across several screens, each serving a distinct purpose such as capturing details, displaying instructions, or collecting answers. Responses from each screen are carried forward using the `payload` object and submitted together at the end.

Marketers can view submitted quiz responses, including participant details and answers, in the **User Profiles** section of CleverTap under _WhatsApp > Flow Responses_. This data can be used to identify engaged users and trigger follow-up campaigns.

### Flow Overview

The Flow progresses through the following steps:

1. The user starts the quiz from a welcome screen using the `navigate` action.
2. The user enters their participant details using the `navigate` action.
3. The Flow displays quiz instructions using the `navigate` action.
4. The user answers multiple-choice questions across individual question screens using the `navigate` action.
5. The user taps **Done** to submit all captured responses using the `complete` action.

### Screens in this Flow

The following screens are defined in the Flow configuration.

| Screen                  | Purpose                                                     |
| ----------------------- | ----------------------------------------------------------- |
| `start_screen`          | Introduces the quiz and starts the Flow                     |
| `player_details_screen` | Captures participant details such as name and email         |
| `instruction_screen`    | Displays quiz instructions and routes to the first question |
| `questionOne_screen`    | Captures the answer to the first question                   |
| `questionTwo_screen`    | Captures the answer to the second question                  |
| `result_screen_Two`     | Confirms completion and submits responses using `complete`  |

### JSON Payload

The following JSON defines the interactive quiz Flow:

```json
{
  "version": "7.3",
  "screens": [
    {
      "id": "start_screen",
      "title": "Welcome",
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "TextHeading",
            "text": "Interactive Quiz"
          },
          {
            "type": "TextBody",
            "text": "Test your knowledge in this short quiz experience."
          },
          {
            "type": "Footer",
            "label": "Start Quiz",
            "on-click-action": {
              "name": "navigate",
              "next": {
                "type": "screen",
                "name": "player_details_screen"
              }
            }
          }
        ]
      }
    },
    {
      "id": "player_details_screen",
      "title": "Your Details",
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "Form",
            "name": "player_form",
            "children": [
              {
                "type": "TextInput",
                "label": "Full Name",
                "name": "full_name",
                "required": true
              },
              {
                "type": "TextInput",
                "label": "Email (optional)",
                "name": "email",
                "input-type": "email"
              },
              {
                "type": "Footer",
                "label": "Continue",
                "on-click-action": {
                  "name": "navigate",
                  "next": {
                    "type": "screen",
                    "name": "instruction_screen"
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

## Customer Satisfaction Survey With Engagement Preferences

A telecom company wants to measure how satisfied customers are after a support interaction. Instead of following up with a separate email survey that goes ignored, they send a WhatsApp message that lets the customer rate their experience across service quality, response time, and resolution satisfaction, then choose how they want to hear from the brand next. The support team gets actionable ratings and the customer gets a quick, frictionless way to share feedback.

A static Flow means all screens, rating options, and engagement channels are defined upfront. No external server is involved. Responses from the rating screen are carried forward using the `payload` object and submitted together with the channel preferences at the end.

Marketers can view the submitted ratings, comments, and preferred engagement channels in the **User Profiles** section of CleverTap under _WhatsApp > Flow Responses_. This data can be used to segment dissatisfied customers and trigger targeted recovery campaigns.

### Flow Overview

The Flow progresses through the following steps:

1. The user starts the survey from an introduction screen using the `navigate` action.
2. The user provides satisfaction ratings across multiple service dimensions and optionally adds comments using the `navigate` action.
3. The user selects one or more preferred engagement channels using the `complete` action.

### Screens in this Flow

The following screens are defined in the Flow configuration.

| Screen              | Purpose                                                         |
| ------------------- | --------------------------------------------------------------- |
| `start_screen`      | Introduces the survey and starts the Flow                       |
| `survey_screen_One` | Captures satisfaction ratings and optional qualitative feedback |
| `engagement_screen` | Captures engagement channel preferences and completes the Flow  |

### Sample Flow JSON

The following JSON illustrates the static customer satisfaction survey and engagement preference structure described above.

```json
{
  "version": "7.3",
  "screens": [
    {
      "id": "start_screen",
      "title": "Customer Satisfaction Survey",
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "TextHeading",
            "text": "Thank you for your recent support visit!"
          },
          {
            "type": "TextBody",
            "text": "We value your feedback. This survey will take less than a minute."
          },
          {
            "type": "Footer",
            "label": "Start Survey",
            "on-click-action": {
              "name": "navigate",
              "next": {
                "name": "survey_screen_One",
                "type": "screen"
              }
            }
          }
        ]
      }
    },
    {
      "id": "survey_screen_One",
      "title": "Rate Our Service",
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "TextSubheading",
            "text": "Please rate the following from 1 (poor) to 5 (excellent):"
          },
          {
            "type": "Form",
            "name": "survey_form",
            "children": [
              {
                "type": "RadioButtonsGroup",
                "name": "service_quality",
                "label": "Service Quality",
                "required": true,
                "data-source": [
                  { "id": "1", "title": "1" },
                  { "id": "2", "title": "2" },
                  { "id": "3", "title": "3" },
                  { "id": "4", "title": "4" },
                  { "id": "5", "title": "5" }
                ]
              },
              {
                "type": "RadioButtonsGroup",
                "name": "response_time",
                "label": "Response Time",
                "required": true,
                "data-source": [
                  { "id": "1", "title": "1" },
                  { "id": "2", "title": "2" },
                  { "id": "3", "title": "3" },
                  { "id": "4", "title": "4" },
                  { "id": "5", "title": "5" }
                ]
              },
              {
                "type": "RadioButtonsGroup",
                "name": "resolution_satisfaction",
                "label": "Resolution Satisfaction",
                "required": true,
                "data-source": [
                  { "id": "1", "title": "1" },
                  { "id": "2", "title": "2" },
                  { "id": "3", "title": "3" },
                  { "id": "4", "title": "4" },
                  { "id": "5", "title": "5" }
                ]
              },
              {
                "type": "TextArea",
                "label": "Additional Comments",
                "name": "additional_comments",
                "helper-text": "Optional feedback"
              },
              {
                "type": "Footer",
                "label": "Next",
                "on-click-action": {
                  "name": "navigate",
                  "next": {
                    "name": "engagement_screen",
                    "type": "screen"
                  },
                  "payload": {
                    "service_quality": "${form.service_quality}",
                    "response_time": "${form.response_time}",
                    "resolution_satisfaction": "${form.resolution_satisfaction}",
                    "additional_comments": "${form.additional_comments}"
                  }
                }
              }
            ]
          }
        ]
      }
    },
    {
      "id": "engagement_screen",
      "title": "Stay Connected",
      "terminal": true,
      "data": {
        "service_quality": { "type": "string" },
        "response_time": { "type": "string" },
        "resolution_satisfaction": { "type": "string" },
        "additional_comments": { "type": "string" }
      },
      "layout": {
        "type": "SingleColumnLayout",
        "children": [
          {
            "type": "TextSubheading",
            "text": "How would you like to receive updates from us?"
          },
          {
            "type": "Form",
            "name": "engagement_form",
            "children": [
              {
                "type": "CheckboxGroup",
                "name": "engagement_channels",
                "label": "Preferred Channels",
                "required": true,
                "min-selected-items": 1,
                "data-source": [
                  { "id": "email", "title": "Email" },
                  { "id": "sms", "title": "SMS" },
                  { "id": "whatsapp", "title": "WhatsApp" }
                ]
              },
              {
                "type": "Footer",
                "label": "Submit",
                "on-click-action": {
                  "name": "complete",
                  "payload": {
                    "service_quality": "${data.service_quality}",
                    "response_time": "${data.response_time}",
                    "resolution_satisfaction": "${data.resolution_satisfaction}",
                    "additional_comments": "${data.additional_comments}",
                    "engagement_channels": "${form.engagement_channels}"
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

<br />
