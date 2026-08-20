# NASA-Solar-Collector
Collect Solar Flare Using NASA API, n8n, Hermes Agent, Ollama

## Features

- Workflow for n8n to collect solar flare data from NASA DONKI API
- Collect solar flare data from NASA DONKI API
- Filter solar flare data based on class type
- Build Backend for Solar Flare Data with Go

## Current Architecture

![img](simple_architecture.png)

## Future
```mermaid
graph TD
    A[n8n: Collect NASA API data every 24h] --> B[n8n: Internal rule check]
    B -->|Value within normal range| C[Save data only - End, no Hermes call]
    B -->|Anomaly detected| D[Trigger Hermes via Webhook]
    D --> E[Hermes + LLM]
    E --> F[Interpret & assess: why the anomaly occurred, how severe it is]
    F --> G[Report to Slack / Discord]
```
## NASA Open API

[NASA Open API](https://api.nasa.gov/)
 
Go to the link above and register for the API Key.

Of Course this is free to use.

## Usage

Run the workflow to collect solar flare data
