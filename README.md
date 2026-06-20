# Practice: Adding Observability

⌨️ In this practice task, you'll enable LangSmith tracing for the PR Review Agent, run the agent on all five sample PRs, and use the traces to fill in an observability table.


## **👩‍💻 Workflow at a glance**

1. Set up your environment
2. Install and configure tracing
3. Verify one trace
4. Run all five PRs
5. Fill in the observability table
6. Answer the diagnostic question
7. Check your work
8. Submit

## 1. Set up your environment

Check that the repo `your-mobile-agent-observability` appears in your account.

## 2. Install and configure tracing

Set up LangSmith tracing as covered in the tool walkthrough, using `"LANGSMITH_PROJECT": "pr-review-agent"` as the project name.

## 3. Verify one trace

Run `/review-pr 1` with `LANGSMITH_METADATA` set to `{"pr_number": "1"}`. Confirm a trace appears in LangSmith before continuing.

## 4. Run all five PRs

Before each run, update `LANGSMITH_METADATA` with the PR number:

```json
"LANGSMITH_METADATA": "{\"pr_number\": \"2\"}"
```

Run `/review-pr 1` through `/review-pr 5`. Answer `no` when the agent asks to post.

## 5. Fill in the `docs/observability-table.md`

Open each trace and read the data. Fill in the table. 

| Input | Total tokens | Most expensive span | `security-reviewer` called? |
| --- | --- | --- | --- |
| PR-01 (clean) |  |  |  |
| PR-02 (style violations) |  |  |  |
| PR-03 (hardcoded API key) |  |  |  |
| PR-04 (architecture violation) |  |  |  |
| PR-05 (mixed issues) |  |  |  |

## 6. Diagnostic question

Open the trace for PR-03 (the hardcoded API key input). 

Answer:

1. Was the `security-reviewer` subagent called? (Y/N)
2. What did the `security-reviewer` return? (paste the span output)
3. If the security finding is missing from the final output — based on the trace, which failure mode was it? Choose from: subagent not called / wrong input / tool never fired / subagent ran but prompt insufficient.

Add your answer to `docs/observability-table.md`.

## 7. Check your work

- [ ]  The observability table is complete for all five PRs
- [ ]  The diagnostic question for PR-03 is answered in four bullets
- [ ]  `docs/observability-table.md` is saved in the repo

## 8. Submit your task

1. Commit your changes.
2. Push to GitHub.
3. Return to the lesson and click "Submit."
