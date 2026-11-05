# Sensors and dashboard

The integration exposes these sensors when Anthropic reports their data:

- Session usage (%) and reset time
- Seven-day usage (%) and reset time, across all models
- Seven-day Sonnet usage (%) and reset time
- Extra-usage enabled status, utilization (%), consumed credits and monthly limit

It also creates a sensor for each entry in the API's `limits[]` array, such as
session and weekly model-specific buckets. Each sensor reports utilization as
its state and carries `resets_at`, `severity`, `is_active`, `kind`, `model` and
`surface` attributes. New buckets create new sensors without an integration
update; missing buckets become unavailable while retaining their history. A
model rename creates a new sensor because the API exposes no stable model ID.

## Dashboard

A sample dashboard lives in [`dashboards/claude_usage.yaml`](../dashboards/claude_usage.yaml).
In Home Assistant, create a dashboard under **Settings → Dashboards**, open
its **Raw configuration editor**, paste the YAML and save. You can instead
copy individual cards into an existing dashboard.

## Polling and rate limits

Set the update interval through the integration's options. The default is
300 seconds, with a range of 60–3600 seconds. Anthropic's usage API may rate
limit frequent requests, potentially affecting usage displays in other Claude
clients as well; keep polling conservative.
