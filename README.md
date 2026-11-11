# PentAGI Post-Training Agent

CSC 5870 - Special Advanced Topics in Artificial Intelligence  
Team: PentAGI

## Project Goal

Our project investigates whether PentAGI can collect structured agent trajectories that can later be used to post-train a stronger penetration-testing model.

The intended system operates only on authorized Capture-the-Flag and lab targets. We focus on improving model decision-making: selecting useful next actions, interpreting tool outputs, recovering from failed attempts, and producing evidence-supported reports.

## Current Prototype

The current prototype uses PentAGI as an agent framework rather than building a full multi-agent orchestration system from scratch.

### Implemented

- PentAGI environment configured in a Docker-based Kali Linux environment.
- Connection to an LLM hosted on Cal Poly infrastructure.
- Authorized Hack The Box CTF connectivity through OpenVPN.
- Agent workflow can receive a target and goal, invoke available tools, and store chat and terminal activity.
- PentAGI logs provide a record of agent instructions, tool calls, tool outputs, and intermediate decisions.
- Initial exploratory run performed on the authorized Hack The Box “Meow” CTF challenge.

### Current Vertical Slice

**Input:** An authorized CTF target IP address and the objective to find the flag.

**Processing:** PentAGI sends the task to the model, the agent selects actions and tools through the Kali Linux environment, and PentAGI records observations and terminal output.

**Output:** A saved agent trajectory consisting of chat logs, tool calls, terminal output, and task progress.

## Technologies

- PentAGI agent framework
- Docker and Kali Linux container
- Windows host with WSL
- Huihui-Qwen3.8-27B-abliterated base model
- Cal Poly-hosted LLM infrastructure
- OpenVPN for authorized Hack The Box CTF access
- Planned post-training method: QLoRA

## Repository Structure

```text
.
├── README.md
