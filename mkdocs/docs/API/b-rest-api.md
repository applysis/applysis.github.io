# Rest API

### Submission feedback with API Key

Once you [generate the API](a-creating-api-source.md) key on the Applysis platform, you can use it now in your own software systems to submit customer feedback directly to us.

Our feedback object expects 8 fields. Here is what you can submit to us.

-   **text**: optional, e.g review text, email body etc.
-   **title**: optional, e.g email subject, question, review title etc.
-   **date**: optional. We expect any valid JSON date.
-   **rating**: optional, e.g review rating, we expect it to be minimum 1, maximum 5
-   **author**: optional, e.g user name, email address.
-   **region**: optional, it can hold any region value you desire e.g country, city, county.
-   **version**: optional, e.g 1.5, 1.6.1 etc.
-   **tags**: optional, array of Strings e.g ["brake", "speed", "price"] etc.

### Steps to submit

#### 1. Prepare the valid JSON

Here are some few important things to consider:

1. API expects an array of the feedback objects.
2. You can not submit more than 50 feedbacks at a single batch and it can be minimum one feedback.

Here is the example of JSON:

```
[
    {
        "text": "Thank you for providing such an amazing app!",
        "title": "Nice app!",
        "date": "2020-04-23T18:25:43.511Z",
        "rating": 5,
        "author": "shalva@applysis.io",
        "region": "Tallinn",
        "version": "1.5.1",
        "tags": ["brake", "speed", "price"]
    }
]
```

#### 2. Add headers

Here is the place where we will use the generated secret key. So, we require to append only two headers:

1. `x-api-key: your-secret-key`
2. `Content-Type: application/json`

#### 3. Submit feedback

Prepare your request, add body, headers and POST it to `https://api-public.applysis.io`

**N.B** If you are going to submit feedback from Apple systems, we have prepared [Swift Package](c-ios-sdk.md) supporting iOS, OSX, WatchOS and TVOS, which eases the submission process.

## Limitations

-   You can not submit more than 50 feedbacks at a single request.
-   With the current plans, you can submit a maximum 2000 feedbacks in a month. If you wish to increase the amount, please, [reach out](mailto:contact@applysis.io) to us.
-   `text` field can not be `null` nor empty.

For any issues or technical difficulties, please [reach out](mailto:contact@applysis.io) to us.
