# auction-houses

## API Endpoints

**Base path:** `/auction-houses`

### GET /auction-houses/
Returns all registered auction houses.
- **Response:** 200 OK with JSON array of auction houses, or 204 No Content if empty

### POST /auction-houses/
Creates a new auction house.
- **Request body:** 
  ```json
  {
    "group": "string",
    "auction-feed": "string"
  }
  ```
- **Response:** 201 Created
- Automatically generates a UUID for the new auction house

### DELETE /auction-houses/{uuid}
Deletes an auction house by its UUID.
- **Response:** 204 No Content if deleted, or 404 Not Found if UUID doesn't exist

**Port:** 8030

## Docker Deployment

```bash
docker-compose up -d
```

Or build and run manually:
```bash
docker build -t auction-houses .
docker run -p 8030:8030 auction-houses
```

## Manual Deployment

```
ssh pi@10.2.2.34 (ask Jan for password)
tmux attach-session -t auction-houses
/home/pi/auction-houses/target/debug/auction-houses
(CTRL+B => D)
exit
```
