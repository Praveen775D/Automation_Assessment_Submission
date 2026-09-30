# Bonus — Uptime Monitor

Runs every 5 minutes, retries the HTTP check up to 3 times, evaluates the response status, and sends a Slack alert when the status is anything other than HTTP 200.

The Slack token is stored in n8n Credentials. Before enabling the workflow, verify that `https://demo.realworld.show` is the exact URL used for Task 1; if you choose a different Task 1 app, change the URL to that app.
