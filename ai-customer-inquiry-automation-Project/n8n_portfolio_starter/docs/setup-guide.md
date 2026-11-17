# Setup guide

This is a portfolio sample and requires your own n8n instance and connected services.

1. Create a separate test n8n workspace/workflow. Do not import public files directly into production.
2. Once available, import `workflow/customer-inquiry-workflow.json` using the workflow menu's **Import from File** option.
3. Configure your own Google Sheets trigger and create a spreadsheet with `Timestamp`, `Customer Name`, `Email Address`, `Inquiry Type`, and `Your Message`.
4. Configure Groq access in n8n using a securely stored credential. Never place an API key directly into a workflow field committed to GitHub.
5. Set up a test destination for inquiry records and configure your own database connection.
6. Configure Gmail with a test recipient. Avoid using live distribution lists until validated.
7. Update every node with your test spreadsheet, accounts, database settings, and recipients.
8. Use `sample-data/sample-inquiries.csv` for functional testing. Verify validation, duplicate handling, category, priority, notifications, and no unintended customer sends.
9. Enable any workflow only after reviewing all external actions and associated permissions.

The sanitized export, if added, may have placeholder values and **will not run without your own configuration**. Node names and settings may vary with your n8n version.
