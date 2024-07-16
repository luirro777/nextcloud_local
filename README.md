# Nextcloud Local

Instala una instancia de Nextcloud en tu servidor local utilizando Ansible.

## Instalación

### 1. Instalar Ansible

Primero, asegúrate de tener Ansible instalado en tu sistema:

```bash
sudo apt install ansible
```

### 2. Clonar este repositorio

Clona el repositorio `nextcloud_local` desde GitHub y navega al directorio:

```bash
git clone https://github.com/luirro777/nextcloud_local
cd nextcloud_local/
```

### 3. Configurar variables

Antes de ejecutar el playbook, configura las siguientes variables según tus necesidades:

#### En `roles/mysql/defaults/main.yml`:
- `db_name`: Nombre de la base de datos MySQL para Nextcloud.
- `db_user`: Usuario de la base de datos MySQL para Nextcloud.
- `db_password`: Contraseña del usuario de la base de datos MySQL.

#### En `roles/nextcloud/defaults/main.yml`:
- `nc_dbname`: Nombre de la base de datos para Nextcloud.
- `nc_dbuser`: Usuario de la base de datos para Nextcloud.
- `nc_dbpassword`: Contraseña del usuario de la base de datos para Nextcloud.

#### En `roles/apache/defaults/main.yml`:
- `servername`: Nombre del servidor, debe coincidir con el FQDN (Nombre de dominio completo) de tu servidor.

#### En `inventory/nextcloud`:
- `ansible_host`: IP del servidor donde se llevará a cabo la instalación.

### 4. Ejecutar el playbook

Una vez configuradas las variables, ejecuta el playbook de Ansible para instalar Nextcloud:

```bash
ansible-playbook -i inventory/nextcloud nextcloud.yml
```

### Contacto

Si tienes alguna pregunta o problema, no dudes en ponerte en contacto conmigo:
- Email: luisromano@gmail.com

