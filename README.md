# cv-rag-n8n
# CV RAG Chatbot

I built a RAG (Retrieval-Augmented Generation) chatbot that 
only answers questions related to my CV. Nothing else — if 
you ask it something unrelated, it politely refuses.

## Why I built this
Instead of someone scrolling through my CV manually, they can 
just ask questions and get instant answers about my experience, 
skills and background.

## How it works

### Ingestion
I read the CV file from disk, extracted the text from the PDF, 
and uploaded it to Pinecone as vectors using Cohere embeddings. 
This was the tricky part — I got stuck figuring out how to 
properly pass the text into Pinecone through n8n, but once I 
understood how the Default Data Loader worked it all clicked.

### Retrieval
Built an AI Agent using Groq model that fetches relevant data 
from Pinecone based on the user's question and generates a 
response — strictly limited to CV content only.

## Tech Stack
- n8n — workflow automation
- Pinecone — vector database
- Cohere — embeddings
- Groq — AI model for responses

## How to Import
1. Open n8n
2. Click Add Workflow → Import from File
3. Select the .json file
4. Add your own API credentials
