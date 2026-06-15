# PlainPlan Action — Live Demo

This repo demonstrates the [PlainPlan GitHub Action](https://github.com/adamnmcc/plainplan-action).

On every pull request, the workflow sends the committed `plan.json`
(a `terraform show -json` export) to PlainPlan and posts a plain-English,
risk-flagged review as a PR comment.

The sample plan here intentionally includes risky changes — a database
replacement, an `0.0.0.0/0` security group rule, an S3 bucket deletion, and a
wildcard IAM policy — to show how risk flags appear.

## Usage

```yaml
- name: Analyze with PlainPlan
  uses: adamnmcc/plainplan-action@v1
  with:
    plan_file: plan.json
    api_key: ${{ secrets.PLAINPLAN_API_KEY }}
```

See the open/closed pull requests for example output.

