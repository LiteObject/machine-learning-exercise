# Overview of Embeddings and Vector Databases

## What are embeddings?
An embedding is a vector (list) of floating point numbers. The distance between two vectors measures their relatedness.

Embeddings are commonly used for:
- Search
- Clustering
- Recommendaions
- Anomaly detection
- Diversity measurement
- Classification

```mermaid
flowchart LR
    d[Data:\nLorem ipsum dolor sit amet...]
    -->e[Embedding model\nConverts into an array of numbers]
    -->v[Vector\nDatabase]
```
## Create embeddings

Example requests:
```bash
curl https://api.openai.com/v1/embeddings \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -d '{
    "input": "Your text string goes here",
    "model": "text-embedding-ada-002"
  }'
```
Example response:
```bash
{
  "data": [
    {
      "embedding": [
        -0.006929283495992422,
        -0.005336422007530928,
        ...
        -4.547132266452536e-05,
        -0.024047505110502243
      ],
      "index": 0,
      "object": "embedding"
    }
  ],
  "model": "text-embedding-ada-002",
  "object": "list",
  "usage": {
    "prompt_tokens": 5,
    "total_tokens": 5
  }
}
```