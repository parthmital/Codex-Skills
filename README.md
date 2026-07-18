# Codex Skills

## Table of Contents

1. [Quick Start](#quick-start)
2. [Project Overview](#project-overview)
3. [Problem Statement](#problem-statement)
4. [Project Goals](#project-goals)
5. [Key Features](#key-features)
6. [Supported Use Cases](#supported-use-cases)
7. [System Architecture](#system-architecture)
8. [Application Workflow](#application-workflow)
9. [Technology Stack](#technology-stack)
10. [Repository Structure](#repository-structure)
11. [Prerequisites](#prerequisites)
12. [Local Installation](#local-installation)
13. [Dependency Installation](#dependency-installation)
14. [Environment Configuration](#environment-configuration)
15. [Database Setup](#database-setup)
16. [Running The Project](#running-the-project)
17. [Available Scripts And Commands](#available-scripts-and-commands)
18. [API Documentation](#api-documentation)
19. [Authentication And Authorisation](#authentication-and-authorisation)
20. [Input Validation](#input-validation)
21. [Error Handling](#error-handling)
22. [Logging](#logging)
23. [Testing](#testing)
24. [Code Quality Checks](#code-quality-checks)
25. [Build Process](#build-process)
26. [Production Deployment](#production-deployment)
27. [CI Or CD Process](#ci-or-cd-process)
28. [Repository Metrics](#repository-metrics)
29. [Security Considerations](#security-considerations)
30. [Performance Considerations](#performance-considerations)
31. [Monitoring And Maintenance](#monitoring-and-maintenance)
32. [Troubleshooting](#troubleshooting)
33. [Known Limitations](#known-limitations)
34. [Contribution Guidelines](#contribution-guidelines)
35. [Coding Standards](#coding-standards)
36. [Licence](#licence)
37. [Support And Contact Information](#support-and-contact-information)

## Quick Start

This repository is a collection of Codex skill folders. It is not a web application, API service, Python package, or Node package.

### 1. Confirm that the shell is in the repository root

Run this command from the repository root:

```powershell
Get-ChildItem .prettierrc.json
```

What it does: checks that the shell can see a file that exists at the repository root.

Expected result: later commands can find paths such as `ipynb-guardian/scripts/notebook_doctor.py`.

Common errors:

<table>
  <thead>
    <tr>
      <th>Problem</th>
      <th>Likely cause</th>
      <th>Resolution</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>The file is not found.</td>
      <td>The shell is not in the repository root.</td>
      <td>Change to the folder that contains `.prettierrc.json` and the skill folders.</td>
    </tr>
  </tbody>
</table>

### 2. Install the verified Python dependency for the notebook utility

Run this command from the repository root:

```powershell
python -m pip install nbformat
```

What it does: installs `nbformat`, which is imported by `ipynb-guardian/scripts/notebook_doctor.py`.

Expected result: pip completes successfully and the notebook utility can import `nbformat`.

Common errors:

<table>
  <thead>
    <tr>
      <th>Problem</th>
      <th>Likely cause</th>
      <th>Resolution</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>python is not recognised.</td>
      <td>Python is not installed or is not on PATH.</td>
      <td>Install Python 3 or use the Python launcher available on your machine.</td>
    </tr>
    <tr>
      <td>Missing dependency: install with `python -m pip install nbformat`.</td>
      <td>`nbformat` is not installed in the active Python environment.</td>
      <td>Run the install command again in the same environment used to run the script.</td>
    </tr>
  </tbody>
</table>

### 3. Smoke test the notebook utility

Run this command from the repository root:

```powershell
python ipynb-guardian/scripts/notebook_doctor.py --help
```

What it does: checks that the `notebook_doctor.py` command line interface starts correctly.

Expected result: the command prints usage text and lists these subcommands: `inspect`, `validate`, `repair`, `clean`, `export-code`, and `diff`.

Common errors:

<table>
  <thead>
    <tr>
      <th>Problem</th>
      <th>Likely cause</th>
      <th>Resolution</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>The script path is not found.</td>
      <td>The command was not run from the repository root.</td>
      <td>Change to the repository root and run the command again.</td>
    </tr>
  </tbody>
</table>

## Project Overview

This repository stores reusable Codex skills. A skill is a folder with a `SKILL.md` instruction file. Each skill in this repository also has an `agents/openai.yaml` metadata file that gives a display name, a short description, a default prompt, and implicit invocation policy.

The repository currently contains five skills:

1. `frontend-design`
2. `internet-research`
3. `ipynb-guardian`
4. `readme-generator`
5. `software-architecture`

The `ipynb-guardian` skill is the only skill in this repository that includes an executable helper script.

## Problem Statement

Codex skills need to be stored as clear, reviewable, reusable project files. Without a repository level README, a new developer cannot quickly know:

1. Which skills are available.
2. Which files define skill behaviour.
3. Which commands can be safely run.
4. Which dependencies are required.
5. Which parts of the project are not implemented, such as tests, CI, package manifests, APIs, and deployment files.

## Project Goals

The repository has these verified goals based on the skill descriptions:

1. Provide frontend design guidance through `frontend-design`.
2. Provide internet research workflow guidance through `internet-research`.
3. Provide safe Jupyter notebook inspection and maintenance guidance through `ipynb-guardian`.
4. Provide repository README generation guidance through `readme-generator`.
5. Provide software architecture planning and review guidance through `software-architecture`.

## Key Features

1. Five Codex skill instruction files.
2. Five OpenAI agent metadata files.
3. One notebook maintenance utility script.
4. One notebook precommit reference document.
5. One Prettier configuration file.

## Supported Use Cases

<table>
  <thead>
    <tr>
      <th>Skill</th>
      <th>Supported use case</th>
      <th>Primary files</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>frontend-design</td>
      <td>Guidance for frontend UI, UX, layout, typography, colour, responsive polish, and design systems.</td>
      <td><a href="frontend-design/SKILL.md">frontend-design/SKILL.md</a>, <a href="frontend-design/agents/openai.yaml">frontend-design/agents/openai.yaml</a></td>
    </tr>
    <tr>
      <td>internet-research</td>
      <td>Guidance for current external research, comparable project scouting, source quality checks, and recommendations.</td>
      <td><a href="internet-research/SKILL.md">internet-research/SKILL.md</a>, <a href="internet-research/agents/openai.yaml">internet-research/agents/openai.yaml</a></td>
    </tr>
    <tr>
      <td>ipynb-guardian</td>
      <td>Guidance and tooling for safe Jupyter notebook inspection, validation, repair, cleaning, code export, and semantic diff.</td>
      <td><a href="ipynb-guardian/SKILL.md">ipynb-guardian/SKILL.md</a>, <a href="ipynb-guardian/scripts/notebook_doctor.py">ipynb-guardian/scripts/notebook_doctor.py</a></td>
    </tr>
    <tr>
      <td>readme-generator</td>
      <td>Guidance for generating a verified repository README.</td>
      <td><a href="readme-generator/SKILL.md">readme-generator/SKILL.md</a>, <a href="readme-generator/agents/openai.yaml">readme-generator/agents/openai.yaml</a></td>
    </tr>
    <tr>
      <td>software-architecture</td>
      <td>Guidance for architecture planning, critique, tradeoff analysis, ADRs, migrations, and verification plans.</td>
      <td><a href="software-architecture/SKILL.md">software-architecture/SKILL.md</a>, <a href="software-architecture/agents/openai.yaml">software-architecture/agents/openai.yaml</a></td>
    </tr>
  </tbody>
</table>

## System Architecture

This repository has a file based architecture:

1. Each top level skill folder owns one `SKILL.md` file.
2. Each skill folder owns one `agents/openai.yaml` metadata file.
3. `ipynb-guardian` also owns a `scripts` folder and a `references` folder.
4. There is no shared runtime entry point.
5. There is no API layer, web server, database, queue, cache, or background worker in the current repository.

No Mermaid diagram is included because the repository does not define a runtime system flow, API flow, authentication flow, database relationship, or deployment flow.

## Application Workflow

This repository does not define an application workflow. It defines skill usage workflows.

General skill workflow:

1. A user invokes or implies a skill.
2. Codex reads the matching `SKILL.md`.
3. Codex follows the workflow and rules in that file.
4. If the skill has helper files, Codex uses them only when relevant.

`ipynb-guardian` workflow:

1. Inspect a notebook.
2. Validate notebook structure.
3. Repair structure only when needed.
4. Clean outputs only when the task requires it.
5. Export code or create a semantic diff when needed.
6. Execute the notebook from a fresh kernel when execution is possible and relevant.

## Technology Stack

<table>
  <thead>
    <tr>
      <th>Technology</th>
      <th>Version</th>
      <th>Purpose</th>
      <th>Where used</th>
      <th>Why it is needed</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Markdown</td>
      <td>Not declared</td>
      <td>Stores skill instructions and documentation.</td>
      <td>`SKILL.md`, `README.md`, and `references/precommit.md` files.</td>
      <td>Codex skills are instruction documents.</td>
    </tr>
    <tr>
      <td>YAML</td>
      <td>Not declared</td>
      <td>Stores agent metadata.</td>
      <td>Each `agents/openai.yaml` file.</td>
      <td>The metadata defines display name, short description, default prompt, and implicit invocation policy.</td>
    </tr>
    <tr>
      <td>Python</td>
      <td>Exact version not declared</td>
      <td>Runs the notebook maintenance utility.</td>
      <td>`ipynb-guardian/scripts/notebook_doctor.py`.</td>
      <td>The script inspects, validates, repairs, cleans, exports, and diffs notebooks.</td>
    </tr>
    <tr>
      <td>nbformat</td>
      <td>Exact version not declared</td>
      <td>Reads, writes, converts, normalises, and validates Jupyter notebooks.</td>
      <td>`ipynb-guardian/scripts/notebook_doctor.py`.</td>
      <td>The script depends on `nbformat` instead of editing raw notebook JSON directly.</td>
    </tr>
    <tr>
      <td>Prettier configuration</td>
      <td>Prettier version not declared</td>
      <td>Defines formatting preferences.</td>
      <td>`.prettierrc.json`.</td>
      <td>The repository sets `useTabs` to `true` and `tabWidth` to `2`.</td>
    </tr>
  </tbody>
</table>

## Repository Structure

```text
.
  .prettierrc.json
  README.md
  frontend-design/
    SKILL.md
    agents/
      openai.yaml
  internet-research/
    SKILL.md
    agents/
      openai.yaml
  ipynb-guardian/
    README.md
    SKILL.md
    agents/
      openai.yaml
    references/
      precommit.md
    scripts/
      notebook_doctor.py
  readme-generator/
    SKILL.md
    agents/
      openai.yaml
  software-architecture/
    SKILL.md
    agents/
      openai.yaml
```

Important paths:

1. `.prettierrc.json`: formatter preferences for tabs and tab width.
2. `frontend-design/SKILL.md`: frontend design workflow and design quality rules.
3. `internet-research/SKILL.md`: internet research workflow and source quality rules.
4. `ipynb-guardian/SKILL.md`: notebook safety workflow and completion checklist.
5. `ipynb-guardian/README.md`: short install and smoke test notes for the notebook skill.
6. `ipynb-guardian/references/precommit.md`: optional notebook repository protection notes.
7. `ipynb-guardian/scripts/notebook_doctor.py`: command line notebook maintenance utility.
8. `readme-generator/SKILL.md`: README generation workflow and validation rules.
9. `software-architecture/SKILL.md`: software architecture planning, review, ADR, and validation workflow.
10. `*/agents/openai.yaml`: agent display and invocation metadata for each skill.

## Prerequisites

<table>
  <thead>
    <tr>
      <th>Prerequisite</th>
      <th>Required for</th>
      <th>Version</th>
      <th>Verification</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Codex skills compatible environment</td>
      <td>Using the skill folders as Codex skills.</td>
      <td>Not declared in the repository.</td>
      <td>No command is provided in the repository.</td>
    </tr>
    <tr>
      <td>Python 3</td>
      <td>Running `notebook_doctor.py`.</td>
      <td>Exact version not declared.</td>
      <td>The script has a Python 3 shebang and Python 3 syntax.</td>
    </tr>
    <tr>
      <td>nbformat</td>
      <td>Running `notebook_doctor.py`.</td>
      <td>Exact version not declared.</td>
      <td>The script imports `nbformat` and exits with an install message if it is missing.</td>
    </tr>
  </tbody>
</table>

## Local Installation

There is no repository level installer script.

To use the skill files locally:

1. Keep this repository in a stable folder.
2. Copy the required skill folder into your Codex skills directory when you want to install that skill.
3. Preserve the folder name and the `SKILL.md` file.

The only folder that documents this copy based install process inside the repository is `ipynb-guardian`.

## Dependency Installation

There is no `requirements.txt`, `pyproject.toml`, `package.json`, or lock file in the repository.

The verified required dependency is:

```powershell
python -m pip install nbformat
```

Optional notebook repository protection dependencies are documented in `ipynb-guardian/references/precommit.md`:

```powershell
python -m pip install nbformat nbstripout nbdime
nbdime config-git --enable
nbstripout --install
```

These optional commands were not executed while preparing this README because they modify local Git or user configuration.

## Environment Configuration

No environment variables are read by the current repository files.

<table>
  <thead>
    <tr>
      <th>Variable name</th>
      <th>Required</th>
      <th>Purpose</th>
      <th>Expected format</th>
      <th>Safe example value</th>
      <th>Default value</th>
      <th>Security notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>None found</td>
      <td>No</td>
      <td>Not applicable</td>
      <td>Not applicable</td>
      <td>Not applicable</td>
      <td>Not applicable</td>
      <td>No secret values are required by the repository.</td>
    </tr>
  </tbody>
</table>

## Database Setup

No database files, schemas, migrations, seed files, or database connection code are present.

## Running The Project

There is no long running application to start.

The executable part of the repository is the notebook utility:

```powershell
python ipynb-guardian/scripts/notebook_doctor.py --help
```

Run it from the repository root. The expected result is command usage text.

## Available Scripts And Commands

### notebook_doctor.py

Show help:

```powershell
python ipynb-guardian/scripts/notebook_doctor.py --help
```

Inspect a notebook:

```powershell
python ipynb-guardian/scripts/notebook_doctor.py inspect path/to/notebook.ipynb
```

Validate a notebook:

```powershell
python ipynb-guardian/scripts/notebook_doctor.py validate path/to/notebook.ipynb
```

Repair a notebook and create a backup:

```powershell
python ipynb-guardian/scripts/notebook_doctor.py repair path/to/notebook.ipynb --backup
```

Clean notebook outputs and execution counts while creating a backup:

```powershell
python ipynb-guardian/scripts/notebook_doctor.py clean path/to/notebook.ipynb --backup
```

Clean notebook outputs, execution counts, and widget metadata:

```powershell
python ipynb-guardian/scripts/notebook_doctor.py clean path/to/notebook.ipynb --backup --drop-widgets
```

Export notebook code cells:

```powershell
python ipynb-guardian/scripts/notebook_doctor.py export-code path/to/notebook.ipynb --output path/to/notebook_cells.py
```

Show a semantic notebook diff:

```powershell
python ipynb-guardian/scripts/notebook_doctor.py diff before.ipynb after.ipynb
```

### Documented notebook execution check

`ipynb-guardian/SKILL.md` documents this Jupyter execution command:

```bash
jupyter nbconvert \
  --to notebook \
  --execute notebook.ipynb \
  --output notebook.executed.ipynb \
  --ExecutePreprocessor.timeout=600 \
  --ExecutePreprocessor.kernel_name=python3
```

This command was not executed while preparing this README because the repository does not contain a notebook file.

## API Documentation

No API endpoints are present in the repository. No HTTP routes, request bodies, response bodies, status codes, or API authentication rules can be documented from the current files.

## Authentication And Authorisation

No authentication or authorisation code is present. The skill documents are local instruction files and the notebook utility runs as a local command.

## Input Validation

The repository contains input validation in `ipynb-guardian/scripts/notebook_doctor.py`.

Verified behaviour:

1. `load_notebook` reads notebooks through `nbformat.read`.
2. Invalid JSON exits with an explicit message.
3. `validate_notebook` runs `nbformat.validate`.
4. Duplicate cell IDs are treated as invalid.
5. `repair_notebook` converts notebooks to format version 4 and regenerates missing or duplicate cell IDs.
6. `atomic_write` validates a notebook before replacing the target file.

## Error Handling

The notebook utility handles these errors:

1. Missing `nbformat` dependency.
2. Invalid JSON in a notebook file.
3. Notebook read failure.
4. Notebook validation failure.
5. Duplicate cell IDs.

The script reports failures through console output and process exit codes.

## Logging

No logging framework is present. The notebook utility uses `print` statements and standard error for command line feedback.

## Testing

No test files are present in the repository.

Verified checks run while preparing this README:

```powershell
python ipynb-guardian/scripts/notebook_doctor.py --help
```

This command passed and printed command usage text.

The repository does not contain sample notebooks, so notebook validation, repair, cleaning, export, and diff commands were not run against a real notebook.

## Code Quality Checks

The repository contains `.prettierrc.json` with these settings:

```json
{
	"useTabs": true,
	"tabWidth": 2
}
```

No formatter script, lint script, type check script, or precommit configuration file is present at the repository root.

## Build Process

No build process is present. There is no compiled application, package manifest, bundler configuration, or build script.

## Production Deployment

No production deployment process is present. There is no hosting configuration, Dockerfile, compose file, deployment script, or release workflow.

## CI Or CD Process

No CI or CD workflow is present. There is no `.github` directory or other pipeline configuration in the repository.

## Repository Metrics

<table>
  <thead>
    <tr>
      <th>Metric name</th>
      <th>Verified value</th>
      <th>Source file or command used for verification</th>
      <th>Notes or limitations</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Skill directories</td>
      <td>5</td>
      <td>`Get-ChildItem -Directory`</td>
      <td>Top level skill folders only.</td>
    </tr>
    <tr>
      <td>Skill definition files</td>
      <td>5</td>
      <td>`rg --files`</td>
      <td>Files named `SKILL.md`.</td>
    </tr>
    <tr>
      <td>Agent metadata files</td>
      <td>5</td>
      <td>`rg --files`</td>
      <td>Files named `agents/openai.yaml`.</td>
    </tr>
    <tr>
      <td>Python scripts</td>
      <td>1</td>
      <td>`Get-ChildItem -Recurse -File`</td>
      <td>`ipynb-guardian/scripts/notebook_doctor.py`.</td>
    </tr>
    <tr>
      <td>Notebook utility subcommands</td>
      <td>6</td>
      <td>`python ipynb-guardian/scripts/notebook_doctor.py --help`</td>
      <td>`inspect`, `validate`, `repair`, `clean`, `export-code`, and `diff`.</td>
    </tr>
    <tr>
      <td>Package manifests</td>
      <td>0</td>
      <td>`Get-ChildItem -Recurse -File -Include package.json,pyproject.toml,requirements.txt,setup.py`</td>
      <td>No package manager metadata found.</td>
    </tr>
    <tr>
      <td>API endpoints</td>
      <td>0</td>
      <td>`rg` search for common route and server patterns</td>
      <td>No API server code found.</td>
    </tr>
    <tr>
      <td>Environment variables</td>
      <td>0</td>
      <td>`rg` search for common environment variable access patterns</td>
      <td>No environment reads found.</td>
    </tr>
    <tr>
      <td>Database models</td>
      <td>0</td>
      <td>Repository file inspection</td>
      <td>No database files found.</td>
    </tr>
    <tr>
      <td>Test files</td>
      <td>0</td>
      <td>`Get-ChildItem -Recurse -File -Include '*test*','*.spec.*','*.test.*'`</td>
      <td>No test files found.</td>
    </tr>
    <tr>
      <td>Test coverage percentage</td>
      <td>Not measured in the current repository.</td>
      <td>No coverage tool or report found.</td>
      <td>Coverage cannot be verified.</td>
    </tr>
    <tr>
      <td>Notebook output warning threshold</td>
      <td>5 MiB</td>
      <td>`ipynb-guardian/scripts/notebook_doctor.py`</td>
      <td>The inspect command warns when embedded outputs exceed this size.</td>
    </tr>
    <tr>
      <td>Notebook execution timeout in documented command</td>
      <td>600 seconds</td>
      <td>`ipynb-guardian/SKILL.md`</td>
      <td>Documented for `jupyter nbconvert` execution verification.</td>
    </tr>
    <tr>
      <td>Default ports</td>
      <td>0</td>
      <td>Repository file inspection</td>
      <td>No server or port configuration found.</td>
    </tr>
  </tbody>
</table>

## Security Considerations

1. No real secrets, tokens, passwords, private keys, or connection strings were found during README inspection.
2. No environment variables are required by repository code.
3. Notebook outputs can contain sensitive data. `ipynb-guardian/SKILL.md` instructs users to check for secrets and machine specific paths before finalising notebook work.
4. `notebook_doctor.py` can create backups when `--backup` is passed to `repair` or `clean`.
5. The script does not implement a full secret scanner. Manual review is still required before sharing notebooks.

## Performance Considerations

No runtime performance benchmark is present.

Verified performance related value:

1. `notebook_doctor.py inspect` warns when embedded notebook outputs exceed 5 MiB.

Other values are not measured in the current repository.

## Monitoring And Maintenance

There is no monitoring setup because the repository does not run a service.

Recommended maintenance based on current files:

1. Keep each skill folder self contained.
2. Update the matching `agents/openai.yaml` when a skill name, description, or default prompt changes.
3. Run the notebook utility smoke test after changing `notebook_doctor.py`.
4. Add a dependency manifest if more Python dependencies are introduced.
5. Add tests if `notebook_doctor.py` gains more behaviour.
6. Add the missing `LICENSE.txt` file or remove the licence reference from `frontend-design/SKILL.md`.

## Troubleshooting

<table>
  <thead>
    <tr>
      <th>Problem</th>
      <th>Likely cause</th>
      <th>Diagnostic command</th>
      <th>Resolution</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`python` is not recognised.</td>
      <td>Python is not installed or is not on PATH.</td>
      <td>`python --version`</td>
      <td>Install Python 3 or use the available Python launcher.</td>
    </tr>
    <tr>
      <td>`notebook_doctor.py` reports missing `nbformat`.</td>
      <td>The active Python environment does not have `nbformat` installed.</td>
      <td>`python -m pip show nbformat`</td>
      <td>Run `python -m pip install nbformat`.</td>
    </tr>
    <tr>
      <td>The notebook path is not found.</td>
      <td>The command uses a placeholder path or the shell is in the wrong directory.</td>
      <td>`Get-Location`</td>
      <td>Run the command from the repository root or pass the correct notebook path.</td>
    </tr>
    <tr>
      <td>A notebook is reported as invalid.</td>
      <td>The file has invalid JSON, invalid notebook schema, or duplicate cell IDs.</td>
      <td>`python ipynb-guardian/scripts/notebook_doctor.py validate path/to/notebook.ipynb`</td>
      <td>Inspect the error. If structure repair is appropriate, run `repair` with `--backup`.</td>
    </tr>
    <tr>
      <td>Optional precommit commands are unavailable.</td>
      <td>`nbstripout` or `nbdime` is not installed.</td>
      <td>`python -m pip show nbstripout nbdime`</td>
      <td>Install them with the optional command documented in `ipynb-guardian/references/precommit.md`.</td>
    </tr>
  </tbody>
</table>

## Known Limitations

1. The current folder is not a Git repository.
2. There is no root package manifest.
3. There is no automated test suite.
4. There is no CI or CD setup.
5. There is no deployment configuration.
6. There is no API service or database layer.
7. `frontend-design/SKILL.md` references `LICENSE.txt`, but no `LICENSE.txt` file is present in the repository.
8. `ipynb-guardian` is the only skill with a helper script.
9. The exact supported Python version is not declared.
10. Dependency versions are not pinned.

## Contribution Guidelines

No formal contributing guide is present.

For changes to this repository:

1. Keep each skill in its own folder.
2. Keep the main instruction file named `SKILL.md`.
3. Keep agent metadata in `agents/openai.yaml`.
4. Update this README when adding, renaming, or removing a skill.
5. Add tests before expanding notebook utility behaviour.
6. Do not commit secrets or personal machine paths.

## Coding Standards

Current verified standards:

1. `.prettierrc.json` sets tabs and a tab width of 2.
2. `notebook_doctor.py` uses Python type annotations.
3. Notebook operations should use `nbformat` or `notebook_doctor.py` instead of blind raw JSON edits.
4. Skill instructions should be direct and task specific.

No lint configuration is present.

## Licence

No repository level licence file is present.

`frontend-design/SKILL.md` contains this front matter field:

```yaml
license: Complete terms in LICENSE.txt
```

The referenced `LICENSE.txt` file is not present in the repository, so the licence terms cannot be verified from the current files.

## Support And Contact Information

No support contact, issue tracker, maintainer email, or project URL is present in the repository.
