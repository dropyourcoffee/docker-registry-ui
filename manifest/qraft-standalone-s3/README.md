# Example for issue #20 (HTTPS supports)

Docker Compose consist of 3 containers:
 - registry hosting over HTTP on port 5000
 - joxit/registryui over HTTP on port 80 with nginx for reverse-proxying {registry+registryui} over HTTPS
 - minio instance to bridge Amazon S3 cloud storage service for image persistence.

Generating a self signed certificate:

```
openssl req -newkey rsa:2048 -nodes -keyout nginx/privkey.pem -x509 -days 3650 -out nginx/fullchain.pem
```

