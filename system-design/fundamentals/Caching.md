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

- Cache invalidation is hard
- Stale data risk
- Extra memory cost

## Real-world examples

- Redis
- Memcached
- Browser cache
- CDN

## Related concepts

- [[Database Replication]]
- [[Load Balancer]]


## Takeaway

Use caching:
1- When read-heavy systems have repeated data access.
2- Data changes are often.
3- Slight stale data is acceptable.

Avoid cache when:
1- Data changes constantly.
2- Strong consistency is needed.
3- Memory budget is limited.

## Tags

#system-design #fundamental  #caching