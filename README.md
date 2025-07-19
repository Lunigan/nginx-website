# 🧪 Ansible Nginx Static Site Test

This repository contains a minimal static website used to verify Ansible-based deployments with custom nginx configuration.

## 📂 Structure

- `index.html` — The default landing page served by nginx.  
- `nginx/default` — Customized default configuration for nginx, pointing to `/opt/static-site`.

## 🚀 Purpose

If you're seeing the page that says:

> _"Ansible test – success"_  
> _"This is new default site for nginx on this server"_

...then congratulations — your Ansible playbook and nginx setup worked! 🎉

This setup replaces the system default nginx page and demonstrates:
- Serving a custom HTML page on port 80
- Correct root path (`/opt/static-site`)
- Basic file handling with `try_files`

## ⚙️ Nginx Configuration

The custom `default` config modifies:
- **Document root** from `/var/www/html` → `/opt/static-site`
- **Index page** to serve `index.html`
- **Error fallback** via `try_files $uri $uri/ =404`

## 🧵 Deployment Notes

This site is designed to be deployed via Ansible:
- Copy `index.html` to `/opt/static-site`
- Replace nginx default config with `nginx/default`
- Reload nginx

---

📌 _This project is minimal by design. It's a sandbox for automation success and webserver verification._

