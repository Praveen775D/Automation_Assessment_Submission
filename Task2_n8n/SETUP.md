# n8n setup checklist

1. Import `Task2_Workflow_Udugundla_Praveen.json` into n8n.
2. Create an n8n **Slack API** credential and select it on `Send Digest to Slack` and `Send Fallback Alert to Slack`.
3. Change `#morning-brief` to a channel where the connected Slack app is allowed to post.
4. Execute the workflow manually once to verify the API calls and Slack delivery.
5. Capture the required screenshots after the successful execution.
