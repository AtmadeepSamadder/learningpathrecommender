# learningpathrecommender
Project Overview
The Personalized Learning Path Agent is an intelligent system designed to help students navigate large course catalogs by creating custom educational journeys. It utilizes a Retrieval-Augmented Generation (RAG) architecture to match a student's unique background and goals with specific courses from a dataset of over 800 entries.

Technical Architecture
The system is built on a modular pipeline that ensures data is processed efficiently and logic is applied accurately:


Data Layer: Processes a Coursera dataset (CSV) containing course titles, organizations, ratings, difficulty levels, and enrollment numbers.

Retrieval Layer: Uses semantic search to find the most relevant courses. Instead of simple keyword matching, it leverages transformer-based embeddings to understand the meaning behind a user's goal.

Reasoning Layer: Utilizes the Qwen2.5-7B-Instruct model via Hugging Face Inference APIs to act as the academic advisor, interpreting the retrieved data to build a logical path.

Interface Layer: An interactive command-line interface that allows users to select from predefined options or enter custom profiles and goals.

Key Features

Metadata Compression: Combines multiple data columns into a single searchable context for the AI, ensuring the advisor understands the provider and difficulty of each recommendation.

Dynamic Personalization: Adjusts its recommendations based on whether the user identifies as an undergraduate, a working professional, or a hobbyist.


Zero-Inference Retrieval: Treats user data as factual constraints to ensure the generated path is grounded in the available catalog.

Interactive Menu System: Provides a structured way for users to input their data, reducing errors and improving the quality of the generated advice.

Technical Stack
Programming Language: Python

Libraries: Pandas (Data Manipulation), Scikit-learn (Similarity Logic), Huggingface_hub (LLM Connectivity).

Models: Qwen2.5-7B-Instruct (Reasoning) and all-MiniLM-L6-v2 (Embeddings).

Implementation Steps

Data Cleaning: The system cleans the dataset, converting enrollment strings into numerical values and preparing metadata strings.

User Input: The agent captures the user's current profile and learning objectives through an interactive loop.


Semantic Matching: The system calculates the mathematical similarity between the user's goal and the course catalog to retrieve the top candidates.

Contextual Generation: The retrieved courses are passed to the LLM, which generates a 3-step path with detailed justifications for each step.

Usage Example
User Goal: Specializing in AI for Medical Diagnosis.

User Profile: AIML Undergraduate.


Agent Output: A structured path starting with foundational AI courses, moving to specialized medical imaging courses, and concluding with medical treatment models found in the catalog
