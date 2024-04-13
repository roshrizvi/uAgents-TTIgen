# uAgents: AI Agent Framework

uAgents is a library developed by Fetch.ai that allows for creating autonomous AI agents in Python. With simple and expressive decorators, you can have an agent that performs various tasks on a schedule or takes action on various events.

## 🚀 Features

-🤖 **Paragraph Analysis**: Analyzes a given paragraph using a BERT model to extract key concepts.
-📸 **Image Generation**: Generates an image based on the extracted information using Stable Diffusion v1-5.
-🔗 **AgentVerse.ai Integration**: Leverages AgentVerse.ai's framework for efficient communication and protocol handling.

## 🧶 Prerequisites
-An **AgentVerse.ai** account and project setup with deltaV access.
-API keys for both the **BERT model** (BERT_API_URL and BERT_HEADERS) and the **Stable Diffusion v1-5 model** (STADIF_API_KEY). You can obtain these from Hugging Face (https://huggingface.co/).
-An **Imgur client ID** for image upload (upload_image_to_imgur).


## ⚡ Quickstart

### Installation

Get started with uAgents by installing it for Python 3.9 to 3.12:

    pip install uagents

#### Creating an Agent

Build your first uAgent using the following script:

    from uagents import Agent, Context
    alice = Agent(name="alice", seed="alice recovery phrase")

Include a seed parameter when creating an agent to set fixed addresses, or leave it out to generate random addresses each time.

#### Giving it a task

Give it a simple task, such as greeting:

    @alice.on_interval(period=2.0)
    async def say_hello(ctx: Context):
        ctx.logger.info(f'hello, my name is {ctx.name}')

    if __name__ == "__main__":
        alice.run()

#### Running the Agent

So far, your code should look like this:

    from uagents import Agent, Context

    alice = Agent(name="alice", seed="alice recovery phrase")

    @alice.on_interval(period=2.0)
    async def say_hello(ctx: Context):
        ctx.logger.info(f'hello, my name is {ctx.name}')

    if __name__ == "__main__":
        alice.run()

Run it using:

    python agent.py

You should see the results in your terminal.

## 📖 Documentation

- [👋 Introduction](https://fetch.ai/docs/concepts/agents/agents)
- [💻 Installation](https://fetch.ai/docs/guides/agents/installing-uagent)
- Tutorials
  - [🤖 Create an agent](https://fetch.ai/docs/guides/agents/create-a-uagent)
  - [🛣️ Agent Communication](https://fetch.ai/docs/guides/agents/communicating-with-other-agents)
  - [🍽️ Restaurant Booking Demo](https://fetch.ai/docs/guides/agents/booking-demo)
- Key Concepts:
  - [📍Addresses](https://fetch.ai/docs/guides/agents/getting-uagent-address)
  - [💾 Storage](https://fetch.ai/docs/guides/agents/storage-function)
  - [📝 Interval Tasks](https://fetch.ai/docs/guides/agents/interval-task)
  - [🌐 Agent Broadcast](https://fetch.ai/docs/guides/agents/broadcast)
  - [⚙️ Almanac Contracts](https://fetch.ai/docs/guides/agents/register-in-almanac)

## 🌱 Examples

The [`examples`](https://github.com/fetchai/uAgents/tree/main/python/examples) folder contains several examples of how to create and run various types of agents.

## 🌲 Integrations

The [`integrations`](https://github.com/fetchai/uAgents/tree/main/integrations) folder contains examples that provide a more in depth use of the uAgents library.

## Python Library

Go to the [`python`](https://github.com/fetchai/uAgents/tree/main/python) folder for details on the Python uAgents library.

## ✨ Contributing

All contributions are welcome! Remember, contribution includes not only code, but any help with docs or issues raised by other developers. See our [contribution guidelines](https://github.com/fetchai/uAgents/blob/main/CONTRIBUTING.md) for more details.


## 🛡 Disclaimer

This project, uAgents, is provided "as-is" without any warranty, express or implied. By using this software, you agree to assume all risks associated with its use, including but not limited to unexpected behavior, data loss, or any other issues that may arise. The developers and contributors of this project do not accept any responsibility or liability for any losses, damages, or other consequences that may occur as a result of using this

