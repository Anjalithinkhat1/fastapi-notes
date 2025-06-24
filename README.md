# FastAPI Notes API

A simple CRUD (Create, Read, Update, Delete) API built with FastAPI for managing notes.

## Endpoints

- `GET /notes` - List all notes
- `GET /notes/{id}` - Get a single note by ID
- `POST /notes` - Create a new note
- `PUT /notes/{id}` - Update an existing note
- `DELETE /notes/{id}` - Delete a note

## How to Run

```bash
uvicorn index:app --reload
