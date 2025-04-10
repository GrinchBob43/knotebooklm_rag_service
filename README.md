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
- **`test.txt`**: A sample text file used for testing.
- **`chroma_langchain_db/`**: Directory containing the Chroma vector database.
- **`.gitignore`**: Specifies files and directories to be ignored by Git.


## Usage
Testing Text Splitting and Embedding:
Run the text_split.py script to test text splitting and embedding:
 
## Testing the API
Run the post.py script to test the API:


## Adding New Documents
Send a POST request to the /new endpoint of the API with the following JSON payload:

{
  "text": "<your-text>",
  "doc_id": "<document-id>",
  "user_id": "<user-id>",
  "notebook_id": "<notebook-id>"
}
## Notes
The Chroma vector database is stored in the chroma_langchain_db/ directory.
Ensure that the chroma_langchain_db/ directory is writable for the application.
