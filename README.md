<a href="https://livekit.io/">
  <img src="./.github/assets/livekit-mark.png" alt="LiveKit logo" width="100" height="100">
</a>

# Python Voice Agent

<p>
  <a href="https://cloud.livekit.io/projects/p_/sandbox"><strong>Deploy a sandbox app</strong></a>
  •
  <a href="https://docs.livekit.io/agents/overview/">LiveKit Agents Docs</a>
  •
  <a href="https://livekit.io/cloud">LiveKit Cloud</a>
  •
  <a href="https://blog.livekit.io/">Blog</a>
</p>

A basic example of a voice agent using LiveKit and Python.

## Dev Setup

Clone the repository and install dependencies to a virtual environment:

```console
# Linux/macOS
cd voice-pipeline-agent-python
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python3 agent.py download-files
```

<details>
  <summary>Windows instructions (click to expand)</summary>
  
```cmd
:: Windows (CMD/PowerShell)
cd voice-pipeline-agent-python
python3 -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```
</details>


Set up the environment by copying `.env.example` to `.env.local` and filling in the required values:

- `LIVEKIT_URL`
- `LIVEKIT_API_KEY`
- `LIVEKIT_API_SECRET`
- `OPENAI_API_KEY`
- `CARTESIA_API_KEY`
- `DEEPGRAM_API_KEY`

You can also do this automatically using the LiveKit CLI:

```console
lk app env
```

Run the agent:

```console
python3 agent.py dev
```

This agent requires a frontend application to communicate with. You can use one of our example frontends in [livekit-examples](https://github.com/livekit-examples/), create your own following one of our [client quickstarts](https://docs.livekit.io/realtime/quickstarts/), or test instantly against one of our hosted [Sandbox](https://cloud.livekit.io/projects/p_/sandbox) frontends.

## Documentation

This project is a basic example of a voice agent using LiveKit and Python. The purpose of this project is to demonstrate how to create a voice agent that can interact with users through voice commands and responses.

### Environment Variables

The following environment variables are required for the project to run:

- `LIVEKIT_URL`: The URL of your LiveKit server.
- `LIVEKIT_API_KEY`: Your LiveKit API key.
- `LIVEKIT_API_SECRET`: Your LiveKit API secret.
- `OPENAI_API_KEY`: Your OpenAI API key.
- `CARTESIA_API_KEY`: Your Cartesia API key.
- `DEEPGRAM_API_KEY`: Your Deepgram API key.

These variables should be set in a `.env.local` file in the root directory of the project. You can use the `.env.example` file as a template.

### Usage

To run the agent, use the following command:

```console
python3 agent.py dev
```

When the agent is running, it will connect to the specified LiveKit server and wait for a participant to join. Once a participant joins, the agent will start interacting with the participant through voice commands and responses. The agent uses Deepgram for speech-to-text (STT), OpenAI for language model (LLM), and Cartesia for text-to-speech (TTS). The agent also includes features like voice activity detection (VAD), turn detection, and noise cancellation.
