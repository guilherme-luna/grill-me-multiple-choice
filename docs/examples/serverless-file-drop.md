# Example: planning a serverless file drop

This is an illustrative session, not a recorded transcript. It shows the format: numbered questions, three options with the recommended one first, and an "Other" field. The answers were picked to show how the rounds build on each other.

Prompt:

```
/grill-me a serverless file drop on AWS: a user requests an upload link, uploads a file to a private bucket and gets a download link that expires
```

## Round 1

```
Q1 - How should users prove who they are before getting an upload link?
  (a) API key per user (Recommended) - simple, easy to revoke, enough for a first version
  (b) Amazon Cognito - full sign-up and login, more setup
  (c) No login, rate limit only - fastest, but anyone can fill the bucket
  (d) Other: ____________

Q2 - How should the infrastructure be defined?
  (a) Terraform (Recommended) - one tool for the whole stack, deploy and destroy in one command
  (b) AWS SAM - shorter for Lambda, less general
  (c) Console only - quick, but nothing to review or repeat
  (d) Other: ____________

Q3 - Where do the expiry times live?
  (a) DynamoDB with a TTL (Recommended) - records expire on their own
  (b) Only in the S3 pre-signed URL - fewer parts, no list of files
  (c) Both
  (d) Other: ____________
```

Answers: a, a, a.

## Round 2

```
Q4 - Which API entry point?
  (a) API Gateway with throttling (Recommended) - rate limits built in
  (b) Lambda function URL with IAM auth - fewer parts, less control over limits
  (c) Application Load Balancer - overkill for this size
  (d) Other: ____________

Q5 - How are the controls proven to work?
  (a) Negative tests (Recommended) - scripts showing a role cannot read another prefix, plain HTTP is refused, an expired link fails
  (b) IAM Access Analyzer only - good, but does not test behavior
  (c) Manual checks
  (d) Other: ____________
```

Answers: a, a.

The session ends when no open decision is left, and nothing is built until you confirm the shared understanding.
