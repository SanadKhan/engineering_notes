# Caching

## What is it?

Caching stores frequently access data to a faster storage to reduce access time.

## Why do we need it?

To reduce the latency and make the response much faster as Databases are expensive and slower than memory. Repeated reads increase latency. Caching improves speed and reduces database load.

## Core Idea

Store hot data closer to the application.

Instead of:

Client → App → Database

Do:

Client → App → Cache → Database

## Types

- Client-side cache
- CDN cache
- Application cache
- Database cache
## How it works

- Request comes in
- Check cache
- If found → return (cache hit)
- Else → fetch from DB (cache miss)
- Store result in cache

## Advantages

- Faster reads
- Reduced DB load
- Better scalability

## Limitations

## Real-world examples

- Redis
- Memcached
- Browser cache
- CDN

## Related concepts

- [[Database Replication]]
- [[Load Balancer]]


## Takeaway

Use caching when read-heavy systems have repeated data access.

## Tags

#system-design #fundamental  #caching