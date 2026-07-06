# Documentación Técnica

## Arquitectura del Sistema

El proyecto Sportmatch sigue una arquitectura Cliente-Servidor separada en dos repositorios principales.

### Frontend
- **Framework:** React 18+ (SPA - Single Page Application).
- **Bundler:** Vite.
- **Estilos:** Vanilla CSS / TailwindCSS.
- **Mapas:** `react-leaflet` interactuando con la API gratuita de OpenStreetMap.
- **Rutas:** Consumo de la API gratuita **OSRM (OpenStreetMap Routing Machine)** para calcular trazados de conducción y distancias Haversine para distancias en línea recta.

### Backend
- **Framework:** Spring Boot (Java).
- **Base de Datos:** PostgreSQL.
- **Seguridad y Gestión de Identidad:** **Keycloak** como proveedor de identidad (IAM) para la gestión de usuarios, roles (`USER` y `ADMIN`) y emisión de tokens JWT.

### Infraestructura y Despliegue
- **Contenedores:** **Docker** y **Docker Compose** son utilizados para orquestar los servicios de base de datos (PostgreSQL) y el servidor de identidad (Keycloak) de manera ágil y reproducible.

---

## Estructura del Frontend

La estructura de carpetas de la aplicación cliente es la siguiente:

```text
src/
├── components/     # Componentes de UI reutilizables (Paginacion, CardLugar, MapaCanchas)
├── config/         # Configuraciones globales (Axios, API URLs)
├── context/        # Manejo de estado global (AuthContext)
├── hooks/          # Custom Hooks (useGeolocalizacion, useRutaMapa)
├── pages/          # Vistas principales y rutas (InfoCanchitas, Dashboard)
├── services/       # Integración con APIs externas (rutaService para OSRM)
├── utils/          # Funciones puras (fórmula Haversine, utilidades de Leaflet)
└── index.css       # Estilos globales y utilidades personalizadas
```

---

## Guía de Instalación y Ejecución Local

### Prerrequisitos
- Node.js (v18 o superior).
- Java 17+ y Maven (para el backend).
- **Docker** y **Docker Compose** instalados (para levantar Keycloak y PostgreSQL).

### 1. Levantar Servicios con Docker (Keycloak & Postgres)
Antes de ejecutar el backend, debes levantar la infraestructura de datos y seguridad:
1. Asegúrate de tener el demonio de Docker corriendo en tu sistema.
2. Navega a la carpeta raíz del backend donde se encuentra el archivo `docker-compose.yml`.
3. Ejecuta el comando para levantar los servicios en segundo plano:
   ```bash
   docker-compose up -d
   ```
4. *Nota:* Keycloak estará disponible (usualmente en el puerto 8080 u 8443) y PostgreSQL en el puerto 5432. Puedes acceder a la consola de Keycloak para importar el *Realm* del proyecto si es necesario.

### 2. Levantar el Backend (Spring Boot)
1. Clona el repositorio `sportmatch-backend` (si no lo has hecho).
2. Verifica que tu archivo `application.properties` (o `.yml`) apunte correctamente a los contenedores de Postgres y al servidor de Keycloak.
3. Ejecuta el proyecto desde tu IDE (IntelliJ/Eclipse) o mediante terminal con `mvn spring-boot:run`.

### 3. Levantar el Frontend
1. Entra a la carpeta del frontend `pnc-proyecto-final-frontend-ft-grupo-01-s02`.
2. Instala las dependencias:
   ```bash
   npm install
   ```
3. Ejecuta el servidor de desarrollo local:
   ```bash
   npm run dev
   ```
4. Abre `http://localhost:5173` en tu navegador.
