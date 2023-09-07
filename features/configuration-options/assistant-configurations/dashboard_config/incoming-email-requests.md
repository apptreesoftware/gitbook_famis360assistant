# Incoming Email Requests

For customers wanting to manage incoming emails via the assistant, review, and submit to FAMIS360 to create a new work request, the following additional configurations are needed.

```typescript
  openEmailsEnabled?: boolean;
  openEmailsWidgetText?: EmailWidgetText;
  processedEmailsEnabled?: boolean;
  processedEmailsWithinDays?: number;
  processedEmailsRefreshInterval?: number;
  processedEmailsWidgetText?: EmailWidgetText;
  allowedEmailProfileIds?: number[];
```
