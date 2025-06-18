# Práctica e02_practica

Este proyecto Ansible automatiza la configuración básica de un servidor Ubuntu, incluyendo:

- Instalación y configuración de **Nginx** con una landing page personalizada.
- Creación de un **usuario devops** con acceso sudo sin contraseña.
- Configuración de **reglas básicas de firewall** (UFW).

## Requisitos

- Ansible instalado en la máquina de control.
- Acceso SSH a los servidores destino.
- Variables definidas en `../inventories/dev/group_vars/vars.yml`:
  - `landing_url`: URL del template HTML a descargar (archivo ZIP).
  - `landing_path`: Ruta donde se desplegará la landing page.
- Archivo de configuración de Nginx en `../files/nginx.conf`.

## Tareas principales

1. **Instala Nginx, UFW y utilidades**  
   Asegura que los paquetes necesarios estén presentes y actualizados.

2. **Crea el usuario devops**  
   Con acceso a bash, grupo sudo y permisos de sudo sin contraseña.

3. **Despliega la landing page**  
   Descarga y descomprime el template HTML, y lo copia al directorio configurado.

4. **Configura Nginx**  
   Aplica la configuración personalizada y habilita el sitio.

5. **Configura el firewall UFW**  
   Permite conexiones SSH, HTTP y HTTPS, y habilita UFW con política por defecto de denegar.

## Ejecución

Desde la carpeta raiz:

```bash
ansible-playbook playbooks/main.yml
```

## Autor

- Este proyecto fue creado por **Oscar Diaz**