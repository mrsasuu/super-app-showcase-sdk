# Super App Showcase SDK

SDK for the [Super App Showcase](https://github.com/callstack/super-app-showcase).

Its purpose is three-fold:

- serve as source of truth for dependencies & dev-dependencies necessary for compatibility with the super-app
- provide utilities to use these dependencies easily in other workspaces & external repositories (`news-mini-app`)
- remove the necessity of keeping `shared` dependencies in-sync manually by automating the process

We use `rnx-kit/align-deps` to align the dependencies. Learn more about it [here](https://microsoft.github.io/rnx-kit/docs/guides/dependency-management).

Learn more about Super Apps here: [https://www.callstack.com/super-app-development](https://www.callstack.com/super-app-development?utm_campaign=super_apps&utm_source=github&utm_content=super_app_showcase).



# Super App Showcase SDK

This SDK helps align dependencies between a Super App **host** (built using [Re.Pack](https://github.com/callstack/repack)) and the **mini apps** that run within it.

It exports a preset and utility files that allow all projects to share the same runtime and development dependencies. This ensures compatibility and simplifies integration between independently developed apps.

---

## 🔧 Usage

Install the SDK in your host and all mini apps:

```sh
pnpm add @mrsasuu/super-app-showcase-sdk
```

Add the following configuration to your `package.json`:

```json
{
  "rnx-kit": {
    "kitType": "app",
    "alignDeps": {
      "presets": [
        "./node_modules/@mrsasuu/super-app-showcase-sdk/preset"
      ],
      "requirements": [
        "@mrsasuu/super-app-showcase-sdk@0.0.4"
      ],
      "capabilities": [
        "super-app"
      ]
    }
  }
}
```

Use the exported `rnxPreset` or the dependency configuration files to sync dependencies consistently across your project.

### What it does

- Exposes **production** and **development** dependency arrays through `lib/dependencies.json` and `lib/devDependencies.json`.
- Ensures **all apps use the same versions** of shared libraries (like `react`, `react-native`, etc.).
- Provides a preset (`preset.js`) that applies the same dependency configuration across all consuming apps.

To align a new dependency across the host and mini apps, simply add it to the appropriate list in this SDK.

> **Note:** At the moment, all listed dependencies apply to **both** the host and mini apps.

---

## 🚀 Releasing new versions

This package uses custom release scripts.

### Bump the version:

```sh
pnpm run bump patch   # or "minor" / "major"
```

### Publish the package:

```sh
pnpm run publish
```

---

## 📌 Current Behavior

The SDK currently applies **all shared dependencies to both the host and all mini apps**. While in a realistic scenario only the **host** would require all dependencies, this SDK treats every app the same to simplify setup and demonstrate the concept.

---

## 💡 Architectural Notes

This project is a **showcase** of how to align dependencies in a Super App architecture. It's intentionally simplified.

In a more advanced setup, dependencies could be grouped by **capabilities** (e.g., camera, location, auth), so a mini app only includes the dependencies it needs. Some ideas to scale this SDK further include:

- Splitting dependencies by capabilities.
- Automatically applying capability-specific dependencies to apps that require them.
- Providing a configuration client to define required capabilities per mini app.

These approaches could improve scalability but also introduce complexity and maintenance overhead. They are **not implemented** in this showcase.

---

## 🧳 Mono repo vs Poly repo

- In a **mono repo**, this SDK could live inside the same workspace as the host and mini apps.
- In a **poly repo**, the SDK must be published as a standalone package so it can be reused across independent projects.

---

# 🇪🇸 Super App Showcase SDK

Este SDK ayuda a alinear dependencias entre una Super App **host** (usando [Re.Pack](https://github.com/callstack/repack)) y las **mini apps** que se ejecutan dentro de ella.

Exporta una configuración y archivos utilitarios que permiten compartir dependencias de producción y desarrollo entre todos los proyectos, garantizando compatibilidad y facilitando la integración.

---

## 🔧 Uso

Instala el SDK en el host y en todas las mini apps:

```sh
pnpm add @mrsasuu/super-app-showcase-sdk
```

Añade la siguiente configuración a tu `package.json`:

```json
{
  "rnx-kit": {
    "kitType": "app",
    "alignDeps": {
      "presets": [
        "./node_modules/@mrsasuu/super-app-showcase-sdk/preset"
      ],
      "requirements": [
        "@mrsasuu/super-app-showcase-sdk@0.0.4"
      ],
      "capabilities": [
        "super-app"
      ]
    }
  }
}
```

Usa el `rnxPreset` exportado o los archivos de dependencias para mantener sincronización entre los proyectos.

### Qué hace

- Expone arrays de dependencias de **producción** y **desarrollo** (`lib/dependencies.json`, `lib/devDependencies.json`).
- Asegura que **todas las apps usen las mismas versiones** de bibliotecas compartidas como `react` y `react-native`.
- Proporciona un preset (`preset.js`) que aplica la configuración de dependencias a todos los proyectos que consumen el SDK.

Para alinear un nuevo paquete entre el host y las mini apps, basta con añadirlo a las listas de dependencias del SDK.

> **Nota:** Actualmente, todas las dependencias listadas se aplican tanto al **host** como a todas las **mini apps**.

---

## 🚀 Publicación de nuevas versiones

Este paquete usa scripts personalizados para lanzar nuevas versiones.

### Aumentar la versión:

```sh
pnpm run bump patch   # o "minor" / "major"
```

### Publicar el paquete:

```sh
pnpm run publish
```

---

## 📌 Comportamiento actual

El SDK actualmente aplica **todas las dependencias compartidas tanto al host como a todas las mini apps**. En un caso realista, solo el **host** debería tener todas las dependencias, pero este SDK aplica la misma configuración a todos para simplificar el ejemplo.

---

## 💡 Notas de arquitectura

Este proyecto sirve como **ejemplo** de cómo alinear dependencias dentro de una arquitectura de Super App. Está diseñado para ser simple.

En un sistema más avanzado, se podrían agrupar las dependencias por **capacidades** (por ejemplo: cámara, localización, autenticación), y aplicar solo las necesarias en cada mini app. Algunas ideas para escalar este SDK podrían incluir:

- Dividir las dependencias por capacidades.
- Aplicar automáticamente las dependencias necesarias según las capacidades requeridas.
- Ofrecer un cliente de configuración para definir las capacidades por mini app.

Estas ideas **no están implementadas** en este ejemplo.

---

## 🧳 Mono repo vs Poly repo

- En un **mono repo**, el SDK puede vivir en el mismo workspace que el host y las mini apps.
- En un **poly repo**, el SDK debe publicarse como un paquete independiente para ser reutilizado entre distintos proyectos.
