# ioshdev_key-cache

Crawls a URL, follows redirects to the canonical destination, and indexes the page metadata so you can query it later.

## Run
```
npm install
npm run start:dev
```

## Configuration
`.env`:
```
ELASTICSEARCH_HOST=127.0.0.1:9200
ELASTICSEARCH_INDEX=links
MONGODB_URI=mongodb://127.0.0.1:27017/ioshdev_key-cache
REDIS_URL=redis://127.0.0.1
```

## Usage

Submit a crawl:
```
curl -d '{"url": "https://example.com/a/short"}' -H "Content-Type: application/json" "http://localhost:3000/api/v1/link"
```

List everything indexed:
```
curl "http://localhost:3000/api/v1/link"
```

Delete one:
```
curl -X DELETE -d '{"url": "https://example.com/a/short"}' -H "Content-Type: application/json" "http://localhost:3000/api/v1/link"
```
