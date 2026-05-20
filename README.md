# OpenLLM Audit

OpenLLM Audit is an early-stage open-source tool for testing local LLM deployments.

It is being built for teams that run models with Ollama, llama.cpp, local HTTP APIs, or small RAG setups. The tool is designed to run on the user's machine, so prompts, logs, test data, and reports stay inside the local environment.

The project is in planning and early development. The first public version will focus on a small, useful workflow for common local setups.

## Planned Scope

- CLI audit runner
- Ollama adapter
- llama.cpp adapter
- local HTTP API adapter
- prompt handling tests
- malformed input tests
- basic RAG abuse tests
- runtime checks for latency, memory use, crashes, and timeouts
- JSON and HTML reports
- practical hardening suggestions

## Why Local First

Many small teams use local LLMs because they work with private documents, internal data, or sensitive client material. A security audit tool for those systems should follow the same privacy model.

Audit runs will work without a cloud service. Updates can be installed through normal open-source releases.

## Repository Status

This repository is a starting point for the project.

Current status:

- project scope defined
- initial module layout created
- roadmap drafted
- implementation is still in early development

## Planned Architecture

```text
openllm-audit/
  src/
    offensive_simulation/    Python audit modules
    memory_monitor/          runtime metrics and local checks
    hardening_generator/     report and recommendation helpers
  README.md
  LICENSE
  SECURITY.md
  CONTRIBUTING.md
  ROADMAP.md
```

## Target Runtimes

| Runtime | Status |
| --- | --- |
| Ollama | planned |
| llama.cpp | planned |
| local HTTP model APIs | planned |
| simple RAG setups | planned |

## Planned Usage

The exact command line interface may change during development.

```bash
openllm-audit scan --target http://localhost:11434 --profile basic
openllm-audit report --input audit.json --format html
```

## Current Development Notes

The first implementation work will focus on a minimal local scan flow:

1. connect to a local Ollama endpoint
2. run a small test profile
3. capture response, latency, timeout, and error state
4. write a JSON report
5. generate a simple HTML summary

## Safety

OpenLLM Audit is intended for authorized testing of local systems owned or controlled by the user. The project will include safe-use guidance and a responsible disclosure process for issues found in related open-source tools.

## License

OpenLLM Audit is released under the GNU Affero General Public License v3.0 or later. See [LICENSE](LICENSE).

## Maintainers

This project is maintained through the public repository.

Please use GitHub issues for questions, bug reports, and project discussion.
