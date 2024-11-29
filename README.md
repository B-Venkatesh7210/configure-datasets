# Configure Datasets

This repository demonstrates how to use the **Mira SDK** to configure and manage datasets for use in various flows from the Mira Marketplace. It includes examples for creating and uploading datasets, enabling seamless integration of data-driven workflows.

Refer to the following [docs](https://docs.mira.network/sdk/configure_datasets) to understand the concept even better.

---

## **Features**
- Initialize the Mira SDK client with an API key.
- Create and configure datasets for flows.
- Upload datasets to the Mira Marketplace.
- Add dataset to your existing or new flow.
- Securely manage sensitive data using environment variables.

---

## **Prerequisites**
1. **Mira Account**: Ensure you have created an account at [Mira Marketplace](https://console.mira.network/).
2. **API Key**: Generate an API Key from your [Mira Account Dashboard](https://console.mira.network/account/api-keys).
3. **Python**: Ensure you have Python 3.10.0 installed. Currently, `mira-sdk@0.1.8` is compatible with Python 3.10.0.
4. **Dependencies**: Install the required libraries using the steps in the **Setup** section.

---

## **Setup**

### 1. Clone the Repository
```bash
git clone https://github.com/B-Venkatesh7210/configure-datasets.git
cd configure-datasets
```

### 2. Install Dependencies
```bash
pip install mira-sdk python-dotenv
```

### 3. Configure the API Key
- Create a `.env` file in the root of the project:
  ```bash
  touch .env
  ```
- Add your Mira Marketplace API key to the `.env` file:
  ```plaintext
  API_KEY=your_api_key_here
  ```

### 4. Run the Example Scripts
Run the example scripts for creating, uploading, and managing datasets:
```bash
python creating-dataset.py
python deploy-flow.py
python execute-flow.py
```

---

## **Usage**

### Example Input
The scripts allow you to work with datasets for flows. For instance, you can create and add source to a dataset as follows:
```python
from mira_sdk import MiraClient

client = MiraClient(config={"API_KEY": "YOUR_API_KEY"})

# Create dataset
client.dataset.create("author/dataset_name", "Optional description")

# Add URL to your data set (URL must be added to an existing dataset)
client.dataset.add_source("author/dataset_name", url="example.com")

# Add file to your data set (file must be added to an existing dataset)
client.dataset.add_source("author/dataset_name", file_path="path/to/my/file.csv")
```


## **Project Structure**
```plaintext
.
├── creating-dataset.py    # Script to create a new dataset and add sources to it
├── flow.yaml              # A YAML file to describe your flow and add dataset to it
├── deploy-flow.py         # Script to deploy your flow to the marketplace
├── execute-flow.py        # Script to execute the flow form marketplace
├── .env                 # Environment variables file (not tracked in Git)
├── .env.example         # Example environment variables file
├── README.md            # Project documentation
```

---

## **How It Works**
1. The `MiraClient` is initialized with an API key from the `.env` file.
2. The YAML file describes your custom flow with dataset.
3. **Create Dataset**: The `creating-dataset.py` script demonstrates how to define and register a new dataset.
4. **Deploy Flow**: The `upload-dataset.py` script shows deploy the flow to the marketplace.
5. **Execute Flow**: The `fetch-dataset.py` script shows how to execute the flow.

---

## **Dependencies**
- **[mira-sdk](https://pypi.org/project/mira-sdk/)**: To interact with the Mira Marketplace.
- **[python-dotenv](https://pypi.org/project/python-dotenv/)**: To securely load environment variables.

Install all dependencies with:
```bash
pip install mira-sdk python-dotenv
```

---

## **License**
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---

## **Contributing**
Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch (`feature/your-feature`).
3. Commit your changes.
4. Push the branch and open a pull request.

---

## **Contact**
If you have any questions or feedback, feel free to open an issue or contact [B-Venkatesh7210](https://github.com/B-Venkatesh7210).
