# MIT_Course_Capstone_Project

FAQs - Real-Time Retail Feedback Intelligence
Why do we need Generative AI instead of simple sentiment analysis?

Simple sentiment analysis only tells us whether feedback is positive or negative. It cannot explain why the customer feels that way or what exactly went wrong. Generative AI is used because it can understand the full context of the review. It can identify whether the feedback is about fit, quality, delivery, or service, summarise the issue, and suggest clear actions for the retail team. This makes the analysis more useful for real business decisions.

What does “detect which product or service each feedback refers to” mean?

This means understanding what the customer is talking about in their review.

Product-related feedback includes fit, size, fabric, quality, or price of the item.
Service-related feedback includes delivery experience, returns, or customer support.

There is no separate service column in the dataset. The AI model reads the review text and identifies whether the feedback is about a product issue or a service-related issue.


What does “summarise insights by product category and urgency level” mean?

This means grouping customer feedback in a way that helps teams take quick action.

Product category comes from existing data such as department names (for example: Dresses, Tops).
Urgency level is not directly given and is understood from the review text.

Based on the review:

High urgency indicates serious complaints or critical problems
Medium urgency indicates delivery delays or repeated issues
Low urgency indicates minor issues, suggestions, or positive feedback


What is Zero-Shot Prompting in this project?

Zero-Shot Prompting means giving the AI clear instructions without providing any examples.

The model is asked to analyse each review and generate:

Category
Sentiment
Summary
Personalised Message
Retail Insight
The goal is to test prompt clarity, not to train the model.


How do we design a Zero-Shot prompt for this task?

A Zero-Shot prompt is designed by:

Clearly defining the model’s role
Listing all required outputs
Defining allowed values (such as Positive, Negative, Neutral)
Keeping the instructions clear and structured
No examples are given in the prompt.


What does “Category” mean in the AI output?

Category refers to the type of feedback, not the product category.

Examples of categories include:

Fit
Quality
Delivery
Price
Other
These categories help identify which part of the customer experience the feedback relates to.


How is urgency identified if it is not present in the dataset?
Urgency is identified by reading the review text and understanding the seriousness of the issue.

For example:

Strong complaints or safety concerns are treated as high urgency
Delivery or service delays are treated as medium urgency
Suggestions or positive comments are treated as low urgency
The AI model helps infer this from the language used by the customer.

-----------------------------------------------------------------------------------
Here's how you can generate the OpenAI token for your upcoming MLS/LVC/Projects.

1. Once you sign in to Olympus, click on the Settings option in the dropdown that appears on clicking your profile icon in the top-right part of the screen. You will be able to see an option called OpenAI Token.



 2. Clicking on CREATE TOKEN will assign you a Token and an API Base as follows:



 3. This Token (further referred to as API Key) and API Base are required to be utilized in the notebooks for this module in order to call the OpenAI model via API for inference.

 

Loading API Key via Google Colab Secrets

Click on the “Key icon” in the left sidebar in Colab.
Click “+ Add new secret”. Please refer to the screenshot for reference:
secrets_1-2.png

In the Name field, enter OPENAI_API_KEY. In the Value field, paste your OpenAI API Key.
Toggle Notebook access for secret key. Please refer to the screenshot for reference:
secrets_2-2.png

Now in your notebook, access it using the following code:
Python------------------------------------------------------------------------------------------------------------------

CODE:

import os

from google.colab import userdata # Access user-specific data securely

openai_api_key = userdata.get(‘OPENAI_API_KEY')

  

 

Important NOTE : OpenAI Key Usage Guidelines: 

The following are the account limits associated with the OpenAI Token and Key you will receive:

1. Maximum Credit Limit: $20

2. Requests per Minute (RPM) Limit: 50

3. Maximum Daily Credit Limit: $4

 

Since this OpenAI Key, with its account limits, will also be required as part of Projects, you are encouraged to use it sparingly - only for the upcoming MLS, and Project notebooks. Please refrain from utilizing it for any personal or other professional projects. If you encounter any challenges or issues setting up or using this API Key, please do not hesitate to contact us via Support Request.
