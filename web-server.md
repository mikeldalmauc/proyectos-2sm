
# 📂 PROYECTO INTERMODULAR: Infraestructura Web de Alto Rendimiento (WordPress)

![alt text](images/wp-nginx.png)

- [📂 PROYECTO INTERMODULAR: Infraestructura Web de Alto Rendimiento (WordPress)](#-proyecto-intermodular-infraestructura-web-de-alto-rendimiento-wordpress)
  - [1. 📋 Ficha Técnica del Proyecto](#1--ficha-técnica-del-proyecto)
  - [2. 🗓️ Cronograma Detallado (50 Horas)](#2-️-cronograma-detallado-50-horas)
    - [📅 SEMANA 1: Arquitectura y Pila Tecnológica (10 horas)](#-semana-1-arquitectura-y-pila-tecnológica-10-horas)
    - [📅 SEMANA 2: Instalación y Configuración del Servidor (20 horas)](#-semana-2-instalación-y-configuración-del-servidor-20-horas)
    - [📅 SEMANA 3: Optimización (WPO) y Seguridad (12 horas)](#-semana-3-optimización-wpo-y-seguridad-12-horas)
    - [📅 SEMANA 4: Pruebas de Estrés y Defensa (8 horas)](#-semana-4-pruebas-de-estrés-y-defensa-8-horas)
  - [3. 📊 Rúbrica de Evaluación (Enfoque Rendimiento)](#3--rúbrica-de-evaluación-enfoque-rendimiento)
  - [4. 💡 El "Factor Pro" (Mejoras Diferenciales)](#4--el-factor-pro-mejoras-diferenciales)
    - [¿Por qué este proyecto?](#por-qué-este-proyecto)

## 1. 📋 Ficha Técnica del Proyecto

| Aspecto | Detalles |
| --- | --- |
| **Título** | Despliegue, Securización y Optimización de un Portal Corporativo con CMS |
| **Duración** | 50 horas |
| **Equipo** | 3 alumnos (Roles: SysAdmin/DevOps, Frontend/CMS Specialist, Security Admin) |
| **Módulos integrados** | Servicios de Red e Internet, Aplicaciones Web, Seguridad Informática |
| **Software principal** | **WordPress**, Pila **LEMP** (Linux, **Nginx**, MariaDB, PHP-FPM), Redis (Caché) |
| **Hardware requerido** | 1 Servidor Ubuntu Server, 1 Cliente para pruebas de carga |
| **Cliente ficticio** | "Diario Digital Local" (Requiere tiempos de carga menores a 1 segundo y soportar picos de visitas) |

---

## 2. 🗓️ Cronograma Detallado (50 Horas)

### 📅 SEMANA 1: Arquitectura y Pila Tecnológica (10 horas)

**Sesión 1-3: Diseño de la Solución**

* **Reto:** El cliente se queja de que su web actual "se cae" cuando hay una noticia importante y va muy lenta.
* **Decisión Técnica:** Cambio de Apache a **Nginx** (mejor rendimiento) y uso de **PHP-FPM**.
* **Roles:**
* *SysAdmin (Alumno 1):* Preparación del servidor y configuración de Nginx (Virtual Hosts).
* *CMS Specialist (Alumno 2):* Selección de plantilla ligera (ej. Astra/GeneratePress) y estructura de contenidos.
* *Security (Alumno 3):* Planificación de firewall (UFW) y configuración de Fail2Ban para evitar ataques de fuerza bruta al login.



### 📅 SEMANA 2: Instalación y Configuración del Servidor (20 horas)

**Sesión 4-6: El Servidor Web (LEMP Stack)**

* Instalación manual de **Nginx, MariaDB y PHP 8.x**.
* **Configuración Avanzada:** Ajustar el `php.ini` y el `nginx.conf` para maximizar la memoria disponible y la compresión GZIP/Brotli.
* Creación de la base de datos y usuario seguro.

**Sesión 7-8: Despliegue de WordPress con WP-CLI**

* **OBLIGATORIO:** No usar el instalador web. Usar **WP-CLI** (Línea de comandos de WordPress) para:
* Descargar el core.
* Crear el archivo `wp-config.php`.
* Instalar y activar plugins desde la terminal.
* *¿Por qué?* Demuestra dominio de la consola de administración.



### 📅 SEMANA 3: Optimización (WPO) y Seguridad (12 horas)

**Sesión 9: WPO (Web Performance Optimization) - La Clave del Proyecto**

* **Caché de Servidor:** Instalación y configuración de **Redis** o **Varnish** para cachear consultas a la base de datos.
* **Caché de Aplicación:** Configuración de plugin de caché (ej. WP Rocket o W3 Total Cache) bien ajustado.
* **Prueba de velocidad:** Medición con Google PageSpeed Insights (Objetivo: >90 puntos).

**Sesión 10: Seguridad y Backup**

* **HTTPS:** Certificado SSL gratuito con **Certbot (Let's Encrypt)** configurando la renovación automática.
* **Hardening:** Ocultar versión de WP, cambiar prefijo de tablas DB, deshabilitar edición de archivos desde el dashboard.
* **Backups:** Script automático que exporte la DB y comprima la carpeta `/var/www` enviándola a una ruta externa.

### 📅 SEMANA 4: Pruebas de Estrés y Defensa (8 horas)

**Sesión 11: Pruebas de Carga (Load Testing)**

* Uso de herramientas como **Apache Benchmark (`ab`)** o **Siege** para simular 100 usuarios concurrentes golpeando la web.
* Monitorización en tiempo real con `htop` para ver cómo aguanta la CPU y la RAM.

**Sesión 12: Presentación**

* Defensa del rendimiento: "Antes cargaba en 3s, ahora en 0.8s".
* Demostración de seguridad: Intentar entrar al `/wp-admin` varias veces mal y ver cómo el servidor banea la IP (Fail2Ban).

---

## 3. 📊 Rúbrica de Evaluación (Enfoque Rendimiento)

| Criterio | **10 (Avanzado)** | **7.5 (Intermedio)** | **5 (Básico)** | **0 (Necesita mejorar)** |
| --- | --- | --- | --- | --- |
| **Infraestructura Servidor (LEMP)** | Nginx optimizado con HTTP/2 o HTTP/3. PHP-FPM ajustado. Uso de **Redis/Varnish** operativo. | Servidor Nginx funcionando con PHP y base de datos, pero sin configuración de caché avanzada (Redis). | Instalación básica (quizás usaron Apache por error o XAMPP en lugar de un servidor real). Funciona pero lento. | No funciona el servidor web o error 500 constante. |
| **Gestión WordPress (WP-CLI)** | Instalación y gestión realizada mediante **WP-CLI** (consola). Creación de Tema Hijo (Child Theme) para personalizaciones. | Instalación web estándar. Tema instalado correctamente. Uso de plugins básicos. | Instalación con errores de permisos (pidiendo credenciales FTP para instalar plugins). | WordPress no carga o error de conexión a Base de Datos. |
| **Seguridad y HTTPS** | **SSL (A+)** en Qualys SSL Labs. Protección contra fuerza bruta (Fail2Ban) activa. Permisos de ficheros perfectos (755/644). | HTTPS activo con Let's Encrypt. Algunos ajustes de seguridad básicos aplicados. | Web por HTTP (insegura). Permisos de carpetas peligrosos (777). | Web hackeada durante las pruebas o accesible sin contraseña. |
| **Rendimiento (WPO)** | Tiempo de carga < 1s. Puntuación PageSpeed > 90. Aguanta prueba de estrés de 50 usuarios concurrentes sin caerse. | Tiempo de carga aceptable (< 2s). Aguanta tráfico moderado. | La web va lenta. Se cae inmediatamente al recibir 5 o 10 peticiones seguidas. | La web tarda más de 5 segundos en cargar o da "Time out". |
| **Defensa y Documentación** | Memoria incluye comparativa "Antes vs Después" de optimizar. Defensa técnica de por qué Nginx es mejor que Apache en este caso. | Documentación correcta de los pasos. Defensa estándar mostrando la web. | Documentación escasa, solo pantallazos sin explicación. Defensa pobre. | No se entrega documentación. |

---

## 4. 💡 El "Factor Pro" (Mejoras Diferenciales)

Para obtener la máxima calificación y diferenciar el proyecto de una instalación casera:

1. **Entorno Staging vs Producción:**
* Crear dos Virtual Hosts: `test.midominio.com` (donde se prueban los cambios) y `www.midominio.com` (la web real). Explicar cómo pasan cambios de uno a otro.


2. **CDN (Content Delivery Network):**
* Conectar el servidor a **Cloudflare** (capa gratuita) para gestionar las DNS y la seguridad perimetral. Enseñar en la defensa cómo Cloudflare paró ataques.


3. **Monitorización:**
* Instalar **Netdata** o un dashboard simple en el servidor para ver gráficas bonitas de consumo de RAM/CPU en la memoria técnica.



### ¿Por qué este proyecto?

Este proyecto cubre competencias críticas de SysAdmin (Linux, Nginx, Bash) y de Desarrollador Web (CMS, Optimización, BD). Es perfecto para perfiles híbridos que suelen buscar las empresas de marketing digital y hosting.