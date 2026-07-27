[[DB Theory]]

## Key value pair 
**Data Format:** Key (String) $\rightarrow$ Value (Blob, String, Encrypted String, or Binary).
**Querying Ability:** You can **only** lookup or mutate data if you know the exact key. You cannot easily ask: _"Find all items where price is less than $20."_
**Performance:** Ultra-fast, near-constant read/write latencies (often sub-millisecond if in-memory) because there's zero processing overhead to parse content.
***Examples***: Redis, DynamoDB

***Document:***  Structured JSON or JSON-like format. Each object (document) has unique ID. 
**Querying Ability:** You can query, index, and aggregate based on internal fields. You can give questions like "Give me all documents that have field with value X".
***Performance:*** Slightly higher latency than Key Value Pair



(
Add Relational DB's, Wide Column DB's, Graph DB's
)