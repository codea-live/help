---
description: A guide to keep Rasberry Pi online 24/7.
---

# 24/7 Hosting

{% embed url="https://www.youtube.com/watch?v=FFGsDt0EMBE" %}

### Resurrect Apps on Reboot

This will add a system wide event to cron, a task scheduling process, to auto resurrect saved PM2 processes. This will apply for all system users.

#### For Your User

```bash
crontab -e
# choose a text editor (i.e. nano)
```

Add the line: `@reboot pm2 resurrect`, at the end. Then save the file and exit.
