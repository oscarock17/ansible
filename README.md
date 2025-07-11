
# 📄 Carpeta de Ansible

Esta carpeta de Ansible está diseñada para proporcionar una guía paso a paso y ejemplos prácticos sobre el uso y la implementación de Ansible en la configuración y gestión de infraestructuras de TI. Desde conceptos básicos hasta patrones de diseño avanzados, este repositorio contiene una variedad de recursos que cubren diversas áreas de la automatización de infraestructura.

## 📂 Ejercicios disponibles

| Nº | Archivo | Descripción |
|----|---------|-------------|
| 01 | [01-primer-playbook](./01-primer-playbook/) | Ejemplo básico de un playbook sencillo para comenzar. |
| 02 | [02-ejemplo-estructura](./02-ejemplo-estructura/) | Esqueleto de una estructura para un proyecto. |
| 03 | [03-inventarios-estaticos](./03-inventarios-estaticos/) | Utilización de inventarios estáticos para diferentes entornos. |
| 04 | [04-inventarios-dinamicos](./04-inventarios-dinamicos/) | Implementación de inventarios dinámicos y configuración asociada. |
| 05 | [05-roles](./05-roles/) | Modularización de la configuración mediante roles de Ansible. |
| 06 | [06-encryptacion-variables](./06-encryptacion-variables/) | Menejo para la encriptacion de variables. |
| 07 | [07-ejemplo-inventario-estatico](./07-ejemplo-inventario-estatico/): | Implementación de un inventario estatico usando las IPs publicas de las instancias en AWS sobre un archivo host. |
| 08 | [08-ejemplo-inventario-dinamico](./08-ejemplo-inventario-dinamico/): | Implementación de un inventario dinamico usando las IPs publicas de las instancias en AWS. |
| 09 | [09-ejemplo-inventario-dinamico-ssm](./09-ejemplo-inventario-dinamico-ssm/): | Implementación de un inventario dinamico usando AWS con instancias privadas usando SSM |
| 10 | [10-ejercicio-config-ubuntu](./10-ejercicio-config-ubuntu/): | Ejercicio automatizacion ubuntu con instalacion de nginx y creacion de usuarios etc.. |
| 11 | [11-ejercicio-config-puertos-usuarios](./11-ejercicio-config-puertos-usuarios/): |Ejercicio automatizacion ubuntu con instalacion de nginx con una landing page, usuarios y puertos. |

## 📌 Requisitos

- Ansible >= versión 2.16.5
- Linux/macOS

## 💻 Comandos útiles en Ansible

### Ejecutar un playbook

```bash
ansible-playbook -i <ruta_inventario> <ruta_playbook.yml>
# Ejemplo
ansible-playbook -i inventories/dev/hosts playbooks/main.yml
```

### Ver los inventarios

```bash
ansible-inventory -i <ruta_inventario> --list
ansible-inventory -i <ruta_inventario> --graph
# Ejemplo
ansible-inventory -i inventories/dev/hosts --list
ansible-inventory -i <ruta_inventario> --graph
```

### Test de conexión (ping)

```bash
ansible all -i <ruta_inventario> -m ping
# Ejemplo
ansible all -i inventories/dev/hosts -m ping
```

### Ejecutar un comando ad-hoc

```bash
ansible all -i <ruta_inventario> -m command -a "<comando>"
# Ejemplo
ansible all -i inventories/dev/hosts -m command -a "uptime"
```

### Ver versión de Ansible

```bash
ansible --version
```

### Ver los hosts de un grupo específico

```bash
ansible <grupo> -i <ruta_inventario> --list-hosts
# Ejemplo
ansible vagrant_vm -i inventories/dev/hosts --list-hosts
```

### Comprobar sintaxis de un playbook

```bash
ansible-playbook --syntax-check <ruta_playbook.yml>
# Ejemplo
ansible-playbook --syntax-check playbooks/main.yml
```

### Encryptar variables

```bash
ansible-vault encrypt <archivo_vars.yml>
# Ejemplo
ansible-vault encrypt secret_vars.yml
```
### Ejecutar playbook con variables encryptadas

```bash
ansible-playbook <ruta_playbook.yml> --ask-vault-pass
# Ejemplo
ansible-playbook playbooks/main.yml --ask-vault-pass
```

### Ejecutar playbook con variables encryptadas

```bash
ansible-playbook <ruta_playbook.yml> --vault-password-file <password_file>
# Ejemplo
ansible-playbook playbooks/main.yml --vault-password-file vault_pass.txt
```

## 👊 Autor

- Este proyecto fue creado por **Oscar Diaz**.

## Contacto

Para cualquier pregunta o comentario, no dudes en ponerte en contacto conmigo en [GitHub](https://github.com/oscarock17)
