# Dutch Governments synthetic data generation

This script generates synthetic data by accessing the OpenAI GPT3.5-Turbo API. It collects 16,000 records of text data (summarization and Q&A) related to 1,620 products and services offered by various Dutch governments. The purpose is to train LLM (Language Model).

Here's how the process works:

1. The script uses a list of all Dutch products and services provided by State Governments, Provinces, Waterschappen, and Municipalities.
2. This list is first unpivoted, resulting in 1,620 records, each representing a product or service for a specific target, either a company or a citizen.
3. For each record, a Prompt is generated, which is then sent to the OpenAI API.
4. The result from the API is received in the form of a JSON string, which is added to a dataframe.
5. Finally, the dataframe is written to disk.

Steps 1 to 5 are performed twice:
A. The first time, it creates a file with context and summary, containing 1,620 records.
B. The second time, it generates a file with the 10 most frequently asked questions and their corresponding answers, totaling 16,200 records.

Both files contain an identifier, allowing them to be joined together into one comprehensive dataset.


BACKGROUND

The Dutch Government has a list of all the products and services (for all different governments). It can be found at:https://standaarden.overheid.nl/upl. An explaination can be found at: https://standaarden.overheid.nl/upl/doc/Toelichting-UPL.pdf

This last document titled "Toelichting UPL" is a Dutch document that provides an explanation of the Uniform Product Language (UPL). The UPL is a standard language for describing products and services in the public sector. It is used to improve the quality of product and service descriptions, making them more understandable and comparable.

The document explains the background and purpose of the UPL, its structure, and how it can be used. It also provides examples of UPL descriptions and discusses the benefits of using the UPL, such as improved communication and transparency.

