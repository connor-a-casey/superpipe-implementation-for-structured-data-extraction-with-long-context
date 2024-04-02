# Superpipe Implementation for AI Model Comparison (OpenAI vs Anthropic)
This repository provides code for comparing AI models using `Superpipe`, designed to extract structured data from long contexts and visualize performance trade-offs 

The following models were tested:
- `GPT-4`
- `Claude 3 Haiku`
- `Claude 3 Sonnet`
- `Claude 3 Opus`

## Overview
The analysis is structured into several steps, each corresponding to a section of the code:

- Building the Pipeline
- Evaluating the Pipeline
- Optimization of the Pipeline
- Visualization of the Results
- Reporting and Commentary

Each section is designed to be modular and easily understandable.

##  Building the Pipeline
The pipeline is constructed using various superpipe steps to search, parse, fetch, and extract data from Wikipedia for a list of notable individuals.

1. SERPEnrichmentStep: Searches for a person's Wikipedia page using their name.

1. LLMStructuredStep: Extracts the Wikipedia URL from the search results.

1. CustomStep: Fetches the contents of the Wikipedia URL and converts them into markdown.

1. LLMStructuredStep: Extracts structured data such as the date of birth, living status, and cause of death from the Wikipedia content.

## Evaluating the Pipeline
The evaluation dataset consists of known facts about famous individuals, and the evaluation function assesses the pipeline's performance by comparing the extracted data to this dataset.

## Optimization of the Pipeline
The optimization process identifies which steps in the pipeline are bottlenecks in terms of cost and latency and then runs a grid search to find more cost-effective model configurations without 

## Visualization of the Results
After the optimization, the performance of each step in the pipeline, including latency and cost, can be printed out for analysis.

## Reporting and Commentary
The final step is to compile the findings into a blog post that can be found on [superpipe.ai](<https://superpipe.ai>)

## Creating Development Environment & Running Notebook
The following was tested and run on an Ubuntu 22.04 VM using Python 3.10.12
```bash
git clone git@github.com:connor-casey-ai/Superpipe-Implementation-for-AI-Model-Comparison-OpenAI-vs-Anthropic-.git
cd Superpipe-Implementation-for-AI-Model-Comparison-OpenAI-vs-Anthropic-/
sudo apt install python3-venv
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python3 -m jupyter notebook
```

## License

This project is licensed under the MIT License - see the `LICENSE.md` file for details.
