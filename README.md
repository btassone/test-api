# test-api

A super simple, very basic, hacked together test api (for testing).

## Endpoints

[GET /metrics]()
[GET /v1/test/args](#get-command-line-arguments)  
[GET /v1/test/env](#get-environment-variables)  
[GET /v1/test/list](#list-files)  
[GET /v1/test/metadata/task]()  
[GET /v1/test/metadata/stats]()  
[GET /v1/test/metadata/task/stats]()  
[GET /v1/test/mirror]()  
[GET /v1/test/panic]()  
[GET /v1/test/ping]()  
[GET /v1/test/routes]()  
[GET /v1/test/status{?code=XXX}]()  
[POST /v1/test/upload](upload-files)  
[GET /v1/test/version]()  

### Get Command Line Arguments

Returns the command line arguments as JSON.

For example, starting with `./test-api foo bar baz --help` will return:

```json
{
  "Args": [
    "foo",
    "bar",
    "baz",
    "--help"
  ]
}
```

### Get Environment Variables

Returns the list of environment variables as JSON.

```json
[
  "PWD=/app",
  "SHELL=/bin/bash",
  "USER=nobody",
  "AWS_DEFAULT_REGION=us-east-1"
]
```

### Get Files

Returns a list of files in the VOLUME_PATH

```json
{
    "Files": [
        {
            "Name": "083821609-20200612_133928832.mp4",
            "Size": "2.7 MB",
            "ModTime": "Thu Jul 23 09:50:05 2020"
        },
        {
            "Name": "491786708-colors-1838392_1920.jpg",
            "Size": "601.0 kB",
            "ModTime": "Thu Jul 23 09:33:12 2020"
        }
    ]
}
```

### Upload Files

POST a file as multipart form data.  The form key needs to be `file`.

## Author

E Camden Fisher <camden.fisher@yale.edu>

## License

GNU Affero General Public License v3.0 (GNU AGPLv3)
Copyright (c) 2020 Yale University
