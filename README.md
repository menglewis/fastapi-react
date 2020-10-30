# fastapi-react

A basic template for building a project using fastapi on the backend and React on the frontend.

This is based on [fastapi-react](https://github.com/Buuntu/fastapi-react) and customized to my preferences.

## Development

Docker is the main thing you need to run this.

### Quick Start

To start:

```bash
docker-compose up -d
```

To run the alembic migrations:

```bash
docker-compose run --rm backend alembic upgrade head
```

And navigate to http://localhost:8000

Auto-generated docs will be at
http://localhost:8000/api/docs

### Frontend Development

In can be easier to run the frontend locally for faster reloading.

```
cd frontend
npm install
npm start
```

Then you can access the frontend at http://localhost:3000

## Migrations

Migrations are run using alembic. To run all migrations:

```
docker-compose run --rm backend alembic upgrade head
```

To create a new migration:

```
alembic revision -m "create users table"
```

And fill in `upgrade` and `downgrade` methods. For more information see
[Alembic's official documentation](https://alembic.sqlalchemy.org/en/latest/tutorial.html#create-a-migration-script).

## Testing

There is a helper script for both frontend and backend tests:

```
./scripts/test.sh
```

### Backend Tests

```
docker-compose run backend pytest
```

### Frontend Tests

```
docker-compose run frontend test
```
