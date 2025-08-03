# network-banner-grabbing-project

## Overview
This mini lab explores the use of banner-grabbing techniques to identify software and service information from running network services. By analyzing service responses, this lab illustrates the types of metadata attackers can obtain and the risks of exposing such information.

---

## 1. Apache Web Server (Port 80)

### Command Used
```bash
wget --server-response http://127.0.0.1
```

### Findings
- Banner: `Server: Apache/2.4.52 (Ubuntu)`
- Tool: `wget`
- This confirms that Apache 2.4.52 is running on Ubuntu.

### Risk
Exposing Apache version numbers can lead to exploitation if the version is outdated or has known vulnerabilities.

---

## 2. MySQL Server (Port 3306)

### Command Used
```bash
telnet 127.0.0.1 3306
```

### Findings
- Banner: `8.0.41-0ubuntu0.22.04`
- Tool: `telnet`
- Confirms that MySQL 8.0.41 is active on the default port.

### Risk
Revealing the MySQL version may aid attackers in identifying known exploits, especially if patching is not up to date.

---

## 3. Django Application (Port 8000)

### Command Used
```bash
wget --server-response http://127.0.0.1:8000/admin/login/?next=/admin/
```

### Findings
- Banner: `WSGIServer/0.2 CPython/3.10.12`
- Tool: `wget`
- Indicates that the Django app is running on a WSGI server with Python 3.10.12.

### Risk
Disclosing backend server and runtime info (e.g., WSGI version and Python version) can lead to targeted exploitation.

---

## Key Takeaways
- Banner grabbing is a simple but powerful reconnaissance technique.
- Exposed software versions can significantly increase an organization’s attack surface.
- Masking server banners or using reverse proxies/firewalls can mitigate these risks.

---

## Author
**Lucy Njuguna**  
Cybersecurity Research | Penetration Testing | Web Application Security
