<H1>Automate LangChain WebRAG Demo -> Chat with your PDF</H1>

This is a port of Jon Strabala's demo found: https://github.com/jon-strabala/easy-webrag-langchain-demo created by Michael Minichino and Terry Boon.

Pull the file down using 

git clone <insert name here>

Config execution
chmod 755 rh.sh

run 
./rh.sh

<h3>Configuration</h3>

<h4>Pre-reqs:</h4>
- Signed up for an account at cloud.couchbase.com/sign-up
- Created a bucket, a database user and created an API key for Couchbase control plane and OpenAI



Once streamlit has displayed the webpage:
<img width="741" alt="image" src="https://github.com/mks-couchbase/beeloud-hackathon/assets/81588469/b03eab20-fb8f-4371-a405-9120f773a500">

Couchbase Server Hostname is found on the **Connect Tab** for your Couchbase server -> _Public Connection String_

Couchbase database user can be defined following the **Database Access** link on the same page.

<img width="742" alt="image" src="https://github.com/mks-couchbase/beeloud-hackathon/assets/81588469/420cd8bc-6e36-48de-b136-aba2657ad0f6">

You can define and configure your couchbase Bucket, Scope and collection from within your Project. Select the Project tab and then the your project name.

Project API Key -> Select settings from within your project and follow the instructions on the page to create the **API Key**



Create a Bucket, Scope and Collection in the **Data Tools** tab inside your Project.

Create an Vector Store (Index) in the **Search** tab on the right side of the Data Tools screen 
<img width="1045" alt="image" src="https://github.com/mks-couchbase/beeloud-hackathon/assets/81588469/d7ab48a6-0d1e-40dd-8fe6-bd05f3f427a6">

How does this demo work?
You can upload your PDFs with custom data & ask questions about the data in the chat box.

For each question, you will get two answers:

one using RAG (Couchbase logo)
one using pure LLM - OpenAI (🤖).
For RAG, we are using LangChain, Couchbase Vector Search & OpenAI. We fetch parts of the PDF relevant to the question using Vector search & add it as the context to the LLM. The LLM is instructed to answer based on the context from the Vector Store.
