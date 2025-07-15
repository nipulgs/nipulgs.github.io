# Increase DSpace Upload Limit (DSpace 6.3)

This guide explains how to increase the file upload limit for DSpace 6.3.

---

## ✅ 1. Increase the limit in `dspace.cfg`

**File:** `[dspace]/config/dspace.cfg`

**Default:**

```properties
upload.max = 2097152
```

This is in bytes (2 MB).

**Change for 1 GB:**

```properties
upload.max = 1073741824
```

Save the file.

---

## ✅ 2. Increase Tomcat’s HTTP POST limit

**File:** `[tomcat]/conf/server.xml`

Find the `<Connector>` tag for your HTTP port (e.g., 8080).

**Set unlimited POST size:**

```xml
<Connector port="8080" protocol="HTTP/1.1"
           connectionTimeout="20000"
           redirectPort="8443"
           maxPostSize="0" />
```

`0` means unlimited. Or set a byte value, e.g., `maxPostSize="1073741824"` for 1 GB.

---

## ✅ 3. Check PostgreSQL `max_allowed_packet`

PostgreSQL does not have the `max_allowed_packet` like MySQL. Large bitstreams are stored on the file system, not directly in the database. Ensure there are no other database constraints blocking large object storage.

---

## ✅ 4. Restart Tomcat

After changes, restart Tomcat:

```bash
sudo systemctl restart tomcat7
```

(Use `tomcat8` or `tomcat9` if applicable.)

---

## ✅ 5. Optional: Adjust Nginx/Apache (if used as reverse proxy)

### For **Nginx**:

```nginx
server {
    ...
    client_max_body_size 2G;
    ...
}
```

### For **Apache**:

```apache
<Directory "/path/to/dspace">
    LimitRequestBody 2147483648
</Directory>
```

---

## ✅ 6. Test it

* Clear your browser cache.
* Upload a larger file through the DSpace submission form.
* If errors occur, check:

  * Tomcat logs: `[tomcat]/logs/catalina.out`
  * DSpace logs: `[dspace]/log/dspace.log`
  * Browser console for POST size errors.

---

## ✔️ Summary

| Where?              | What to change?                              |
| ------------------- | -------------------------------------------- |
| `dspace.cfg`        | `upload.max` to desired bytes                |
| Tomcat `server.xml` | `<Connector maxPostSize="0">`                |
| Nginx/Apache        | `client_max_body_size` or `LimitRequestBody` |
| Restart services    | Tomcat (and proxy if used)                   |
