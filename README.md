 

**Our mission is to empower individuals and organizations with accurate, unbiased, and factual information by leveraging the power of AI.**

## Why GPT Researcher?

- To form objective conclusions for manual research tasks can take time, sometimes weeks to find the right resources and information.
- Current LLMs are trained on past and outdated information, with heavy risks of hallucinations, making them almost irrelevant for research tasks.
- Solutions that enable web search (such as ChatGPT + Web Plugin), only consider limited resources that in some cases result in superficial conclusions or biased answers.
- Using only a selection of resources can create bias in determining the right conclusions for research questions or tasks. 

## Architecture
The main idea is to run "planner" and "execution" agents, whereas the planner generates questions to research, and the execution agents seek the most related information based on each generated research question. Finally, the planner filters and aggregates all related information and creates a research report. The agents leverage both gpt3.5-turbo-16k and gpt-4 to complete a research task.

<div align="center">
<img align="center" height="500" src="https://cowriter-images.s3.amazonaws.com/arch.png">
</div>


More specifically:
* Generate a set of research questions that together form an objective opinion on any given task. 
* For each research question, trigger a crawler agent that scrapes online resources for information relevant to the given task.
* For each scraped resources, summarize based on relevant information and keep track of its sources.
* Finally, filter and aggregate all summarized sources and generate a final research report.

## Demo
https://github.com/assafelovic/gpt-researcher/assets/13554167/a00c89a6-a295-4dd0-b58d-098a31c40fda

## Tutorials
 - [How to Install](https://www.loom.com/share/04ebffb6ed2a4520a27c3e3addcdde20?sid=da1848e8-b1f1-42d1-93c3-5b0b9c3b24ea)
 - [Live Demo](https://www.loom.com/share/6a3385db4e8747a1913dd85a7834846f?sid=a740fd5b-2aa3-457e-8fb7-86976f59f9b8)

## Features
- 📝 Generate research, outlines, resources and lessons reports
- 🌐 Aggregates over 20 web sources per research to form objective and factual conclusions
- 🖥️ Includes an easy-to-use web interface (HTML/CSS/JS)
- 🔍 Scrapes web sources with javascript support
- 📂 Keeps track and context of visited and used web sources
- 📄 Export research reports to PDF and more...

## Quickstart
> **Step 0** - Install Python 3.11 or later. [See here](https://www.tutorialsteacher.com/python/install-python) for a step-by-step guide.

<br />

> **Step 1** - Download the project

```bash
$ git clone https://github.com/assafelovic/gpt-researcher.git
$ cd gpt-researcher
```

<br />

> **Step 2** - Install dependencies
```bash
$ pip install -r requirements.txt
```
<br />

> **Step 3** - Create .env file with your OpenAI Key or simply export it

```bash
$ export OPENAI_API_KEY={Your API Key here}
```

- **By default, we use OpenAI, but you can use any other LLM model (including open sources)** supported by [Langchain Adapter](https://python.langchain.com/docs/guides/adapters/openai), simply change the llm model and provider in config/config.py. Follow [this guide](https://python.langchain.com/docs/integrations/llms/) to learn how to integrate LLMs with Langchain. 
- **We highly recommend using GPT models for optimal performance.**

<br />

> **Step 4** - Run the agent with FastAPI

```bash
$ uvicorn main:app --reload
```
<br />

> **Step 5** - Go to http://localhost:8000 on any browser and enjoy researching!
 

 

## 🛡 Disclaimer

This project, GPT Researcher, is an experimental application and is provided "as-is" without any warranty, express or implied. We are sharing codes for academic purposes under the MIT license. Nothing herein is academic advice, and NOT a recommendation to use in academic or research papers.

Our view on unbiased research claims:
1. The whole point of our scraping system is to reduce incorrect fact. How? The more sites we scrape the less chances of incorrect data. We are scraping 20 per research, the chances that they are all wrong is extremely low.
2. We do not aim to eliminate biases; we aim to reduce it as much as possible. **We are here as a community to figure out the most effective human/llm interactions.**
3. In research, people also tend towards biases as most have already opinions on the topics they research about. This tool scrapes many opinions and will evenly explain diverse views that a biased person would never have read.

**Please note that the use of the GPT-4 language model can be expensive due to its token usage.** By utilizing this project, you acknowledge that you are responsible for monitoring and managing your own token usage and the associated costs. It is highly recommended to check your OpenAI API usage regularly and set up any necessary limits or alerts to prevent unexpected charges.
es with weasyprint, please visit their website and follow the installation instructions: https://doc.courtbouillon.org/weasyprint/stable/first_steps.html

## Try it with Docker

> **Step 1** - Install Docker

Follow instructions at https://docs.docker.com/engine/install/

> **Step 2** - Create .env file with your OpenAI Key or simply export it

```bash
$ export OPENAI_API_KEY={Your API Key here}
```

> **Step 3** - Run the application

```bash
$ docker-compose up
```

> **Step 4** - Go to http://localhost:8000 on any browser and enjoy researching!


