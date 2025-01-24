# Formula_1_Regulations_RAG_Systems

## Introduction
Formula 1 is a sport renowned for its high-speed drama, technological innovation, and global fan base. However, navigating its complexities—such as intricate race strategies, evolving regulations, and driver statistics—can be challenging. Fans often struggle to find comprehensive, accessible information, while the FIA, the sport's governing body, has faced criticism for inconsistent regulatory decisions that impact race outcomes and championships.

## Background
An example of the challenges within Formula 1 is the controversial 2021 Abu Dhabi Grand Prix, where regulatory decisions heavily influenced the championship outcome. These controversies underscore the need for greater transparency and data-driven decision-making in the sport. 

The Formula 1 Regulation RAG System aims to bridge this gap by combining cutting-edge AI technology with a user-friendly platform to provide:
       
- Easy access to Formula 1 regulations, track details, and historical data.
- A decision-support system for the FIA to ensure fair and accurate penalties.
- An engaging platform for fans to predict race outcomes and explore the intricacies of the sport.

## Project Overview
### Objective 
The goal of the Formula 1 Regulation RAG System is to create a Retrieval-Augmented Generation (RAG) platform that delivers:

- Comprehensive insights into Formula 1 regulations and race data.
- Interactive features such as a predictive game for fan engagement.
- Decision-support tools for race incidents, ensuring fairness and consistency.

### Scope
The system offers a suite of features for:

- **Fans**: Access to real-time race data, historical insights, and interactive predictions.
- **FIA Officials**: Real-time regulation analysis to support incident-based decision-making.
- **Content Creators and Journalists**: Quick, reliable access to F1 data for enhanced content creation.

## Key Features
### Information Hub
- Access driver profiles, track details, and race analytics.
- Learn about F1 regulations in an easily digestible format.

### RAG-Powered Chatbot
- Ask complex questions about regulations, historical incidents, and live race data.
- Get clear, accurate answers powered by Pinecone and OpenAI GPT-4.

### Predictive Game Module
- Make predictions about race outcomes and driver performance.
- Engage with F1 strategies through an interactive, gamified experience.

### Decision Support for FIA
- Instantly analyze incidents and suggest penalties based on FIA regulations.
- Enhance transparency and consistency in decision-making.

## Methodology
### Data Sources
- **FIA Regulation Documents**: Scraped from FIA's official website.
- **OpenF1 API**: Provides real-time race data, standings, and driver statistics.
- **Custom Synthesized Data**: Includes historical race incidents and penalties.

### Technologies Used
#### Backend
- **FastAPI**: A modern, fast (high-performance) web framework for building APIs with Python.
  - Used for handling backend operations and serving API endpoints.
  - Provides asynchronous support for efficient data handling.

- **Snowflake**: A cloud-based data warehousing solution.
  - Used for storing structured data, such as regulations, race results, and user interactions.
  - Ensures scalability and high performance for complex queries.

- **Pinecone**: A vector database designed for similarity search.
  - Used for storing and retrieving text embeddings generated by OpenAI GPT-4.
  - Enables efficient retrieval of relevant regulation clauses based on user queries.

#### Frontend
- **Streamlit**: An open-source app framework for Machine Learning and Data Science projects.
  - Provides an interactive user interface with dropdown menus, chat UI, and data visualizations.

#### Data Processing
- **Adobe Extractor**: Used to extract text from FIA regulation PDFs.
  - Ensures accurate and structured extraction of regulatory content.
- **Airflow**: An open-source workflow management platform.
  - Automates data scraping, ingestion, and processing tasks.

#### AI & Machine Learning
- **OpenAI GPT-4**: The core engine for delivering RAG-based responses.
  - Generates accurate and context-aware answers to user queries.
  - Powers the chatbot and decision-support features.

- **Scikit-Learn**: A machine learning library in Python.
  - Used to develop the predictive game module.
  - Implements various classification and regression models for race outcome predictions.

## Project Plan and Timeline
### Phase 1: Core Data Setup and Backend Foundation (Week 1)
1. Extract and store FIA regulation documents.
2. Set up Snowflake and Pinecone databases.
3. Develop the FastAPI backend for handling data requests.

### Phase 2: Build Minimum Viable Product (MVP) (Week 2)
1. Create a basic Streamlit interface with dropdowns and chatbot capabilities.
2. Integrate real-time race data using the OpenF1 API.
3. Deploy the RAG bot for regulation-based queries.

### Phase 3: UI Finalization and Testing (Week 3)
1. Enhance the user interface for a seamless experience.
2. Conduct functional and user acceptance testing.
3. Document the platform for ease of use and deployment.

## Risks and Mitigation Strategies
### Risks
1. **Time Constraints**: Limited development window.
2. **Data Integration Challenges**: Potential compatibility issues between APIs and databases.
3. **API Reliability**: Outages or usage rate limitations may hinder real-time data feeds.
4. **Testing Limitations**: Insufficient time for thorough testing may leave undetected issues.

### Mitigation
1. Prioritize core features and use parallel development for efficiency.
2. Standardize data formats and perform incremental integration testing.
3. Cache data to mitigate API reliability issues.
4. Focus on critical bug fixes during testing to ensure core functionality.

## Deliverables
### Interactive Platform
- Access to regulations, race data, and predictive tools.
- Chatbot for regulation-related queries.

### Predictive Game
- Engaging feature to increase fan interaction and knowledge of race dynamics.

### Documentation
- Comprehensive guide for users and developers.

## Setup Instructions
### Step 1: Clone the Repository
Clone the repository to your local machine:
```bash
git clone https://github.com/your-repo/formula1-regulation-rag.git
cd formula1-regulation-rag
```

### Step 2: Install Dependencies
Install all required dependencies using Poetry:
```bash
poetry install
```

### Step 3: Configure Environment Variables
Create a `.env` file in the root directory and add the following variables:
```env
OPENAI_API_KEY=your_openai_api_key
SNOWFLAKE_USER=your_snowflake_user
SNOWFLAKE_PASSWORD=your_snowflake_password
SNOWFLAKE_ACCOUNT=your_snowflake_account
S3_BUCKET_NAME=your_s3_bucket_name
OPENF1_API_KEY=your_openf1_api_key
```

### Step 4: Initialize Databases
Set up Snowflake for structured data:
1. Create tables for storing regulatory clauses, historical race information, and user data.
2. Populate initial data for testing.

Populate Pinecone with embeddings:
- Use the text embeddings from OpenAI to index regulatory content in Pinecone.

Configure Amazon S3:
- Store FIA PDFs in an S3 bucket for text extraction.

### Step 5: Run Airflow for Automation
Initialize Airflow and set up data scraping:
```bash
airflow db init
airflow webserver -p 8080
airflow scheduler
```

### Execution Instructions
#### Step 1: Start the Backend Server
Run the FastAPI server to handle backend operations:
```bash
poetry run uvicorn fastapi_app:app --reload
```

#### Step 2: Start the Frontend Application
Run the Streamlit application for the user interface:
```bash
poetry run streamlit run app.py
```

#### Step 3: Access the Application
Open your browser and navigate to:
```arduino
http://localhost:8501
```

## Conclusion
The Formula 1 Regulation RAG System is designed to transform the way Formula 1 fans, professionals, and officials interact with the sport. By integrating advanced AI capabilities with real-time data access and an engaging user interface, the platform will enhance transparency, education, and entertainment. Whether you're a casual fan or a decision-maker in the FIA, the system offers tools to enrich your understanding and engagement with Formula 1.

## References
- Formula 1 Revenue Report
- FIA Official Website

