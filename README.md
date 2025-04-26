# ansible-nginx-weather
Ansible automation project to deploy an NGINX web server hosting a weather app. It fetches real-time data from OpenWeatherMap using a Vault-encrypted API key. Includes roles, templates, handlers, and best practices for secure and modular infrastructure setup

# 🌦️ Ansible NGINX Weather App Deployment

This project automates the deployment of an NGINX web server that hosts a real-time weather web app.  
It uses Ansible roles, templates, handlers, and secure variable management with Ansible Vault.

## 📌 Project Features

- Installs and configures NGINX automatically.
- Deploys a weather web page using a dynamic HTML template.
- Fetches live weather data from OpenWeatherMap API.
- Protects API keys using Ansible Vault encryption.
- Follows Ansible best practices: roles, variables, handlers.

## 📁 Project Structure

``` ansible-nginx-weather/
├── ansible.cfg
├── deploy_weather.yml
├── inventory.txt
├── ping_test.yml
├── README.md         <-- Add instructions
└── roles/
    └── nginx_weather/
        ├── defaults/
        ├── handlers/
        ├── tasks/
        ├── templates/
        ├── vars/
        └── meta/
```
## ⚙️ How to Set Up and Run

1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-username/ansible-nginx-weather.git
   cd ansible-nginx-weather/
   ```
   **Encrypt Your API Key**
   ```
   ansible-vault create roles/nginx_weather/vars/secrets.yml
```
