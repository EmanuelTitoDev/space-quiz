# Misión Espacial · Quiz

Un quiz interactivo en español sobre el espacio. Responde diez preguntas de opción múltiple, consulta la explicación de cada respuesta y descubre tu puntuación al final. La interfaz se adapta al tema claro u oscuro del dispositivo y permite repetir la misión.

## Ejecutar en local

No necesitas instalar dependencias ni compilar el proyecto. Abre `index.html` directamente en un navegador.

También puedes servir la carpeta con cualquier servidor estático. Por ejemplo, con Python:

```bash
python -m http.server 8000
```

Después, visita <http://localhost:8000>.

## Publicación

El sitio se publica en GitHub Pages mediante GitHub Actions al hacer push a `main`. El flujo sube los archivos estáticos del repositorio y despliega el artefacto; no hay un paso de compilación.
