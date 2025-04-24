# Text Embedding and Storage System

This project is a text embedding and storage system that processes text documents, splits them into smaller chunks, generates embeddings for each chunk, and stores them in a vector database. It also includes an API for uploading and processing new documents.

## Features

- **Text Splitting**: Splits large text documents into smaller chunks using a recursive character text splitter.
- **Text Embedding**: Generates embeddings for text chunks using Google Generative AI Embeddings.
- **Vector Storage**: Stores embeddings in a Chroma vector database for efficient retrieval.
- **API**: Provides a Flask-based API for uploading and processing new documents.
- **Testing Scripts**: Includes scripts for testing text splitting, embedding, and API functionality.

## Project Structure

- **`api.py`**: Flask API for handling document uploads and processing.
- **`embed_and_store.py`**: Handles embedding generation and storage in the Chroma vector database.
- **`split.py`**: Contains the logic for splitting text into smaller chunks.
- **`text_split.py`**: A script for testing text splitting and embedding functionality.
- **`post.py`**: A script for testing the API by sending a sample document.


## Setup
- Clone this repository using
  ```sh
  git clone https://github.com/GrinchBob43/knotebooklm_rag_service.git
  cd knotebooklm_rag_service
  ```
- create a .env file with
  ```sh
  nano .env
  ```
  Then set variable ```GOOGLE_API_KEY='<My google developer API key>'```
  Then use ```Ctrl + X``` to exit and save
- Install dependencies with:
  ```sh
  pip install requirements.txt
  ```
- Run the API with
  ```sh
  python3 api.py
  ```

## Usage
Testing Text Splitting and Embedding:
 Run the text_split.py script to test text splitting and embedding functionality
 
## Testing the API
Run the post.py script to test the API


## Adding New Documents
Send a POST request to the /new endpoint of the API with the following metadata:

{
  "text": "<your-text>",
  "doc_id": "<document-id>",
  "user_id": "<user-id>",
  "notebook_id": "<notebook-id>"
}

- A successfull response will look something like this:

{
  Request successful!
{'embedding_ids': ['586925ae-ec38-45a7-9947-06e47f602818', '282c88d5-1230-49aa-832d-4f200cc10ce6', '688f07b8-579b-4e72-ada1-d5b0f912b360', '6522495a-4686-4ab9-b057-5025d978abb0', '72bc660b-d6f1-4a9f-a679-6b64382d49f4', '5379c669-cf7e-4dd8-a7a1-aedad34c8ec0', '4bcd29b0-0cf0-46a1-a9f2-daf34e606a93', '34b0d65b-b129-4cec-bc61-1b4a36c7e197', 'a766c10b-47e5-4178-b080-c4f752865577', '05f76bad-d671-4a11-8153-5d42c90b7192', 'b98d64d3-fadc-44dc-b195-b01699864b00', '68754952-3aa2-4a9f-8cde-5594b92107ce', '1a37796e-ba55-484f-b3b0-bc5f2017c42d']}
}

- If you don't include one of the parameters in your json payload you will get an error like this:

{
  Error: 400
{
  "error": "Bad request"
}
}
## Notes
The Chroma vector database is stored in the chroma_langchain_db/ directory.
Ensure that the chroma_langchain_db/ directory is writable for the application.
