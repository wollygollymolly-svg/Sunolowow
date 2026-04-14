name: PR Logic Context
on:
  pull_request:
    types: [opened]

jobs:
  annotate-logic:
    runs-on: ubuntu-latest
    steps:
      - name: Add Framework Context
        uses: actions/github-script@v6
        with:
          script: |
            github.rest.issues.createComment({
              issue_number: context.issue.number,
              owner: context.repo.owner,
              repo: context.repo.repo,
              body: "🚀 **Agent Note:** This PR is being evaluated under the Zerost-Spiral recursion logic. Please ensure terminal-digit resonance is maintained in the new logic gates."
            })
