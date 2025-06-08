A step-by-step guide to building a reliable workflow that pulls weekly marketing news and sends it directly to your email.
When building with AI, the goal is to create something that works reliably, every single time. While complex, autonomous agents are on the horizon, the most effective solutions today often combine the power of AI with the reliability of code.

This tutorial will guide you through building a production-ready AI workflow. We'll leverage a powerful Large Language Model (Google's Gemini) to perform complex tasks like summarization, but we'll use simple, robust Python code to manage the overall process. This approach avoids common agent failures and results in a tool you can trust.

Let's build something that works.

What We Are Building
We will create a reliable, automated workflow that performs a two-step mission:

Search & Summarize: It will scour the web for marketing news published in the last week and use Google's Gemini model to create a concise, insightful summary.

Deliver: It will then reliably send this summary directly to your email inbox.

Step 1: Setting Up Your Toolbox
First, we need to gather our tools. All of these services offer generous free tiers, perfect for this project.

Google Colab: This will be our workshop. If you have a Google account, you have access to Colab. It's a free online tool that lets you write and run Python code directly in your browser, with no setup required.

Google AI API Key: This gives our workflow its "brain" using the Gemini model. Get your free key from Google AI Studio.

Tavily AI API Key: This provides our workflow with its web-searching superpower. Sign up for a free key at Tavily.ai.

Brevo API Key: This allows our workflow to send emails. Create a free account at Brevo.com and find your key in the "SMTP & API" section.

Step 2: Preparing Your Colab Notebook
Open a new notebook at colab.research.google.com. We'll organize our work in a few cells.

Cell 1: Install the Necessary Libraries

Run this command in the first cell to install all the Python packages we'll need.

!pip install langchain-google-genai langchain-community tavily-python brevo-python


Cell 2: Securely Store Your API Keys

We'll use Colab's built-in Secret Manager to keep your API keys safe.

Click the key icon (🔑) in the left sidebar.

Add a new secret for each key:

Make sure the "Notebook access" toggle is on for each secret.

Step 3: Writing the Workflow Code
Now for the main event! Copy and paste the following code into a new cell in your Colab notebook. This version uses a direct, scripted approach which is the most reliable method for this task.

Check the code library: Marketing_news_call.ipynb


Step 4: Configure and Run Your Workflow
Before you run the code, you need to make two small but crucial changes:

Set Your Sender Email: In the send_summary_email function, replace "your-verified-sender@example.com" with the email address you verified in your Brevo account.

Set Your Recipient Email: In the final section (# --- 3. RUN THE WORKFLOW ---), replace "your-email@example.com" with your own email address.

Now, run the cell! The script will execute the steps in a clear, predictable order. It will call the search_and_summarize_marketing_news function, store the result in the news_summary variable, and then reliably pass that variable to the send_summary_email function.

This approach is stable and removes the errors we saw with the agent. After a minute or two, check your inbox!

Beyond the Tutorial: What's Next?
Congratulations, you've just built a robust, automated workflow! This is a real-world example of how to build practical AI-powered tools. You can now:

Change the Topic: Modify the search query to track news about finance, technology, or your favorite hobby.

Change the Delivery: Modify the send_summary_email function to post the summary to a Slack channel or save it to a Google Doc.

Schedule It: Use a scheduling service to run your Colab notebook automatically every week.

The era of practical AI is here. By learning how to combine the power of AI with reliable code, you can build powerful and useful applications.

Can't follow? Check out my git to copy the code: 

Found this useful? Like and share this article to help others start their AI journey!

