Code-B — n8n Lead Capture Automation
An example n8n workflow for collecting incoming leads via a POST webhook, mapping lead fields, saving them to an n8n Data Table, and flagging leads whose service field contains AI Automation.
Workflow
Lead Capture Trigger → Prepare Lead Data → Save Lead to Database → Qualify Lead → Prepare Priority Alert (matching leads only)
A separate Code B - Lead Database node is included for initial table creation and is not connected to the main execution path.
Fields
name, email, phone, service, message.
Setup
1. Import codeb-lead-capture-public.json into n8n.
2. Create an n8n Data Table with the five fields above, or configure the included standalone table-creation node.
3. In Save Lead to Database, select your own table; the exported table ID is deliberately replaced with a placeholder.
4. Configure the webhook and test with a sample POST payload.
5. Review data retention and access controls before collecting real personal information.
Example test payload:
{"name":"Example User","email":"example@example.com","phone":"0000000000","service":"AI Automation","message":"Interested in an automation demo"}
Scope and limitations
- Priority-alert text is prepared but not delivered via email, Slack, or another service.
- No Google Sheets integration or duplicate detection is implemented in this version.
- No input validation or spam protection is implemented.
- This is a portfolio demonstration, not a production-ready lead intake service.
Security
The public workflow copy excludes original workflow/instance identifiers and uses a placeholder for the internal Data Table reference. No real lead records or API credentials are included.
