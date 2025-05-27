# Manual de Instalación

## Requisitos

- Node.js (versión 18 o superior)
- MongoDB (local oMongoDB Atlas)

## Estructura del proyecto

- **Gateway**: Puerto 3000 - Punto de entrada a la aplicación
- **User Services**: Puerto 3100 - Gestión de usuarios y autenticación
- **Content Services**: Puerto 3200 - Gestión de contenido

## Pasos de instalación

### 1. Clonar el repositorio

```bash
git clone <https://github.com/noefaguero/altemap.git>
cd altemap
git submodule update --init --recursive
```

### 2. Instalar dependencias

Es necesario instalar las dependencias de cada microservicio y la aplicación web:

```bash
# Gateway
cd api/gateway
npm install

# User Service
cd api/user-services
npm install

# Content Service
cd api/content-services
npm install

# Website
cd website
npm install
```

### 4. Iniciar la aplicación

#### Modo desarrollo

```bash
# Website
cd website
npm run dev

# Servidor con todos los microservicios
cd api/gateway
npm run dev:server
```

El comando `dev:server` utiliza `concurrently` para iniciar simultáneamente:
- User Services en el puerto 3100
- Content Services en el puerto 3200
- Gateway en el puerto 3000

#### Modo producción

```bash
cd api/altemap-gateway
npm run start

# User Service
cd api/altemap-user-services
npm run start

# Content Service
cd api/altemap-content-services
npm run start
```