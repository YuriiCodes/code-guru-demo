## Amazon CodeGuru Reviewer JavaScript Detector Samples

Amazon CodeGuru Reviewer is an AWS service that leverages program analysis and machine learning to surface hard-to-find defects and suggest improvements in your code.

CodeGuru Reviewer supports Java, Python, and JavaScript. To learn how to configure and run it, see the [Amazon CodeGuru Reviewer User Guide](https://docs.aws.amazon.com/codeguru/latest/reviewer-ug/welcome.html).

This repository showcases a selection of JavaScript detectors available in CodeGuru Reviewer. For detailed descriptions of each detector, visit the [Detector Library](https://docs.aws.amazon.com/codeguru/detector-library/index.html). You can also explore parallel examples in [Java](https://github.com/aws-samples/amazon-codeguru-reviewer-java-detectors) and [Python](https://github.com/aws-samples/amazon-codeguru-reviewer-python-detectors).

> **Important:** All code here is intentionally vulnerable—this repo exists purely for educational purposes. Do **not** use these examples in production.

---

## Running the CodeGuru Reviewer GitHub Action on This Repo

You can test CodeGuru Reviewer against this repository using your AWS credentials.

### 1. Prerequisites

Before you scan a fork of this repo, you’ll need:

- An IAM Role with permissions to call CodeGuru Reviewer
- An S3 bucket for storing review artifacts
- The corresponding IAM policy

You can automate this setup by following the steps in the [CDK sample project](https://github.com/aws-samples/aws-codeguru-reviewer-cicd-cdk-sample#cdk-typescript-project-to-set-up-the-codeguru-reviewer-cicd-integration).

### 2. Configuration

A workflow template already exists at `.github/workflows/analyze.yml`. To get started:

1. Fork this repository.
2. Open `.github/workflows/analyze.yml` and fill in:
    - `role-to-assume`: your IAM Role ARN
    - `aws-region`: the AWS Region
    - `s3_bucket`: your S3 bucket name
3. Go to the **Actions** tab in GitHub.
4. Select the **CodeGuru Reviewer** workflow.
5. Click **Run workflow**.
6. After ~5–10 minutes, view findings under the **Security** tab (available on public repos).

---

## Integrating the GitHub Action into Your Own Repository

To scan your own code, copy the `analyze.yml` workflow you configured above into any repo. Even without GitHub Advanced Security, you can:

- Review findings in the AWS Console.
- Use tools like `jq` in your workflow to post-process or filter results.
- Print specific findings to stdout to see them in your workflow logs.

---

## Getting Help

- Report bugs or suggest features via GitHub issues.
- Open a support case with [AWS Support](https://docs.aws.amazon.com/awssupport/latest/user/getting-started.html).
- Read our [CONTRIBUTING](https://github.com/aws-samples/amazon-codeguru-reviewer-python-detectors/blob/main/CONTRIBUTING.md) guide for contribution details.

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md#security-issue-notifications) for information on reporting security issues and submitting improvements.

---

## License

This project is licensed under the Apache 2.0 License. See [LICENSE](LICENSE) for full details.
