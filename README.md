# Superpipe Implementation for AI Model Comparison (OpenAI vs Anthropic)

This repository contains the code for implementing a comparison of AI models GPT-4, Claude 3 Haiku, Claude 3 Sonnet, and Claude 3 Opus using Superpipe. The analysis is designed to extract structured data with a long context and visualize the performance trade-offs.

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

SERPEnrichmentStep: Searches for a person's Wikipedia page using their name.

LLMStructuredStep: Extracts the Wikipedia URL from the search results.

CustomStep: Fetches the contents of the Wikipedia URL and converts them into markdown.

LLMStructuredStep: Extracts structured data such as the date of birth, living status, and cause of death from the Wikipedia content.

## Evaluating the Pipeline

The evaluation dataset consists of known facts about famous individuals, and the evaluation function assesses the pipeline's performance by comparing the extracted data to this dataset.

## Optimization of the Pipeline

The optimization process identifies which steps in the pipeline are bottlenecks in terms of cost and latency and then runs a grid search to find more cost-effective model configurations without 

## Visualization of the Results
After the optimization, the performance of each step in the pipeline, including latency and cost, can be printed out for analysis.

## Reporting and Commentary

The final step is to compile the findings into a blog post that can be found on [superpipe.ai](<https://superpipe.ai>)


## License

This project is licensed under the MIT License - see the LICENSE.md file for details.


## Creating Development Environment
The following was tested and run on an Ubuntu 22.04 VM using Python 3.10.12
```bash
sudo apt install python3-venv
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python3 -m jupyter notebook
```

## Usage

To run the entire pipeline:

```bash
python3 main.py
```