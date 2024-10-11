# PDF Processing and Summarization Pipeline

## Project Overview

This project is a Python-based pipeline that processes PDF documents, extracts key content, generates summaries, and identifies keywords. The extracted information is stored in a MongoDB database for easy retrieval. This solution helps automate the process of analyzing large sets of PDF files, making it easier to manage and understand key points from each document.

### Features:
- Automatically download PDFs from provided URLs.
- Extract text content from PDFs using `PyPDF2`.
- Summarize the content by extracting the first few sentences.
- Extract important keywords using Natural Language Processing (NLP) techniques.
- Store the metadata, summaries, and keywords in MongoDB.

## Repository Structure
wasserstoff/AiInternTask/ │ ├── data/ # Contains dataset or PDF URL list │ └── Dataset.json # JSON file with PDF URLs │ ├── src/ # Main source code │ ├── main_pipeline.py # Main pipeline script │ └── utils.py # Utility functions (e.g., for downloading PDFs) │ ├── README.md # Project documentation (this file) ├── requirements.txt # Python dependencies ├── .gitignore # Files and directories to ignore in Git └── vercel.json # Vercel deployment settings (if applicable)

Install dependencies:
Create a virtual environment and install the required Python libraries:

python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
pip install -r requirements.txt

 Set up MongoDB:
You need to set up a MongoDB instance. You can either:

Use a local MongoDB instance.
Use MongoDB Atlas for a cloud-based solution.
Update the MongoDB connection string in the script to point to your MongoDB instance. Use an environment variable for the connection string for better security. In your .env file (which you should not commit), add:

MONGODB_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/test?retryWrites=true&w=majority
Add dataset:
Ensure the Dataset.json file contains URLs of the PDFs to be processed. The structure should be as follows:

json

{
  "Document 1": "https://example.com/sample1.pdf",
  "Document 2": "https://example.com/sample2.pdf"
}

 Run the pipeline:
You can run the main pipeline using:

bash
Copy code
python src/main_pipeline.py
This will:

Download the PDFs from the specified URLs.
Extract and summarize the content.
Extract keywords from the text.
Store the results in MongoDB.
Running Tests
(If applicable, mention if you have test scripts) To run the test scripts, use:

bash
Copy code
pytest tests/
Deploying the Application
This project can be hosted publicly using Vercel or any other deployment platform.

1. Deploy on Vercel:
Connect your GitHub repository to Vercel.
Vercel will automatically build and deploy your application based on the vercel.json file.
Visit the deployed link and share it.
Example Output
When running the pipeline, MongoDB will store documents like this:

json
Copy code
{
    "document_name": "sample.pdf",
    "path": "path/to/sample.pdf",
    "size": 123456,
    "ingestion_date": "2024-10-11",
    "summary": "First five sentences of the document...",
    "keywords": ["pdf", "processing", "summarization", "pipeline"]
}
Dependencies
The main libraries used in this project are:

PyPDF2 - for extracting text from PDFs.
nltk - for summarizing text and extracting keywords.
pymongo - for interacting with MongoDB.
requests - for downloading PDF files.
Install dependencies:
bash
Copy code
pip install -r requirements.txt
Contributing
Feel free to submit issues or contribute to this project by creating a pull request.

License
This project is licensed under the MIT License - see the LICENSE file for details.

Contact Information
Author: Ramsaikumar
GitHub: vuta-ramsai-kumar
markdown
Copy code

### Next Steps:
1. Customize any specific details about your project.
2. Include the appropriate content for your `requirements.txt`, dataset, and MongoDB configuration.


