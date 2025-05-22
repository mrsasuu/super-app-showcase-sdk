# Super App Showcase SDK

This repository serves as a showcase for implementing a Super App architecture using React Native. It demonstrates best practices for sharing code and native modules across multiple mini apps in a polyrepo setup.

## Repository Structure

```
.
├── sdk/                  # Core SDK for dependency management
│   └── README.md        # SDK documentation
├── modules/             # Shared native modules
│   ├── README.md       # Modules documentation
│   └── locationModule/ # Example location module
└── README.md           # This file
```

## What's Inside?

### SDK
The `sdk` directory contains the core SDK that helps align dependencies between the Super App host and mini apps. It ensures all apps use the same versions of shared libraries and provides utilities for easy integration.

### Modules
The `modules` directory contains shared native modules that can be used across different mini apps. Each module is published as a separate package and can be consumed independently.

## Getting Started

1. Check out the [SDK documentation](./sdk/README.md) to learn about dependency management
2. Explore the [modules documentation](./modules/README.md) to understand how to use shared native modules
3. Look at the [location module](./modules/locationModule/README.md) as an example of a shared native module

## Contributing

This is a showcase repository. Feel free to use it as a reference for your own Super App implementation.

## License

MIT

---

# Super App Showcase SDK

Este repositorio sirve como ejemplo para implementar una arquitectura Super App usando React Native. Demuestra las mejores prácticas para compartir código y módulos nativos entre múltiples mini apps en una configuración polyrepo.

## Estructura del Repositorio

```
.
├── sdk/                  # SDK principal para gestión de dependencias
│   └── README.md        # Documentación del SDK
├── modules/             # Módulos nativos compartidos
│   ├── README.md       # Documentación de módulos
│   └── locationModule/ # Módulo de ubicación de ejemplo
└── README.md           # Este archivo
```

## ¿Qué Contiene?

### SDK
El directorio `sdk` contiene el SDK principal que ayuda a alinear dependencias entre el host de la Super App y las mini apps. Asegura que todas las apps usen las mismas versiones de bibliotecas compartidas y proporciona utilidades para una fácil integración.

### Módulos
El directorio `modules` contiene módulos nativos compartidos que pueden usarse en diferentes mini apps. Cada módulo se publica como un paquete separado y puede consumirse de forma independiente.

## Comenzando

1. Consulta la [documentación del SDK](./sdk/README.md) para aprender sobre la gestión de dependencias
2. Explora la [documentación de módulos](./modules/README.md) para entender cómo usar los módulos nativos compartidos
3. Revisa el [módulo de ubicación](./modules/locationModule/README.md) como ejemplo de un módulo nativo compartido

## Contribuir

Este es un repositorio de ejemplo. Siéntete libre de usarlo como referencia para tu propia implementación de Super App.
