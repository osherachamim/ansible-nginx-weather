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
## 🛠️ Role Creation (Built from Scratch)

This project was built from scratch using the Ansible Galaxy role generator:

```bash
ansible-galaxy init roles/nginx_weather
```
The `nginx_weather` role was then fully customized to:

- ✅ Install and configure **NGINX** on **CentOS** machines
- 🔐 Securely load a **Vault-encrypted API key**
- 🌐 Deploy a **weather page** using a **Jinja2 HTML template**
- 🔁 Include **handlers** for service restart logic

## ⚙️ How to Set Up and Run

1. **Clone the Repository**
   ```bash
   git clone https://github.com/osherachamim/ansible-nginx-weather.git
   cd ansible-nginx-weather/
   ```
2.  **Encrypt Your API Key**
   ```
   ansible-vault create roles/nginx_weather/vars/secrets.yml
   ```
   **Inside, add:**
   ```
   weather_api_key: "your_real_openweathermap_api_key"
   ```
3. **Update Your Inventory**
   ```
   [labs]
    your-server-ip ansible_user=your-ssh-user
   ```

4. **Deploy the Weather App**
   ```
   ansible-playbook deploy_weather.yml --ask-become-pass
    ```
## 🔒 Security

- API keys are encrypted using Ansible Vault.
- No sensitive information is exposed in the project or GitHub.

## 🌍 Access the Weather Web App

After successful deployment, open:
```
http://your-server-ip/
```

You will see live weather information for the selected city.

## ✅ Example Ansible Output

Below is an example output of a successful deployment:

![Ansible Deployment Output](ansible-output.png)

## 📚 Technologies Used

- Ansible
- NGINX
- OpenWeatherMap API
- Ansible Vault
- CentOS (target servers)

## 🎯 Skills Demonstrated

- Infrastructure automation with Ansible
- Secure secret management with Vault
- NGINX server setup and configuration
- Modular Ansible role design
- Real-world DevOps practices

## 🤝 License

This project is licensed under the MIT License.
