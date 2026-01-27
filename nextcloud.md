# 📂 PROYECTO INTERMODULAR: Nube Privada Corporativa (Nextcloud)
![alt text](images/nextclud.png)

- [📂 PROYECTO INTERMODULAR: Nube Privada Corporativa (Nextcloud)](#-proyecto-intermodular-nube-privada-corporativa-nextcloud)
  - [1. 📋 Ficha Técnica del Proyecto](#1--ficha-técnica-del-proyecto)
  - [2. 🗓️ Cronograma Detallado (50 Horas)](#2-️-cronograma-detallado-50-horas)
    - [📅 SEMANA 1: Planificación y Diseño (10 horas)](#-semana-1-planificación-y-diseño-10-horas)
    - [📅 SEMANA 2: Ejecución Técnica (20 horas)](#-semana-2-ejecución-técnica-20-horas)
    - [📅 SEMANA 3: Pruebas y Documentación (12 horas)](#-semana-3-pruebas-y-documentación-12-horas)
    - [📅 SEMANA 4: Defensa y Evaluación (8 horas)](#-semana-4-defensa-y-evaluación-8-horas)
  - [3. 📊 Rúbrica de Evaluación del Proyecto](#3--rúbrica-de-evaluación-del-proyecto)
  - [4. 💡 Elementos Diferenciadores (Para nota extra)](#4--elementos-diferenciadores-para-nota-extra)
  - [📅 Información de Entrega y Modalidad](#-información-de-entrega-y-modalidad)

## 1. 📋 Ficha Técnica del Proyecto

| Aspecto | Detalles |
| --- | --- |
| **Título** | Despliegue de Sistema de Almacenamiento y Colaboración en Nube Privada |
| **Duración** | 50 horas |
| **Equipo** | 3 alumnos (Roles: Administrador de Sistemas, Administrador de Red, Soporte/Seguridad) |
| **Módulos integrados** | Sistemas Operativos, Redes Locales, Seguridad Informática |
| **Software principal** | **Nextcloud** (Open Source), Ubuntu Server, Apache/Nginx, MariaDB |
| **Hardware requerido** | 1 Servidor (físico o virtual), 2 equipos cliente (Windows/Linux), switch |
| **Cliente ficticio** | "Estudio de Arquitectura y Diseño" (necesitan compartir archivos grandes de forma segura) |

---

## 2. 🗓️ Cronograma Detallado (50 Horas)

### 📅 SEMANA 1: Planificación y Diseño (10 horas)

**Sesión 1-3: Definición y Roles**

* **Análisis:** El cliente usa métodos inseguros (WeTransfer gratuito, USBs) para mover planos CAD confidenciales.
* **Solución:** Servidor propio con control total de datos y usuarios.
* **Reparto de tareas:**
* *Alumno 1 (SysAdmin):* Prepara el servidor (Ubuntu) y la pila LAMP.
* *Alumno 2 (Redes):* Configura DNS, IP estática y acceso externo (Simulado o real vía No-IP).
* *Alumno 3 (Seguridad):* Diseña la política de usuarios (Arquitectos vs Becarios) y copias de seguridad.



---

### 📅 SEMANA 2: Ejecución Técnica (20 horas)

**Sesión 4-6: Instalación del Núcleo**

* Instalación de dependencias críticas en Linux (`php-gd`, `php-mysql`, `mariadb-server`).
* Despliegue de Nextcloud y conexión con la base de datos.
* **Reto técnico:** Configurar el archivo `php.ini` para permitir subidas de archivos mayores a 2GB (necesario para los planos del "cliente").

**Sesión 7-8: Seguridad y Optimización**

* Activación de **HTTPS** (certificado autofirmado o Let's Encrypt).
* Configuración de la caché de memoria (Redis/APCu) para que la interfaz web sea rápida.

---

### 📅 SEMANA 3: Pruebas y Documentación (12 horas)

**Sesión 9: Batería de Pruebas**

* **Sincronización:** Instalar el cliente de escritorio en Windows y verificar que los archivos se actualizan en tiempo real.
* **Movilidad:** Acceder desde un móvil/tablet a la nube.
* **Compartición:** Crear un enlace público con contraseña y fecha de caducidad (simulando envío a un cliente externo).

**Sesión 10: Entregables**

* **Manual de Usuario:** "Guía rápida para compartir archivos".
* **Memoria Técnica:** Justificación del hardware, capturas de la instalación y configuración de seguridad.

---

### 📅 SEMANA 4: Defensa y Evaluación (8 horas)

**Sesión 11-12: Presentación**

* Demostración en vivo: Un alumno sube una foto desde su móvil y aparece instantáneamente en la pantalla del proyector (PC del profesor).
* Justificación de costes: Comparativa de ahorro frente a licencias de Dropbox/Google Drive Business.

---

## 3. 📊 Rúbrica de Evaluación del Proyecto

Esta rúbrica está diseñada para evaluar tanto el resultado técnico como las competencias transversales.

| Criterio | **10 (Avanzado)** | **7.5 (Intermedio)** | **5 (Básico)** | **0 (Necesita mejorar)** |
| --- | --- | --- | --- | --- |
| **Funcionalidad Técnica** | La nube funciona fluida, con HTTPS activo y permite subir archivos grandes (+2GB). Sincronización PC-Móvil perfecta. | La nube funciona y sincroniza, pero faltan ajustes de rendimiento (lenta) o no tiene HTTPS configurado. | La instalación básica funciona, pero falla la sincronización con clientes o da errores al subir archivos. | La instalación no finaliza o el servidor no es accesible desde la red. |
| **Configuración de Red y Seguridad** | IP fija correcta, usuarios con permisos bien diferenciados (Admin/Usuario) y política de contraseñas robusta. | IP fija configurada. Usuarios creados pero con permisos genéricos o inseguros (todos admin). | Hay conectividad básica (ping), pero la configuración de usuarios es la que viene por defecto. | No hay conectividad entre cliente y servidor. No se han gestionado usuarios. |
| **Documentación** | Memoria profesional con índice, capturas explicadas y manual de usuario personalizado con logo de la empresa ficticia. | Memoria completa con capturas, pero el manual de usuario es confuso o poco práctico. | Documentación escasa, faltan pasos importantes o capturas de pantalla de la configuración. | No se entrega documentación o es una copia directa de internet sin adaptar. |
| **Defensa y Presentación** | Exposición clara, roles definidos, demostración en vivo exitosa y respuesta solvente a preguntas técnicas. | Exposición correcta, pero la demostración en vivo tiene fallos menores o dudas en las preguntas. | Se limitan a leer las diapositivas. La demostración no se realiza o falla completamente. | No hay presentación preparada o no se demuestra conocimiento de lo realizado. |
| **Trabajo en Equipo** | Reparto equitativo de tareas visible. Todos los miembros dominan el proyecto globalmente. | Buena coordinación, pero se nota que un alumno ha cargado con la parte técnica más difícil. | Descoordinación evidente. Algún miembro desconoce partes del proyecto. | Conflictos no resueltos o trabajo individual sin integración. |

---

## 4. 💡 Elementos Diferenciadores (Para nota extra)

Si el equipo quiere asegurar el **10 (Avanzado)**, se sugiere implementar uno de los siguientes extras:

1. **Integración Ofimática:** Instalar *Nextcloud Office* o *Collabora Online* para editar documentos tipo Word/Excel directamente en el navegador.
2. **Backup Externo:** Configurar un script que haga una copia de seguridad automática de la base de datos a un segundo disco duro o unidad USB a una hora programada.

---

## 📅 Información de Entrega y Modalidad

**Formato de entrega:** Los alumnos han de hacer una Exposición, donde han de grabarse a ellos mismos junto con la pantalla de su ordenador donde expongan el trabajo realizado durante el proyecto, máximo 10 minutos, preferiblemente menos.

**Fecha de entrega:** Mayo 29

**Modalidad:** Individual.

Los proyectos se presentarán la segunda semana de febrero y los alumnos pueden empezar a trabajar desde entonces una vez elegido los que van a realizar.

Es posible que los alumnos realicen su propia propuesta de proyecto pero ha de ser aprobada por el profesor antes de comenzar.