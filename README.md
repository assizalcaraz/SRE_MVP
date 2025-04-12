# MVP de Validación Biométrica y Gestión de Infraestructura en AWS

## 📌 Descripción General

Este proyecto es un MVP (Minimum Viable Product) desarrollado por José Assiz Alcaraz Baxter para demostrar competencias en infraestructura moderna, despliegue en la nube, buenas prácticas de seguridad, monitoreo y resiliencia.

La aplicación central simula un sistema de **validación de identidad biométrica para entornos educativos**, con un backend en Flask/Django, cifrado de datos, y un flujo completo de validación mediante QR y reconocimiento facial. El entorno está diseñado para producción, utilizando contenedores y recursos en AWS.

---

## ⚙️ Arquitectura del Proyecto

### Componentes Principales

- **App principal**: Backend Python (Flask o Django) con endpoints para validación.
- **Base de datos**: SQLite (modo demo) o PostgreSQL (para producción).
- **Dashboard de métricas**: Prometheus + Grafana (en contenedor separado).
- **Dashboard Kanban opcional**: Interfaz web estilo Trello para simular organización de tareas.
- **Logs**: Python Logging + CloudWatch o logs expuestos vía endpoint.
- **Despliegue**: Docker + AWS ECS/Fargate o Elastic Beanstalk.

### Diagrama de Arquitectura (a completar)
> Incluye red, contenedores, servicios, volúmenes y roles de IAM.

---

## 🔐 Seguridad

- Uso de variables de entorno (.env) para manejo seguro de credenciales.
- Tokens JWT para autenticación con expiración.
- Configuración de HTTPS (SSL) usando ACM o self-signed certs.
- Roles IAM mínimos necesarios y grupos de seguridad restrictivos en AWS.

---

## 📊 Observabilidad

- Endpoint `/metrics` expone datos para Prometheus.
- Grafana expone métricas en dashboard preconfigurado.
- Logs almacenados por contenedor o integrados con CloudWatch.
- Simulación de errores y métricas de validación (fallos, tiempo de respuesta).

---

## 🧪 Escenarios de Resiliencia

- Tolerancia a errores: Manejo de reintentos, validación de clave y rostro.
- Caídas simuladas de base de datos o servicios.
- Simulación de concurrencia y validaciones simultáneas.

---

## 🛠️ Instrucciones de Uso

### Requisitos
- Docker
- AWS CLI + IAM user configurado
- Cuenta en AWS con acceso a ECS o Elastic Beanstalk

### Despliegue local

```bash
git clone https://github.com/usuario/proyecto-mvp-biometrico
cd proyecto-mvp-biometrico
cp .env.example .env
docker-compose up --build
```

### Despliegue en AWS (Elastic Beanstalk)

```bash
eb init -p docker nombre-aplicacion
eb create entorno-produccion
eb open
```

---

## 📂 Organización del Proyecto

- `app/` - Aplicación principal (validación biométrica)
- `dashboard/` - Contenedor de dashboard Prometheus + Grafana
- `kanban/` - Contenedor opcional con app estilo Trello
- `scripts/` - Scripts de salud, métricas o deploy
- `infra/` - Configuración de ECS, Dockerfiles, tareas

---

## 📌 Objetivos del Proyecto

- Demostrar conocimiento de AWS, Docker y despliegue CI/CD.
- Mostrar implementación de seguridad y monitoreo.
- Integrar un caso de uso realista: validación biométrica.
- Simular entorno productivo con herramientas modernas.

---

## ✍️ Autor

**José Assiz Alcaraz Baxter**  
Director de Sonido | Desarrollador IT autodidacta | SRE Jr.  
[LinkedIn](https://www.linkedin.com/in/assizalcaraz) | [GitHub](https://github.com/assizalcaraz)
