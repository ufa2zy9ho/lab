# Incident Response Notes

Quick reference for on-call incidents.

## First 5 minutes

- Acknowledge the alert and assess severity.
- Check dashboards and recent deploys.
- Communicate status in the incident channel.

## Common commands

```bash
# Recent logs for a service
journalctl -u <service> --since "10 min ago"

# Open connections
ess -an | grep :<port>

# Disk usage
df -h
```

## Handoff checklist

- Summarise timeline and actions taken.
- Note open questions and next steps.
- Update the postmortem doc if needed.
