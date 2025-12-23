# Runbook: High CPU Investigation

## Goal
Identify the process causing CPU spikes and decide the next step (restart service, tune config, or escalate).

## Steps
1. View top processes:
   - `top`
   - `ps aux --sort=-%cpu | head`

2. Identify process details:
   - `ps -o user,pid,cmd -p <PID>`

3. Check system load:
   - `uptime`

4. If it’s a service, check status:
   - `systemctl status <service>`

5. Review recent logs:
   - `journalctl -u <service> --since "1 hour ago"`

## Document
- Symptom (what happened)
- Findings (commands + results)
- Fix (what you changed)
- Verification (how you confirmed it’s resolved)
- Prevention (idea to reduce repeat incidents)
