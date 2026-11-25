# WellnessCairn — proposed AWS architecture

WellnessCairn uses AWS to review catalogues securely, draft respectful improvements with guardrails, and track progress for every retailer.

## Request flow

1. Catalogue API
2. API Gateway
3. Amazon S3
4. AWS Lambda
5. Bedrock
6. Team approval
7. DynamoDB

## Services

### Amazon Bedrock

**Role:** Analyse clarity and draft improvements

Assesses description clarity, drafts factual alternative text and plain-language rewrites, with Bedrock Guardrails keeping every suggestion non-explicit and free of medical claims.

### Amazon API Gateway

**Role:** Connect retailer catalogues

Provides authenticated APIs for retailers and agencies to submit catalogues for review and retrieve approved changes.

### Amazon S3

**Role:** Store catalogue snapshots

Keeps catalogue exports and product images encrypted, so each review can be compared with the next.

### AWS Lambda

**Role:** Run accessibility checks

Runs rule-based structure, readability and completeness checks, orchestrates Bedrock analysis and calculates page scores.

### Amazon DynamoDB

**Role:** Track issues and approvals

Stores issues, suggestions, review decisions and score history for progress tracking.

## Principles

- **Authorised access only** — We review only catalogues we are permitted to access.
- **Respectful language** — Guardrails keep suggestions factual and non-explicit.
- **Measured progress** — Scores are re-checked after every change.

## Safeguards

- **Your team approves** — Every suggested change is reviewed before it is published.
- **Non-explicit by design** — Suggestions are factual and respectful, enforced by guardrails and review.
- **Supports formal audits** — Automated review complements, but does not replace, expert accessibility audits.
- **No shopper data** — We review product content only — never customer information.

## MVP scope

We review an authorised catalogue export, score every product page, draft improvements for the highest-impact issues and deliver an accessibility report your team works through with us.

- Authorised catalogue import
- Clarity and alt-text review
- Readability and structure checks
- Suggested improvements
- Accessibility progress report
