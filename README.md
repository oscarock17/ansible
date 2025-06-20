
# Carpeta de Ansible

Esta carpeta de Ansible está diseñada para proporcionar una guía paso a paso y ejemplos prácticos sobre el uso y la implementación de Ansible en la configuración y gestión de infraestructuras de TI. Desde conceptos básicos hasta patrones de diseño avanzados, este repositorio contiene una variedad de recursos que cubren diversas áreas de la automatización de infraestructura.

## Estructura de carpetas

- [01-primer-playbook](./01-primer-playbook): Ejemplo básico de un playbook sencillo para comenzar.
- [02-ejemplo-estructura/](./02-ejemplo-estructura/): Esqueleto de una estructura para un proyecto.
- [03-inventarios-estaticos](./03-inventarios-estaticos/): Utilización de inventarios estáticos para diferentes entornos.
- [Practica](./practica/): Ejercicios de practica sobre ansible

## Requisitos

- Ansible >= versión 2.16.5
- Linux/macOS

## Comandos útiles en Ansible

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

## Autor

- Este proyecto fue creado por **Oscar Diaz**.

## Contacto

Para cualquier pregunta o comentario, no dudes en ponerte en contacto conmigo en [GitHub](https://github.com/oscarock17)
