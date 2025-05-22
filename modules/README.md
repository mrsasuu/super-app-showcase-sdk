# Native Modules in Super App Architecture

This directory contains native modules that are shared across the Super App ecosystem. In a polyrepo architecture, native modules need to be distributed as separate packages to ensure consistent functionality across all mini apps.

> **Note:** This is just an example implementation. Organizations can choose to share their native modules in any way that best fits their needs, whether it's through a monorepo, different package structure, or any other approach that works for their team.

## Why a Separate Package?

In a Super App with multiple mini apps (polyrepo), native modules must be:
- Version controlled independently
- Distributed through a package manager
- Compatible with all mini apps
- Maintained in a single source of truth

## Adding New Modules

To add new native modules to your Super App:
1. Create a new directory in the `modules` folder for your module
2. Develop your native module following the same structure as existing modules
3. Publish it to your chosen package registry
4. Add it to the "Available Modules" section below

## Package Distribution

This showcase demonstrates using GitHub Packages for distribution, but you can choose any package registry that fits your needs:
- npm Registry (public or private)
- GitHub Packages
- Artifactory
- Azure Artifacts
- Or any other package registry solution

## Current Implementation

This repository demonstrates how to:
1. Create native modules as a separate package
2. Publish them to GitHub Packages
3. Consume them in mini apps

## Usage

To use these native modules in your mini app:

1. Add the package to your dependencies
2. Link the native modules in your mini app's native code (If required).
3. Import and use the modules in your JavaScript/TypeScript code

## Available Modules

- [Location Module](./locationModule/README.md) - Location services integration

---

# Módulos Nativos en Arquitectura Super App

Este directorio contiene módulos nativos que se comparten en todo el ecosistema de la Super App. En una arquitectura polyrepo, los módulos nativos deben distribuirse como paquetes separados para garantizar una funcionalidad consistente en todas las mini apps.

> **Nota:** Esta es solo una implementación de ejemplo. Las organizaciones pueden elegir compartir sus módulos nativos de cualquier manera que mejor se adapte a sus necesidades, ya sea a través de un monorepo, una estructura de paquetes diferente, o cualquier otro enfoque que funcione para su equipo.

## ¿Por qué un Paquete Separado?

En una Super App con múltiples mini apps (polyrepo), los módulos nativos deben:
- Tener control de versiones independiente
- Distribuirse a través de un gestor de paquetes
- Ser compatibles con todas las mini apps
- Mantenerse en una única fuente de verdad

## Añadir Nuevos Módulos

Para añadir nuevos módulos nativos a tu Super App:
1. Crea un nuevo directorio en la carpeta `modules` para tu módulo
2. Desarrolla tu módulo nativo siguiendo la misma estructura que los módulos existentes
3. Publícalo en tu registro de paquetes elegido
4. Añádelo a la sección "Módulos Disponibles" más abajo

## Distribución de Paquetes

Este ejemplo demuestra el uso de GitHub Packages para la distribución, pero puedes elegir cualquier registro de paquetes que se adapte a tus necesidades:
- Registro npm (público o privado)
- GitHub Packages
- Artifactory
- Azure Artifacts
- O cualquier otra solución de registro de paquetes

## Implementación Actual

Este repositorio demuestra cómo:
1. Crear módulos nativos como un paquete separado
2. Publicarlos en GitHub Packages
3. Consumirlos en mini apps

## Uso

Para usar estos módulos nativos en tu mini app:

1. Añade el paquete a tus dependencias
2. Vincula los módulos nativos en el código nativo de tu mini app (Si tu módulo lo necesita).
3. Importa y usa los módulos en tu código JavaScript/TypeScript

## Módulos Disponibles

- [Módulo de Ubicación](./locationModule/README.md) - Integración de servicios de ubicación 