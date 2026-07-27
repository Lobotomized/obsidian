[[DB Theory]]

## Key value pair 
**Data Format:** Key (String) $\rightarrow$ Value (Blob, String, Encrypted String, or Binary).
**Querying Ability:** You can **only** lookup or mutate data if you know the exact key. You cannot easily ask: _"Find all items where price is less than $20."_
**Performance:** Ultra-fast, near-constant read/write latencies (often sub-millisecond if in-memory) because there's zero processing overhead to parse content.
***Examples***: Redis, DynamoDB

***Document*** - Structured JSON or JSON-like format. Each object (document) has unique ID. 