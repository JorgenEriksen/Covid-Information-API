# Covid-Information-API

The API has endpoints:

http://localhost:8080/corona/v1/country/ <br />
http://localhost:8080/corona/v1/policy/ <br />
http://localhost:8080/corona/v1/diag/ <br />
http://localhost:8080/corona/v1/notifications/ <br />

It is also hosted on OpenStack (10.212.140.3:8080)

# http://localhost:8080/corona/v1/country/
Format: /corona/v1/country/{:country_name}{?scope=begin_date-end_date} <br />
Type: Get <br />
Example request: http://localhost:8080/corona/v1/country/norway?scope?=2020-12-01-2021-01-31 <br />
Example response: <br />
```
{
    "Country": "Norway",
    "Continent": "Europe",
    "Scope": "total",
    "Confirmed": 93150,
    "Recovered": 17998,
    "Population_percentage": 1.75
}
```

# http://localhost:8080/corona/v1/policy/
Format: /corona/v1/policy/{:country_name}{?scope=begin_date-end_date} <br />
Type: Get <br />
Example request: http://localhost:8080/corona/v1/policy/norway?scope=2020-11-01-2021-01-31 <br />
Example response: <br />
```
{
    "Country": "Norway",
    "Scope": "2020-11-01-2021-01-31",
    "Stringency": 73.15,
    "Trend": 29.630000000000003
}
```

# http://localhost:8080/corona/v1/notifications/
Format: /corona/v1/notifications/ <br />
Type: Get <br />
Example request: http://localhost:8080/corona/v1/notifications/ <br />
Example response: <br />

```
[
    {
        "ID": "A40CyNKniZkWqMOPY6Y7",
        "url": "https://webhook.site/8540ab6d-5fd9-4716-bd36-ed9bb12a6461",
        "timeout": 3600,
        "time": "2021-03-28T12:42:29.11Z",
        "field": "confirmed",
        "country": "Norway",
        "trigger": "ON_CHANGE",
        "occurrences": 92469
    },
    {
        "ID": "G95NJUHrVDJI3MegWzqY",
        "url": "https://webhook.site/9326f4b4-4d4a-48dd-b0c4-d7cc5ff9fbb3",
        "timeout": 3600,
        "time": "2021-03-28T12:37:34.549Z",
        "field": "confirmed",
        "country": "Norway",
        "trigger": "ON_CHANGE",
        "occurrences": 92469
    },
]
```

<br />
<br />
Format: /corona/v1/notifications/{id} <br />
Type: Get <br />
Example request: http://localhost:8080/corona/v1/notifications/G95NJUHrVDJI3MegWzqY <br />
Example response: <br />

```
{
    "ID": "G95NJUHrVDJI3MegWzqY",
    "url": "https://webhook.site/9326f4b4-4d4a-48dd-b0c4-d7cc5ff9fbb3",
    "timeout": 3600,
    "time": "2021-03-28T12:37:34.549Z",
    "field": "confirmed",
    "country": "Norway",
    "trigger": "ON_CHANGE",
    "occurrences": 92469
},
```

<br />
<br />
Format: /corona/v1/notifications/ <br />
Type: POST <br />
Example request: http://localhost:8080/corona/v1/notifications/ <br />
Example body: <br />

```
{
    "url": "https://localhost:8080/client/",
    "timeout": 3600,
    "field": "confirmed",
    "country": "Norway",
    "trigger": "ON_CHANGE"
}
```

<br />
<br />
Format: /corona/v1/notifications/ <br />
Type: DELETE <br />
Example request: http://localhost:8080/corona/v1/notifications/G95NJUHrVDJI3MegWzqY <br />
Example response: <br />

```
If the webhook existed, it is now deleted
```

# http://localhost:8080/corona/v1/diag
Format: /corona/v1/diag <br />
Type: Get <br />
Example request: http://localhost:8080/corona/v1/diag <br />
Example response: <br />
```
{
    "Mmediagroupapi": "200",
    "Covidtrackerapi": "200",
    "Registered": 3,
    "Version": "v1",
    "Uptime": 2.7876306
}
```

