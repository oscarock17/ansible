# Proyecto Ansible - 02-práctica-001

Este proyecto Ansible automatiza la configuración básica de un servidor Ubuntu que incluye:

- Instalación y configuración de **Nginx** con una página personalizada.
- Creación de un **usuario con acceso por clave SSH**.
- Configuración de **reglas básicas de firewall** (UFW).

## Requisitos

- Ansible instalado en tu máquina de control.
- Acceso SSH a los servidores destino.
- Inventario y variables definidas en `../inventories/dev/group_vars/vars.yml`.
- Archivo de clave pública SSH en `../files/id_rsa.pub`.
- Plantilla HTML en `../templates/pagina.html.j2`.

## Tareas que realiza el playbook

1. **Instala Nginx y UFW**  
  Asegura que los paquetes necesarios estén presentes y actualizados.

2. **Inicia y habilita Nginx**  
  Garantiza que el servicio Nginx esté corriendo y habilitado al arranque.

3. **Crea un usuario SSH**  
  Crea un usuario definido en la variable `usuario_ssh` con acceso a bash y directorio home.

4. **Configura la clave SSH**  
  Añade la clave pública especificada al usuario creado para acceso seguro.

5. **Despliega una página personalizada**  
  Usa una plantilla Jinja2 para crear una página HTML personalizada en la ruta definida por `pagina_html`.

6. **Configura el firewall UFW**  
  Permite conexiones SSH y HTTP, y habilita UFW con política por defecto de denegar.

## Autor

- Este proyecto fue creado por **Oscar Diaz**.