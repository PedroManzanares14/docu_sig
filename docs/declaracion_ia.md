# Declaración de Uso de Inteligencia Artificial

Cumpliendo con los criterios de evaluación y ética académica, documentamos el uso de herramientas de Inteligencia Artificial durante el ciclo de vida de desarrollo de Sportmatch.

## Herramientas Utilizadas
- **Antigravity / Gemini (Google DeepMind):** Actuó como asistente de programación en modalidad *Pair-Programming* interactiva (IDE agent).

## Áreas de Aplicación

La IA fue utilizada principalmente en las etapas de codificación, integración y refactorización para las Historias de Usuario HU-22, HU-23 (Agrupadas internamente como HU-30) y para la resolución de conflictos (Merge):

### 1. Lógica de Geolocalización (HU-22)
- **Implementación Matemática:** Se utilizó la IA para escribir la función de la fórmula Haversine (`distancia.js`), garantizando precisión en el cálculo de distancia en kilómetros entre dos coordenadas GPS (usuario y canchas).
- **Hooks Personalizados:** Se generó el hook `useGeolocalizacion.js` con soporte para el manejo de estados asíncronos (`cargando`, `error`), gestión de permisos del navegador y rastreo de posición en tiempo real (`watchPosition`).

### 2. Trazado de Rutas (HU-23)
- **Integración de OSRM:** La IA asistió en la creación de `rutaService.js` para consumir la API pública de *OpenStreetMap Routing Machine* (OSRM).
- **Decodificación de Polyline:** Se delegó a la IA la escritura del algoritmo para decodificar las cadenas Polyline versión 5 que retorna OSRM, traduciéndolas a arrays de coordenadas inteligibles por `react-leaflet`.

### 3. Fusión de Ramas (Resolución de divergencias)
- Se utilizó el agente para analizar las divergencias entre el entorno de desarrollo principal y una rama paralela (`ACA`) que contenía un *Dashboard de Administrador* y un componente de *Paginación*.
- La IA realizó un `diff --no-index` para leer los cambios, copiar los archivos selectivamente e inyectarlos de manera segura (`App.jsx`, `NavBar.jsx`) sin causar regresiones en el código de mapas.

## Supervisión Humana y Autoría
Aunque la IA generó fragmentos significativos de código funcional, el equipo de desarrollo (humanos) se encargó de:
1. **Diseño del requerimiento:** Proveer rúbricas detalladas, criterios de aceptación y directrices de UI.
2. **Revisión Arquitectónica:** Decidir *dónde* y *cómo* los componentes debían interactuar (ej. enlazar los botones del UI a las funciones del hook).
3. **Validación (Testing):** Ejecutar pruebas manuales y aprobar los *Commits* paso a paso mediante revisiones atómicas, asegurando que la IA no rompiera implementaciones previas.

**Conclusión:** La IA sirvió como un copiloto de alto rendimiento, acelerando tareas algorítmicas repetitivas, pero el diseño estructural, la toma de decisiones y la responsabilidad del producto final residen exclusivamente en los autores del proyecto.
