# Guía de Despliegue (Investigación - Punto Extra)

## Opción 1: Fly.io

Fly.io permite desplegar aplicaciones dockerizadas fácilmente.

### Prerrequisitos
1. Instalar `flyctl`:
   ```bash
   curl -L https://fly.io/install.sh | sh
   ```
2. Crear una cuenta en [fly.io](https://fly.io).
3. Loguearse:
   ```bash
   fly auth login
   ```

### Pasos para desplegar
1. Inicializar la aplicación (detectará el Dockerfile):
   ```bash
   fly launch
   ```
   - Responde `y` para copiar la configuración al archivo `fly.toml`.
   - Ajusta la región si es necesario.

2. Desplegar:
   ```bash
   fly deploy
   ```

3. Tu aplicación estará disponible en `https://<nombre-app>.fly.dev`.

## Opción 2: Render.com

Render puede construir tu Dockerfile automáticamente desde GitHub.

### Pasos
1. Sube tu código a un repositorio de GitHub.
2. Crea una cuenta en [render.com](https://render.com).
3. Selecciona "New +" -> "Web Service".
4. Conecta tu cuenta de GitHub y selecciona el repositorio `fastapi-ci-cd-example`.
5. Render detectará el `Dockerfile` automáticamente.
6. Elige el plan "Free".
7. Click en "Create Web Service".

Render construirá la imagen y la desplegará. La URL será provista en el dashboard.
