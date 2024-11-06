# YouTube Comment Sentiment Analysis Chrome Plugin

This project involves a **Chrome plugin** that performs sentiment analysis on YouTube comments, determining whether the comment is **positive**, **negative**, or **neutral**. The backend of the project is built using **Flask**, providing a RESTful API that handles requests from the frontend (Chrome plugin) and processes the sentiment analysis.

## Table of Contents
- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Backend API](#backend-api)
  - [API Endpoints](#api-endpoints)
  - [How to Use with Postman](#how-to-use-with-postman)
  - [Flask API Setup](#flask-api-setup)
- [Running the Project Locally](#running-the-project-locally)
- [License](#license)

## Project Overview

The YouTube Comment Sentiment Analysis Chrome Plugin is designed to automatically analyze the sentiment of YouTube comments. It connects to a backend Flask API that handles sentiment prediction using machine learning models trained with a **Reddit dataset**. The sentiment classification can be used to assess public opinions, analyze trends, or provide insights into online discussions.

The backend API is built using **Flask**, and the communication between the frontend (Chrome plugin) and backend is handled through RESTful API requests. The API is capable of receiving a comment, processing it, and returning the predicted sentiment.

## Technologies Used

- **Flask** - Web framework to create the backend API
- **Python** - Programming language used for the backend
- **MLflow** - Model tracking and management
- **DVC** - Data version control to track datasets and experiments
- **LightGBM, XGBoost, TF-IDF** - Machine learning models and feature extraction techniques
- **Postman** - Tool used to test and interact with the API
- **HTML, JavaScript** - Frontend of the Chrome plugin (Not covered here)
- **Chrome Extension** - User interface for interacting with the sentiment analysis service -`https://github.com/sahilbhardwaj23/youtube-comment-Chrome-Plugin`

## Backend API

### API Endpoints

The backend provides the following API endpoints to interact with the sentiment analysis service:

#### 1. **/predict** [POST]
- **Description**: Analyzes the sentiment of a given YouTube comment.
- **Request Body**:
  ```json
  {
    "comment": "This is a sample YouTube comment."
  }
  ```
- **Response**:
  ```json
  {
    "sentiment": "positive"
  }
  ```

#### 2. **/status** [GET]
- **Description**: Check if the Flask API server is running.
- **Response**:
  ```json
  {
    "status": "API is running"
  }
  ```

### How to Use with Postman

1. **Install Postman** if you don't have it already from [here](https://www.postman.com/downloads/).
2. **Run the Flask API locally** (instructions below).
3. Open Postman and set the request type to **POST**.
4. Enter the following URL:
   ```
   http://127.0.0.1:5000/predict
   ```
5. In the **Body** tab of Postman, choose **raw** and set the type to **JSON**. Paste the following JSON request:
   ```json
   {
     "comment": "This is a sample YouTube comment."
   }
   ```
6. Click **Send**. The response will contain the sentiment prediction, e.g.,:
   ```json
   {
     "sentiment": "positive"
   }
   ```

### Flask API Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/sahilbhardwaj23/Youtube-comment-Sentiment-Analysis.git
   cd Youtube-comment-Sentiment-Analysis
   ```

2. **Install dependencies**:
   Ensure you have **Python 3.x** and **pip** installed. Then, install the required libraries:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Flask API**:
   ```bash
   python app.py
   ```
   By default, the server will run on `http://127.0.0.1:5000`.

4. **Test the API**:
   Use Postman or any HTTP client to send requests to the API (as mentioned above).

## Running the Project Locally

1. Clone the repository:
   ```bash
   git clone https://github.com/sahilbhardwaj23/Youtube-comment-Sentiment-Analysis.git
   cd Youtube-comment-Sentiment-Analysis
   ```

2. Set up a Python virtual environment (recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install the necessary Python packages:
   ```bash
   pip install -r requirements.txt
   ```

4. Run the Flask server:
   ```bash
   python flask_app\app.py
   ```
   This will start the Flask API on `http://127.0.0.1:5000`.

5. Open **Postman** or use `curl` to test the endpoints as described above.

