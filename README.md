# hip
Sandbox for playing with processing healthcare messages

# Sample 1: Processing non-standard patient search
Request Model:
* lastname
* firstname
* dob
* gender
* mrn

Lambda: https://console.aws.amazon.com/lambda/home?region=us-east-1#/functions/SimplePatientSearch?newFunction=true&tab=code
HTTP API: https://us-east-1.console.aws.amazon.com/apigateway/main/api-detail?api=sel9ozjvgl&region=us-east-1#



# Lambda: pull queries params from request

```
    if (event.queryStringParameters && event.queryStringParameters.name) {
        console.log("Received name: " + event.queryStringParameters.name);
        name = event.queryStringParameters.name;
    }
```

# Lambda: create test lambda event with query params
```
{
  "queryStringParameters": {
    "name": "Mighty Pulpo",
    "city": "Virginia"
  }
}
```

# Lambda: build response
```
    let response = {
        statusCode: responseCode,
        headers: {
            "x-custom-header" : "my custom header value"
        },
        body: JSON.stringify(responseBody)
    };
```
