# Rest API

### Submission feedback with API Key

Once you generate the API key on Applysis platform, you can use it now in your own systems to submit feedbacks directly to us.

Our API expects 7 fields, out of which only **text** is mandatory. Here is what you can submit to us.

-   **text**: mandatory, e.g review text, email body etc.
-   **title**: optional, e.g email subject, question, review title etc.
-   **date**: optional. We expect any valid JSON date.
-   **rating**: optional, e.g review rating, we expect it to be minimum 1, maximum 5
-   **author**: optional, e.g user name, email address.
-   **region**: optional, it can hold any region value you desire e.g country, city, county.
-   **version**: optional, e.g 1.5, 1.6.1 etc.

### Steps to submit

#### 1. Prepare the valid JSON

Here are some few important things to consider:

1. `text` field can not be `null` nor empty.
2. API expects array of the feedack objects.
3. You can not submit more than 50 feedbacks at a single batch.

Here is the example of JSON:

```
[
    {
        "text": "Thank you for providing such amazing app!",
        "title": "Nice app!",
        "date": "2020-04-23T18:25:43.511Z",
        "rating": 5,
        "author": "shalva@applysis.io",
        "region": "Tallinn",
        "version": "1.5.1"
    }
]
```

#### 2. Add headers

We require to append only two headers:

1. `x-api-key: your-secret-key`
2. `Content-Type: application/json`

#### 3. Submit feedback

Prepare your request, add body and headers and use POST method to `https://api-public.applysis.io`

## Limitations

-   You can not submit more than 50 feedbacks at a single request.
-   With the current plans, you can submit maximum 2000 feedbacks in a month.
-   `text` field can not be `null` nor empty.

For any issues or technical difficulties, please [reach out](mailto:contact@applysis.io) us.
