# Automated AI News Summarizer (n8n + Google Gemini)

An automated workflow built in **n8n** that fetches the latest AI and technology articles from RSS feeds every morning, summarizes the top stories using **Google Gemini**, and delivers a clean digest straight to your Gmail inbox.

![Workflow Preview](workflow-preview.png)

## How It Works
1. **Schedule Trigger:** Runs automatically every day at 10:00 AM.
2. **RSS Feed Readers:** Pulls the latest articles from *NormalTech* (`normaltech.ai/feed`) and *AI Business* (`aibusiness.com/rss.xml`).
3. **Data Merger & Aggregator:** Combines both feeds and extracts the `title`, `link`, `content`, and `contentSnippet`.
4. **AI Summarization (LangChain + Gemini 3.1 Flash Lite):** Processes the aggregated articles and formats the Top 3 AI News items and Top 3 Technology Updates with all-caps headlines, 2–3 sentence summaries, and direct article links.
5. **Gmail Node:** Sends the formatted daily digest to the specified email address.

## How to Use This Workflow
1. Download the `ai-news-summarizer.json` file from this repository.
2. Open your **n8n** workspace, click the menu on the top right, and select **Import from File**.
3. Configure your **Google Gemini (PaLM) API** credentials in the Chat Model node.
4. Connect your **Gmail OAuth2** credentials in the Email Sender node and enter your recipient email address.
5. Activate the workflow!
