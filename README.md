# FESTIVAL CONTROL · React Native + Expo Web + Amplify Data

Demo de operaciones de festival para Expo Web. Mantiene la identidad visual del cuaderno 04-PILARES-SERVERLESS: fondo `#090909`, cards `#151515`, acento `#FF2F92`, confirmado `#39D98A` y retrasado `#F5C542`.

## Inicio rápido

```bash
npm ci
npm run web
```

La app necesita `amplify_outputs.json`, generado al desplegar el backend. Este archivo está ignorado por Git y no debe subirse al repositorio.

## Exportación para AWS Amplify Hosting

```bash
npm run build:web
```

El resultado estático se genera en `dist/`. Conecta la rama `demo/backend` en Amplify Hosting con Fullstack CI/CD y usa `amplify.yml`. El pipeline despliega Amplify Data y después publica `dist/`.

El modelo `Event` está en `amplify/data/resource.ts`. Amplify Data genera la API GraphQL de AppSync y la tabla DynamoDB. La API usa una API key pública para esta demo; no guardes datos sensibles.

## Prueba de alumno

1. Abrir **Eventos** y filtrar por escenario o artista.
2. Crear `TECHNO TITANS`, escenario `MAIN STAGE`, hora `21:45` y estado `CONFIRMED`.
3. Editar el evento y cambiar la hora a `23:00`.
4. Cambiar el estado a `DELAYED`.
5. Eliminar el evento.

Los cuatro eventos de ejemplo se insertan en DynamoDB la primera vez que la tabla está vacía. Las altas, ediciones, cambios de estado y eliminaciones posteriores persisten en DynamoDB.

## Referencia docente

https://github.com/albertohdezakkari/04-PILARES-SERVERLESS
