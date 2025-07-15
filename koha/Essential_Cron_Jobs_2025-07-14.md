# 📚 Essential Koha Cron Jobs

**For:** Koha ILS Production Server  
**Maintainer:** LRC IIT Indore  
**Generated:** 2025-07-14

---

## 📅 **Daily & Frequent Tasks**

Below are the minimum recommended cron jobs for a healthy Koha instance.

---

### **1️⃣ Clear Plack & Cache**
```cron
50 1 * * * /usr/local/bin/koha-clear-cache.sh >> /var/log/koha/koha-clear-cache.log 2>&1
```

### **2️⃣ Rebuild Zebra Index**
```cron
*/10 * * * * /usr/bin/koha-rebuild-zebra -v -f -z iitindore >> /var/log/koha/rebuild-zebra.log 2>&1
```

### **3️⃣ Process Overdue Notices**
```cron
30 2 * * * /usr/share/koha/bin/cronjobs/overdue_notices.pl -v --library iitindore >> /var/log/koha/overdue_notices.log 2>&1
```

### **4️⃣ Send Advance Notices**
```cron
0 8 * * * /usr/share/koha/bin/cronjobs/advance_notices.pl -v >> /var/log/koha/advance_notices.log 2>&1
```

### **5️⃣ Process Message Queue**
```cron
*/15 * * * * /usr/share/koha/bin/cronjobs/process_message_queue.pl -v >> /var/log/koha/message_queue.log 2>&1
```

### **6️⃣ Automatic Renewals**
```cron
15 1 * * * /usr/share/koha/bin/cronjobs/automatic_renewals.pl -v >> /var/log/koha/auto_renewal.log 2>&1
```

### **7️⃣ Clean Database**
```cron
20 2 * * * /usr/share/koha/bin/cronjobs/cleanup_database.pl \
  --sessions --zebraqueue --email_delivery_attempts --tempuploads --days 30 --confirm \
  >> /var/log/koha/cleanup.log 2>&1
```

### **8️⃣ Generate OPAC Sitemap**
```cron
0 1 * * * /usr/share/koha/bin/cronjobs/sitemap.pl \
  --base-url "https://koha.iiti.ac.in" \
  >> /var/log/koha/sitemap.log 2>&1
```

### **✅ Good Practices**

Run cron as the koha system user or via sudo.

Test each script manually.

Check cron logs with ```tail -f /var/log/syslog```
