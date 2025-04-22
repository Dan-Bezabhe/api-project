
# 🛰️ Capital Time API

A simple Flask API that gives you the current local time and UTC offset for any capital city.

Hosted on GCP:  
http://35.193.172.116:5000


# Auth Token


Token:
```
supersecrettoken123
```

Include it in your request headers like this:
```
Authorization: Bearer supersecrettoken123
```

# Endpoints

# 1. /api/hello (open to everyone)

Quick test to make sure it’s alive.

Try it in your browser:
```
GET http://35.193.172.116:5000/api/hello
```

Response:
```json
{ "message": "Hello, world!" }
```

# 2. /api/secure-data (token required)

Example of a protected endpoint.

```
GET http://35.193.172.116:5000/api/secure-data
Authorization: Bearer supersecrettoken123
```

Response:
```json
{ "secret": "This is protected info!" }
```

# 3. /api/time?city=CityName (token required)

Returns local time and UTC offset for any city that geopy can locate.

Example:
```
GET http://35.193.172.116:5000/api/time?city=Addis%20Ababa
Authorization: Bearer supersecrettoken123
```

Response:
```json
{
  "city": "Addis Ababa",
  "local_time": "2025-04-21 22:36:10",
  "utc_offset": "+03:00"
}
```

If the city isn’t found:
```json
{ "error": "City 'Atlantis' not found" }
```
