# GitFlow: Protección de la Rama `main` en GitHub

Este documento describe cómo evitar que alguien cree una rama desde `main` en un repositorio de GitHub utilizando GitFlow, configurando protecciones en las ramas.

## Pasos para Configurar Protecciones de Ramas en GitHub

### 1. Protección de la Rama `main` en GitHub

Sigue estos pasos para proteger la rama `main` y evitar que se realicen commits directos o se creen nuevas ramas a partir de ella:

- Ve a la pestaña **Settings** de tu repositorio en GitHub.
- En el menú de la izquierda, selecciona **Branches**.
- Bajo la sección "Branch protection rules", haz clic en **Add rule**.
- En "Branch name pattern", escribe `main` para aplicar la regla solo a esta rama.
- Activa la opción **Restrict who can push to matching branches**. Esto impedirá que se realicen commits directos o que se creen ramas desde `main`.
- Puedes seleccionar los usuarios o equipos que tienen permiso para crear ramas a partir de `main` si lo deseas, o dejarlo completamente bloqueado.

### 2. Enfoque GitFlow

En el modelo de GitFlow, el trabajo de desarrollo se realiza en la rama `develop`, mientras que las ramas de características (`feature/`) se crean a partir de `develop`, **no desde `main`**. 

Bloquear la creación de ramas desde `main` obliga a los desarrolladores a crear sus ramas a partir de `develop`, alineándose con las mejores prácticas del flujo de trabajo GitFlow.

### 3. Configurar Políticas de Pull Requests (PR)

Para reforzar este flujo de trabajo, puedes configurar GitHub para que:

- Todos los cambios en `main` se hagan únicamente a través de **Pull Requests**.
- Se requiera la aprobación de otros miembros del equipo antes de fusionar.
- Se ejecuten pruebas automáticas que deben aprobarse antes de completar la fusión.

## Resultado

Con estas protecciones en su lugar, los desarrolladores no podrán crear ramas directamente desde `main`, lo que garantiza que las ramas de características se creen a partir de `develop`. Además, los cambios solo se integrarán en `main` cuando se fusionen versiones estables, respetando el flujo de trabajo de GitFlow.