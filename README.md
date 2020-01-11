Quickstart: Compose and Django


IF you want to use different DB you can add another service 
On the file docker-compose.yml

The file will look like this:

"
version: '3'

services:
  db:
    image: postgres
  web:
    build: .
    command: python manage.py runserver 0.0.0.0:8000
    volumes:
      - .:/code
    ports:
      - "8000:8000"
    depends_on:
      - db
"