# On-Call Playbook

Quick reference for common incidents. Keep this updated as we learn.

## Initial Response

1. **Acknowledge** the alert in PagerDuty.
2. **Assess** severity and impact.
3. **Communicate** in #incident channel with a short summary.
4. **Investigate** using the runbooks below.

## Common Runbooks

### High CPU / Load

- Check `top` and `uptime` on affected host.
- Look for recent deploys or cron jobs.
- Collect `vmstat 1 5` and `pidstat` for context.

### API Latency Spikes

- Check APM dashboard for slow endpoints.
- Review recent changes to services or database.
- Verify connection pool metrics and slow query logs.

### Disk Full

- Run `df -h` and `du -x -h / | sort -h | tail -20`.
- Clean temp files if safe; otherwise rotate logs.
- Alert the team if this is a recurring issue.

## Handoff Notes

- Always leave a brief handoff in the incident thread.
- Include what was tried, current status, and next steps.
- Update this file with any new findings.
