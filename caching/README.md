Caching
: Storing precomputed data at some place so as to not fetch again from Database.
- global Cache
- loacl Cache(local app server itself)
- in-browser caching

Caching related Problem
- limited storage
- keep data sync
   - TTL

Netflix OpenConnect

### Cache sync policies
- Write Through (Through n through)
   - Server write on Cache
   - Server write on DB
   - if any fail then request failed  
   - if success then hurrey
- Write Back (backend sync DB)
   - write cache
   - give success
   - Asynchronously update DB in backend
- Write Around (around the cache)
   - Write DB first
   - then sync cache over the time.


CDN working
- Replication
- Anycast (Multiplexing)

Cache Eviction Strategies
- LRU
- LFU
- MRU
- LIFO
- FIFO


Lazy Invalidation