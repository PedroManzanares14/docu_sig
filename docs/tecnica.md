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
- **Seguridad:** JWT (JSON Web Tokens) para autenticación y autorización (roles `USER` y `ADMIN`).

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
- PostgreSQL instalado y corriendo en el puerto 5432.

### 1. Levantar el Backend
1. Clona el repositorio `sportmatch-backend`.
2. Actualiza el archivo `application.properties` con tus credenciales de PostgreSQL.
3. Ejecuta el proyecto desde tu IDE (IntelliJ/Eclipse) o mediante terminal con `mvn spring-boot:run`.

### 2. Levantar el Frontend
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
