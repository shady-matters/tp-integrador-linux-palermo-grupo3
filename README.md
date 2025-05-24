# Trabajo Práctico Integrador - Computación aplicada

## Universidad de Palermo - 2025

### Oferta 2 : Grupo 3

---

## 👥 Integrantes del grupo

- [Capdevila, Luis] - Legajo: [XXXX]
- [Fernandez, Pablo Andres] - Legajo: [XXXX]
- [García Lastra, Manuel] - Legajo: [0145977]
- [Sánchez, Juan Cruz] - Legajo: [XXXX]
- [Nombre Apellido] - Legajo: [XXXX]

---

## 📄 Descripción del trabajo

Este trabajo práctico integrador fue desarrollado en una **máquina virtual Debian GNU/Linux**, provista por la cátedra, cumpliendo con los siguientes objetivos:

- Configuración inicial del entorno y sistema.
- Instalación y configuración de servicios:
  - Servidor **SSH** con autenticación por clave.
  - Servidor **Apache2 con PHP** para servir un sitio web.
  - Base de datos **MariaDB** con carga de datos desde script.
- Configuración de red con IP estática.
- Agregado de un segundo disco y creación de particiones montadas automáticamente.
- Desarrollo de un script de **backup automatizado** configurable.
- Subida de backups y archivos de sistema al repositorio.
- Representación topológica de la infraestructura armada.

---

## 📁 Estructura del repositorio

El repositorio contiene los siguientes archivos comprimidos, generados desde la máquina virtual:

- `root.tar.gz`: backup del directorio `/root`
- `etc.tar.gz`: configuración general del sistema
- `opt.tar.gz`: contiene el script de backup (`/opt/scripts/backup_full.sh`)
- `proc.tar.gz`: snapshot del directorio `/proc`, incluyendo el archivo `particion`
- `www_dir.tar.gz`: archivos del sitio web (index.php y logo.png)
- `backup_dir.tar.gz`: backups generados por el script
- `var_part_aa`, `var_part_ab`, ...: partes comprimidas del directorio `/var`

También se incluye:

- `diagrama_topologia.png`: diagrama de red y estructura de la solución.
- `documentación del proyecto` : Pueden ver el documento completo en Google Docs [aquí](https://docs.google.com/document/d/1JQeTcPudIeyIX1Fp81pObQUNsGaugl5bdzlhhdsRcV0).

---

## 🔧 Cómo probar el entorno

> ⚠️ Esta sección puede completarse si quieren agregar instrucciones para probar la VM o acceder a los servicios.

Ejemplo:

- Usuario: `root`
- Clave: `palermo`
- IP estática asignada: `192.168.X.X`
- Puerto SSH: `22`
- URL del sitio: `http://192.168.X.X`

---

## 🗂️ Estructura de discos montados

- `/www_dir`: montado automáticamente desde partición secundaria (3 GB)
- `/backup_dir`: destino de backups (6 GB)
- Ambos puntos de montaje se configuran vía `/etc/fstab`

---

## 🕒 Automatización de tareas

- Script `backup_full.sh` ubicado en `/opt/scripts`
- Corre automáticamente vía `cron`:
  - Todos los días a las 00:00: backup de `/var/log`
  - Lunes, miércoles y viernes a las 23:00: backup de `/www_dir`

---

## 📌 Observaciones

- Las pruebas de conectividad fueron realizadas desde otra máquina en la misma red.
- El acceso SSH funciona solo con clave privada provista por la cátedra.
- Los servicios corren al inicio del sistema correctamente.

---

## 📷 Diagrama de topología

Ver archivo `diagrama_topologia.png` para más detalles sobre la estructura lógica y física de la implementación.

---

