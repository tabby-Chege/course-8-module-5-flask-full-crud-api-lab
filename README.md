# Module Lab: Building Full CRUD RESTful APIs with Flask

## Overview

This project is a simple event management API built with Flask. It demonstrates full CRUD behavior using in-memory data storage and JSON responses.

## Routes

- `GET /` — returns a welcome message
- `GET /events` — returns a JSON list of all events
- `POST /events` — creates a new event from JSON input
- `PATCH /events/<id>` — updates an existing event title
- `DELETE /events/<id>` — deletes an event by ID

## Example Requests

### Welcome route

```bash
curl http://localhost:5000/
```

Response:

```json
{
  "message": "Welcome to the Event API!"
}
```

### Get all events

```bash
curl http://localhost:5000/events
```

Response:

```json
[
  {"id": 1, "title": "Tech Meetup"},
  {"id": 2, "title": "Python Workshop"}
]
```

### Create an event

```bash
curl -X POST http://localhost:5000/events \
  -H "Content-Type: application/json" \
  -d '{"title": "Hackathon"}'
```

Response:

```json
{
  "id": 3,
  "title": "Hackathon"
}
```

### Update an event

```bash
curl -X PATCH http://localhost:5000/events/1 \
  -H "Content-Type: application/json" \
  -d '{"title": "Hackathon 2025"}'
```

Response:

```json
{
  "id": 1,
  "title": "Hackathon 2025"
}
```

### Delete an event

```bash
curl -X DELETE http://localhost:5000/events/2
```

Response:

- HTTP status: `204 No Content`

## Status Codes Used

- `200 OK` for successful reads and updates
- `201 Created` for successful event creation
- `204 No Content` for successful deletion
- `400 Bad Request` for invalid or missing JSON input
- `404 Not Found` when an event ID does not exist

## Run the API

```bash
python app.py
```

Then visit the routes in a browser or test them with curl/Postman.
