<<<<<<< HEAD
# mcp-agent-lab (version C) 
=======
# mcp-agent-lab (version D)
>>>>>>> efdded0 (docs: title D)

Building an MCP-based LLM agent with evals, then deploying it to Kubernetes with CI and monitoring. (Work in progress.)

## Goal

I'm building an MCP server that an LLM agent can call as tools, and an eval set that checks whether the agent answers correctly. The aim is to learn production applied-AI engineering end to end: build it, measure it, deploy it, and monitor it. The repo uses sample or public data only.

## Roadmap

- [ ] **MCP server + evals** (Nov): an MCP server with tools an agent can call, plus a 20-question eval set.
- [ ] **Kubernetes deploy + CI + monitoring** (Dec): one-command Helm deploy, CI that runs the evals on every PR, and a monitoring dashboard.
- [ ] **Specialisation track** (Jan): inference optimisation or manufacturing ML.

## Quick start

Requires Python 3.12 and [uv](https://docs.astral.sh/uv/).

```bash
uv sync         # create the environment from uv.lock
uv run pytest   # run the tests
```