# pi4
Pi 4
Thanks! Based on your updated requirements:

* Move `"api_key":"123456789fjkflad"` to the **HTTP header**.
* Set crontab to run **every 30 minutes**.
* Use `POST` to `https://edu.myomyintkyaw.com/pi4`.
* Send payload: `{"name":"aung", "id":1}` as the body (`data`).

---

### ✅ Final Shell Script: `/home/youruser/send_payload.sh`

```bash
#!/bin/bash

curl -X POST https://edu.myomyintkyaw.com/pi4 \
  -H "Content-Type: application/json" \
  -H "api_key: 123456789fjkflad" \
  -d '{"name":"aung", "id":1}'
```

Make it executable:

```bash
chmod +x /home/youruser/send_payload.sh
```

---

### ✅ Crontab Entry (Every 30 Minutes)

Edit crontab:

```bash
crontab -e
```

Add:

```cron
*/30 * * * * /home/youruser/send_payload.sh
```

---

### ✅ (Optional) Log Output

If you want to log the response or errors:

```cron
*/30 * * * * /home/youruser/send_payload.sh >> /home/youruser/pi4_cron.log 2>&1
```

Let me know if you want to add dynamic values, error handling, or environment variables.
