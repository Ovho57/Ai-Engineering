# 06 — Retrieval and RAG

RAG means **Retrieval-Augmented Generation**. It finds relevant information and supplies it to a model.

    user question
        ↓
    retrieve relevant documents
        ↓
    add useful passages to model context
        ↓
    model answers using the passages
        ↓
    cite or identify sources

## Basic process
1. Split documents into chunks.
2. Store chunks and metadata.
3. Search for relevant chunks.
4. Select the best matches.
5. Give those matches to the model.

## Embeddings
An embedding is a vector representing text. Similar meanings may have nearby vectors. Embeddings support semantic search but can still retrieve irrelevant content.

Cosine similarity:

    similarity = (a · b) / (length(a) × length(b))

Here a · b is the dot product; length(a) and length(b) are vector norms.

## Common problems
- Irrelevant chunks.
- Missing or outdated documents.
- Retrieved content containing malicious instructions.
- An answer not supported by the source.

Treat retrieved text as untrusted data. Evaluate retrieval and answer quality separately.

## Exercise
Make a tiny search system over three notes and check whether it retrieves the correct note.