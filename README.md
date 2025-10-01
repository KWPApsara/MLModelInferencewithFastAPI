
# Car Recommender ML API

This project provides a machine-learning-based API that predicts a user's preferred car type based on their age and gender. The model is built using a Decision Tree Classifier and is served using **FastAPI**.

## Features

- Predicts car type based on age and gender
- REST API built with FastAPI
- Pre-trained machine learning model using a Decision Tree
- Easy to deploy and extend

## Getting Started

### Prerequisites

Ensure you have the following installed:

- Python 3.7+
- pip (Python package installer)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/car-recommender.git
   cd car-recommender
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Train the model (optional):
   ```bash
   python model_1.py
   ```

   This will train the model on the dataset (`cars.csv`) and save it to `car-recommender.joblib`.

### Running the API

1. Start the FastAPI server:
   ```bash
   uvicorn main:app --reload
   ```
   
2. Access the API at `http://127.0.0.1:8000`.

## API Endpoints

- **GET /**  
  Returns a simple welcome message.

- **POST /predict**  
  Predicts the car type based on user input.
  
  **Request body**:
  ```json
  {
    "age": 30,
    "gender": 1
  }
  ```
  
  **Response**:
  ```json
  {
    "predicted_vehicle_type": "SUV"
  }
  ```

## Deployment

To deploy this API on a cloud platform like Heroku, use the provided **Procfile**:
```bash
web: uvicorn main:app --host=0.0.0.0 --port=${PORT:-5000}
```


## Dataset

The `cars.csv` file contains user demographic data with the following columns:

- `age`: The age of the user
- `gender`: The gender of the user (0 = female, 1 = male)
- `vehicle_type`: The type of vehicle preferred by the user

## License

This project is licensed under the MIT License.
