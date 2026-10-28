# When Tools Get in the Way: research workflow repository

Companion to [arXiv:2609.14157](https://arxiv.org/abs/2609.14157). This repository preserves all four supplied Paper 2 notebooks: an earlier currency pilot and three full domain workflows. The paper reports ten domains and six models; this supplied subset does not itself reconstruct every published run or scope-aware intervention.

## Contents

| Notebook | Role |
|---|---|
| Copy_of_workflowreadonly (1) | Thirty-trial currency pilot |
| paper2_geography_FULL_(2) | Fifty place-data/basic-geography query pairs |
| paper2_biology_FULL_(2) | Fifty species-data/basic-biology query pairs |
| paper2_astronomy_FULL_(3) | Fifty astronomical-data/basic-astronomy query pairs |

## Four-condition mechanism

| Condition | Query | Tool | History |
|---|---|---|---|
| C1 | Tool-required | Available | Fresh utility control |
| C2 | Closed-domain | Absent | Fresh baseline |
| C3 | Identical closed-domain | Available | Fresh availability treatment |
| C4 | Identical closed-domain | Available | Prior tool-domain interaction in the same chat |

Each FULL notebook defines paired questions, fixed reference answers, a scoped lookup function, independent chat branches, an actual-invocation flag and a binary reference-aware correctness judge. The C2-C3 comparison measures availability; C3-C4 measures prior-interaction effects. Answer rate and invocation rate remain separate.

## Known research-snapshot caveats

- C4 sends a preceding tool-domain question but the supplied runner does not force that priming question to call a tool. Verify actual preceding call and success before classifying a row as successfully primed. The invocation flag is reset before the closed-domain question so it measures the second query.
- Domain tools return the paired tool-query record through CURRENT_TOOL_PROMPT; they are scoped experimental utilities, not unrestricted lookup services.
- The three FULL notebooks each configure one historical model. Final six-model/ten-domain results and mitigation totals require their corresponding run archive and code.
- Biology contains later judging timeout/resume patches. Choose the intended implementation rather than executing every replacement cell blindly.
- Existing spreadsheet destinations and authentication/output metadata have been removed. Sheet export is optional reporting, not part of the experimental treatment.

## Credentials and public preparation

All notebook outputs, execution counts and cell/notebook metadata were cleared. Four embedded service-account dictionaries in the Paper 2 source were replaced with environment loading. Credential identity diagnostics were removed. Colab secret reads for the service account now load the `GCP_SA_JSON` environment variable. Original spreadsheet identifiers are replaced with `RESEARCH_SHEET_URL`; automatic sheet publishing defaults to false. Literal cloud project settings use `GCP_PROJECT_ID`. Do not commit real values, credential JSON or generated raw datasets.

Set `GCP_SA_JSON` to the complete service-account JSON string through your runtime's private environment configuration, and `GCP_PROJECT_ID` when a notebook requests it. Do not put these values into notebook cells. The original notebooks use mounted Google Drive and historical Vertex AI model identifiers; they are Colab-oriented and require the corresponding external run/configuration files. Endpoints, permissions and SDK behavior must be checked before a paid run.

## Setup and run

Use a fresh Colab Python runtime, privately configure the environment, then install dependencies:

```bash
python -m pip install -r requirements.txt
```

Open the chosen notebook in Colab or Jupyter and review its configuration and local/Drive file dependencies before running its cells in the documented order. These notebooks contain successive setup/result-cell revisions; they are research records rather than a single unattended execution script. No end-to-end run or model call was performed during repository preparation. Do not use Execute All until you have resolved replacement cells, supplied the intended frozen inputs and confirmed output paths.

For an optional local notebook editor:

```bash
python -m pip install jupyterlab
python -m jupyter lab
```

The notebooks' Google Drive and `google.colab` calls require adaptation outside hosted Colab. Model generation can incur charges; no generation was performed here. Spreadsheet write cells must remain disabled unless intentionally configured.

## Provenance and integrity

`provenance.json` records original and sanitized file SHA-256 hashes and cell-specific sanitization changes. Original notebook filenames are preserved. No benchmark questions, payload rules, rubric logic, model settings, statistical procedures or research-control logic were intentionally changed. Credentials, identifying export configuration and execution metadata were the only preparation changes. `security-scan.json` records a static scan with zero detected key literals/provider tokens, zero retained notebook outputs and no syntax findings in parseable non-magic cells. This is not a runtime or scientific replication result.

No license has been inferred from local possession. Confirm collaborator agreement and applicable rights before adding a redistribution license. Paper findings should be attributed to the collaborative paper rather than solely to this repository owner.


## Browse source

[Every published file](FILE-INDEX.md) · [Snapshot hashes](publication-manifest.json)
