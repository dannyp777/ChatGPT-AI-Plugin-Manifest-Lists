# ChatGPT-AI-Plugin-Manifest-Lists #

A collection of links to ChatGPT/AI "*/.well-known/ai-plugin.json", "*/.well-known/openapi.json" and "*/.well-known/openapi.yaml" manifest files and plugin data from the OpenAI API. Here for educational purposes.

| File | Description |
|------|-------------|
| chat.openai.com.api.response_2023-07-24.json | ChatGPT plugin data from OpenAI API |
| list-ai-plugin-json.txt | list of links to */.well-known/ai-plugin.json and */.well-known/openapi.json manifest files |
| list-openapi-yaml.txt | list of links to */.well-known/openapi.yaml manifest files |

[OpenAI ChatGPT Plugin developers guide](https://platform.openai.com/docs/plugins/introduction) :- [https://platform.openai.com/docs/plugins/introduction](https://platform.openai.com/docs/plugins/introduction)

## How to obtain ChatGPT Plugin data from the OpenAI API (as at 24/07/2023) ##
1. Open a new GPT-4 chat session in ChatGPT
2. Open the browsers Web Developer Tools window panel. (under "More Tools" menu in Firefox v115.0.2 on Linux)
3. Click on the Network tab and select 'XHR' from the network tabs
4. Navigate to the ChatGPT plugin store via the plugin drop-down
5. You should see a GET request to chat.openai.com for a json file.
   Click on it.
6. A new sub-panel will open when you can view the HTTP headers, request and response
7. Right click on the GET request row for the request and select Copy Value--> Copy as cURL
8. Paste it into a notepad and change the limit to a large number (I used 1000) and ensure offset=0
9. Copy the cURL request into your shell. (obviously if you don't have cURL you will need to install it) You will want to redirect the output into a json file, otherwise you have ~245kb of data piped straight into your shell stdout.
10. Use 'jq' to reformat the json nicely. (jq . input.json > nice.json)
