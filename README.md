# gpt-cli
Simple CLI for Chat GPT

## Usage

### Chatting in a text file
Pass in a file with the text you want to generate a response to.
```bash
./gpt file.txt
```
The contents of the file will be the complete prompt for the GPT model. 

```
# file.txt

Hello, how are you?
```

The Chat GPT response will be appended to the file:

```
# file.txt

Hello, how are you?

**GPT Response (model: gpt-4-turbo-preview)**
Hello! I'm here and ready to help you. How can I assist you today?

**User Response**
```

You can continue the conversation by adding your response under `**User Response**` and running the command again with the same file. The GPT response will be appended to the file.

### Scripting with GPT
You can also use the CLI to script with GPT. Pass in the prompt as a string and the response will be printed to the console.
```bash
echo "Hello, how are you?" | ./gpt
# Hello! I'm here and ready to help you. How can I assist you today?
```

Useful for more elaborate scripting use cases or for integrating with other tools.

## Using different models
By default, the CLI uses the `gpt-4-turbo-preview` model. You can specify a different model by passing in the `--model` flag.
```bash
./gpt --model gpt-3.5-turbo file.txt
```
You can also list the available models by running the CLI with the `--list-models` flag.
```bash
./gpt --list
# babbage-002
# dall-e-2
# dall-e-3
# davinci-002
# gpt-3.5-turbo
# gpt-3.5-turbo-0125
# ...
```

## Installation
- Clone the repository
- Make sure [jq](https://jqlang.github.io/jq/download/) is installed in your environment.
- Have an active OpenAI API key set to the `OPENAI_API_KEY` environment variable. 
Thats it!

**TIP:** Add an alias to your `.bashrc` or `.zshrc` for easy access.
```bash
alias gpt="/path/to/gpt-cli/gpt"
```
Now you can run the CLI from anywhere in your terminal.

