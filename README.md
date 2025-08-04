Here’s a README file for your Machine-Lifetime-Prediction repository, tailored to your notebook and the Streamlit application you generated. This README provides a clear overview, setup steps, usage, and credits.

---

# Machine Lifetime Prediction

This repository contains an IBM AutoAI-generated pipeline and Streamlit application for predicting manufacturing machine failures based on sensor data. The notebook demonstrates incremental learning with Watsonx.ai and enables easy model deployment and interactive predictions through a web UI.

## Features

- **IBM AutoAI Pipeline**: Incremental learning and batch training for multiclass machine failure prediction.
- **Streamlit Web App**: User-friendly interface to input key features and get real-time predictions/visualizations.
- **Online Deployment**: Integrates with IBM Watsonx.ai for model deployment and scoring.
- **Visualization**: Probability bar chart for each failure class displayed with every prediction.

## Notebook Overview

- Incremental training using IBM AutoAI (`Machine_liftime_prediction.ipynb`)
- Batch data loading, partial_fit, and evaluation
- Model saving and deployment to IBM Watsonx.ai
- Streamlit app code generation for interactive predictions

## Streamlit Application

The app lets users input the following features:

- Air temperature [K]
- Process temperature [K]
- Rotational speed [rpm]
- Torque [Nm]
- Tool wear [min]

It then predicts the failure type and, if available, shows a probability chart for all classes.

## Setup

### Prerequisites

- Python 3.8+
- IBM Cloud Account with Watsonx.ai access
- IBM Cloud API Key
- Model deployed to IBM Watsonx.ai

### Dependencies

Install all dependencies via pip:

```bash
pip install streamlit ibm-watsonx-ai autoai-libs scikit-learn==1.3.* lale~=0.8.3 snapml==1.14.* matplotlib pandas
```

If running in a Colab or remote environment, also install:

```bash
pip install ngrok pyngrok
```

### Configuration

Set your IBM Cloud API key and (optionally) ngrok token as environment variables:

```bash
export api_key=YOUR_IBM_CLOUD_API_KEY
export NGROK_AUTHTOKEN=YOUR_NGROK_TOKEN  # If using ngrok tunneling
```

Edit `app.py` and set the following variables according to your IBM Cloud deployment:

- `deployment_url`
- `project_id`
- `model_id`

## Running the Streamlit App

```bash
streamlit run app.py
```

If using ngrok (for remote/Colab use):

```bash
ngrok http 8501
```

Then open the ngrok URL shown in your terminal.

## Usage

1. Launch the app as above.
2. Enter sensor values for the required features.
3. Click “Predict” to receive the predicted failure class.
4. If available, view the probability bar chart for all classes.

## Development Notes

- The AutoAI-generated pipeline is best used with the same data schema as during training.
- Model deployment and scoring require valid IBM Cloud credentials.
- For security, use environment variables or Streamlit secrets for sensitive values.

## References

- [IBM AutoAI Documentation](https://www.ibm.com/cloud/watson-studio/autoai)
- [Watsonx.ai Documentation](https://dataplatform.cloud.ibm.com/docs/content/wsj/analyze-data/autoai-notebook.html)
- [Streamlit Documentation](https://docs.streamlit.io/)

## License

Licensed Materials – Copyright © 2025 IBM.  
This repository uses the ILAN License as described in the notebook.

---

Let me know if you want any additional sections or more detailed usage instructions!
