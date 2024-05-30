# Multi-Document Agentic RAG with LlamaIndex

## Overview
This project demonstrates how to build a Multi-Document Agent using LlamaIndex. The agent is designed to handle multiple research papers and answer queries based on the content of these papers. The project leverages the OpenAI API for language modeling and a variety of tools for document processing and retrieval.

## Setup

### Prerequisites
- Python 3.12+
- Necessary Python packages (listed in `requirements.txt`)

### Installation
1. Clone the repository:
    ```sh
    git clone https://github.com/da-ros/MultiDocAgent.git
    cd MultiDocAgent
    ```

2. Create a virtual environment and activate it:
    ```sh
    python -m venv env
    source env/bin/activate  # On Windows, use `env\Scripts\activate`
    ```

3. Install the required packages:
    ```sh
    pip install -r requirements.txt
    ```

4. Set up your OpenAI API key:
    - Ensure you have an API key from OpenAI.
    - Create a file named `.env` and add your API key:
      ```sh
      OPENAI_API_KEY=your_openai_api_key
      ```

### Running the Project
1. Ensure the necessary PDF documents are in the project directory.

2. Run the script:
    ```sh
    python L4_Building_a_Multi-Document_Agent.py
    ```

## Project Structure
- `L4_Building_a_Multi-Document_Agent.py`: Main script for setting up and running the agent.
- `helper.py`: Contains helper functions for getting API keys and other utilities.
- `utils.py`: Contains functions for document processing and tool creation.
- `requirements.txt`: List of required Python packages.

## How It Works

### Initial Setup
The script begins by setting up the environment and importing necessary libraries. It retrieves the OpenAI API key using a helper function and applies `nest_asyncio` to handle asynchronous operations.

### Document Processing
The agent is set up over a collection of research papers. For each paper, the script uses `get_doc_tools` from `utils.py` to create a vector tool and a summary tool, which are then stored in a dictionary.

### Agent Creation
The agent is created using the `FunctionCallingAgentWorker` class from LlamaIndex, initialized with the tools created for each document. The agent can handle queries and provide responses based on the content of the papers.

### Querying the Agent
The agent is queried with specific questions about the research papers. The queries and their corresponding responses are printed out.

### Extending the Agent
The script demonstrates extending the agent to handle more documents by setting up additional tools and creating an index for efficient retrieval. The extended agent can handle more complex queries involving multiple documents.

## Usage

### Example Queries
You can query the agent with various questions about the research papers. For example:
- "Tell me about the evaluation dataset used in LongLoRA."
- "Give me a summary of both Self-RAG and LongLoRA."
- "Compare and contrast the LoRA papers (LongLoRA, LoftQ)."

### Output
The agent will provide detailed responses based on the content of the papers, leveraging the tools created during the setup phase.

## Contributing
If you wish to contribute to this project, please follow these steps:
1. Fork the repository.
2. Create a new branch:
    ```sh
    git checkout -b feature-branch
    ```
3. Make your changes and commit them:
    ```sh
    git commit -m "Description of changes"
    ```
4. Push to the branch:
    ```sh
    git push origin feature-branch
    ```
5. Create a pull request.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgements
Special thanks to the developers of LlamaIndex and OpenAI for their APIs and tools that made this project possible.
