# Declaración de Uso de Inteligencia Artificial

Cumpliendo con los criterios de evaluación y ética académica, documentamos el uso de herramientas de Inteligencia Artificial durante el ciclo de vida de desarrollo del proyecto Sportmatch.

## Herramientas Utilizadas
- **Antigravity / Gemini (Google DeepMind):** Actuó como asistente técnico virtual para agilizar y resolver cuellos de botella durante el desarrollo.

## Áreas de Aplicación

La Inteligencia Artificial se utilizó de manera responsable como una herramienta de apoyo, limitando su alcance a las siguientes áreas críticas:

### 1. Consulta y Uso de Librerías
Se empleó la IA para acelerar el aprendizaje y la integración de librerías específicas del ecosistema, como `react-leaflet` para la implementación de mapas y geolocalización. La herramienta se utilizó para consultar documentación sobre cómo implementar componentes específicos (ej. `Polyline`, `MapContainer`) y gestionar eficientemente sus propiedades, aplicando las mejores prácticas recomendadas.

### 2. Configuración y Levantamiento de la Ejecución
La IA fue consultada para entender y configurar el entorno de desarrollo de manera ágil. Nos apoyamos en ella para estandarizar los scripts de ejecución, revisar comandos de terminal (ej. dependencias de Node.js, configuraciones de Vite) y garantizar un despliegue local estable y fluido para todo el equipo.

### 3. Identificación y Solución de Errores (Debugging)
**Este fue el uso principal y más recurrente de la herramienta.** Durante el desarrollo, la IA sirvió activamente para:
- Analizar *stack traces* y registros de la consola para encontrar el origen de fallas complejas.
- Solucionar errores de sintaxis o de compilación (como fallas al procesar archivos CSS con Tailwind o problemas de versiones incompatibles).
- Detectar y corregir problemas de asincronía en React (hooks) y errores al interactuar con APIs externas (como el servicio OSRM).
- Resolver conflictos técnicos durante la integración de ramas (merge) en Git.

## Supervisión Humana y Autoría
Toda la concepción del producto, el diseño arquitectónico, las reglas de negocio y la aprobación final del código son de **estricta autoría humana**. La IA se limitó a un rol de soporte (similar a un consultor técnico interactivo) enfocado en destrabar errores de codificación y acelerar la investigación de librerías, recayendo la entera responsabilidad del sistema funcional sobre los autores del proyecto.
