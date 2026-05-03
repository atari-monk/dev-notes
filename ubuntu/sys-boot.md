## System Boot & Resume Diagnostics

### Contents

* [Overview](#overview)
* [Check System Boot Time](#check-system-boot-time)
* [Check Resume Events (Sleep/Wake)](#check-resume-events)
* [Combined Usage Notes](#combined-usage-notes)
  * [Important Note](#important-note)

---

### Overview

This note contains useful Linux commands for checking system boot time and investigating resume (sleep/wake) events using system logs.

[Contents](#contents)

---

### Check System Boot Time

Use this command to see when the system last booted:

```bash
uptime -s
```

**What it shows:**

* The exact timestamp of the last system boot
* Useful for verifying reboots or system uptime tracking

Example output:

```
2026-05-03 08:14:22
```

[Contents](#contents)

---

### Check Resume Events (Sleep/Wake) <a id="check-resume-events"></a>

Use this command to filter system logs for resume-related events:

```bash
journalctl --since today | grep -i "resume"
```

**What it shows:**

* Entries related to system resume from sleep/hibernate
* Helps diagnose wake-up behavior or power state transitions

You may also want to expand search for related events:

```bash
journalctl --since today | grep -Ei "resume|suspend|wake"
```

[Contents](#contents)

---

### Combined Usage Notes

* `uptime -s` tells you **when the system started running**
* `journalctl` helps you understand **what happened during the session**
* Together, they help diagnose:

  * unexpected reboots
  * sleep/wake issues
  * system stability problems

<a id="important-note"></a>
**Important Note:** If resume events are missing, it may indicate that:

* the system was fully shut down instead of suspended
* logs were rotated or cleared
* power events were not recorded by the kernel

[Contents](#contents)
