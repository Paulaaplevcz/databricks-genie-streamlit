# Our experience integrating Genie into a Databricks App with Streamlit

We started this project by creating a **Databricks App** using a **Streamlit** interface.  
To do this, we accessed the side menu and navigated to Compute → Apps → Create App.  
We selected the Streamlit type, checked the "Data App" option, chose the desired SQL Warehouse, and named the application.

The creation process takes a few minutes, but soon the app is ready for editing and deployment directly within the Databricks environment.

---

## Training Genie

With the dataset loaded, we trained **Genie** so it could understand the data and respond using natural language queries.

---

## The integration challenge

Our biggest challenge was: how to connect Genie to the app in an interactive way?

After a lot of research and experimentation, we found this [repository by @datasciencemonkey](https://github.com/datasciencemonkey/agents-on-databricks/tree/main), which was essential to help us understand how the API-based integration works — especially for setting up conversational flows with Genie.

---

## What we learned

From that foundation, we were able to:

- Understand how to retrieve and use the `space_id`
- Initiate a conversation with `conversation_id`
- Send and receive messages with `message_id`
- Properly configure `DATABRICKS_HOST` and the personal access token (PAT)
- Display Genie’s responses dynamically within the Streamlit interface

The final application, built as a Databricks App with Streamlit, was able to interact with Genie smoothly.  
Below is a screenshot showing the app in action:

![App interface with integrated Genie](img.png)

---

## Technical aspects of the implementation

Some technical aspects we explored during the project include:

- **Conversation flow management with Genie:** We used public APIs to initiate conversations and track their status using `conversation_id` and `message_id`.
- **Handling structured responses:** The app was designed to handle both plain-text answers and tabular attachments returned by Genie, displaying them directly in the Streamlit interface.
- **Interactive UI with memory:** The interface was built using `st.chat_message` and `st.session_state`, allowing persistent conversational history between the user and Genie.
- **Error handling and timeout control:** We implemented proper exception handling and timeouts to ensure a stable and responsive experience, even when the API is slow or encounters errors.

---

This was a great opportunity to better understand how Databricks Apps, the SDK, and the Genie API work together.  
We documented our experience here as a reference and to help others exploring similar integrations.
