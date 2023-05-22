# Problem Description
Create a “chat with docs” **webapp** that can be trained on the below and access the internet if needed:

* Website data (community forums, KB articles, user manuals, etc)
* PDF documents (user manuals, etc)
* Text files
* A user should be able to log on to a web app, search for specific information, and be provided with clear and helpful information based on the bot's knowledge with sources cited.
* The chat about the docs should continue while maintaining the previous context of the chat.
* Bot results can return generated code, and code should be formatted appropriately in the chat results.
* The backend and frontend functions should be separated so we can chat with the bot through an API or connect to Slack in the future.
* The website should have a gated admin section with Google Auth to allow me to quickly add new websites and PDFs to the LLM training data.
* I should be able to upload or copy-paste the URLs in bulk in the admin section.
* I should be able to easily change the model from GPT 3.5 to 4 and edit the system prompt and the main prompt template in the admin section.

**Acceptance Criteria** 
To win this bounty please let your work speak for itself.
Please provide examples of work that you have done in the past that is similar.
Provide a brief description of what your solution would be.
Estimate how long it would take.

**Technical Requirements** 

The backend should be built on Supabase Hybrid Search, Langchain and llamaindex
https://js.langchain.com/docs/modules/indexes/retrievers/supabase-hybrid
Converted docs should be cleaned prior to adding into the database
Frontend should be a clean web application hosted on Vercel using Edge Functions with streaming, React or Next.js.
Implement streaming of results from the LLM for better UX
Webapp and backend should be built with security best practices in mind.
The app will be open to the public at first but must be able to be gated behind authentication in the future, if needed, with relative ease.
The app should offer a solution for me to add additional websites or PDFs and rerun the training easily.
The code will need to be clean, documented, and maintainable by others in the future.


## Solution
-----------

Clone and run the app locally 

```bash 
# Clone app 
git clone https://github.com/LNshuti/chat-my-data.git

# Move into the application folder 
cd chat-my-data 

# Create conda environment 
conda env create --file=environment.yaml

# ADD OPENAI API KEY to your local env
conda env config vars set OPENAI_API_KEY=YOUR_API_KEY

# Install and run 
streamlit run chat_my_data.py
```

## Environment

Default configuration is in `.env`. Put custom config and secrets in `.env.local`, it will override the values in `.env`.

Check out [.env](./.env) to see what needs to be set.

In summary, create a `.env.local` with the following contents:

```
MONGODB_URL=<url to mongo, for example a free MongoDB Atlas sandbox instance>
HF_ACCESS_TOKEN=<your HF access token from https://huggingface.co/settings/tokens>
```