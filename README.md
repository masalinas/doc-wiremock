## Description
Start a simple mock server

## Install from docker
To install wiremock and configure some stubs(endpoint mocks) execute this command:

```
docker run -d --name wiremock -p 8080:8080 -v $PWD/stubs:/home/wiremock wiremock/wiremock
```

We must create a folder (under /stubs/mappings) where save our endpoints mocks like json files, a simple
hello world endpoint mock could be:

```
{
    "request": {
        "method": "GET",
        "url": "/hello"
    },
    "response": {
        "status": 200,
        "body": "Hello world!",
        "headers": {
            "Content-Type": "text/plain"
        }
    }
}
```

## Test mocks server
To check our endpoint simple send a curl like this:

```
curl http://localhost:8080/hello
```
