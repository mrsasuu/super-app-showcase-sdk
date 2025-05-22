# Location Module

A native module that provides location services functionality for React Native applications in the Super App ecosystem. This module is designed to be shared across all mini apps that require location services.

## Features

- Get current location
- Request location permissions
- Monitor location changes
- Calculate distance between coordinates
- Handle location errors gracefully

## Installation

```sh
pnpm add @mrsasuu/react-native-location
```

## Usage

```typescript
import { LocationModule } from '@mrsasuu/react-native-location';

// Request location permission
const hasPermission = await LocationModule.requestPermission();

// Get current location
const location = await LocationModule.getCurrentLocation();

// Monitor location changes
const subscription = LocationModule.watchLocation((location) => {
  console.log('New location:', location);
});

// Stop watching location
subscription.remove();
```

## API Reference

### `requestPermission()`
Requests location permission from the user.

### `getCurrentLocation()`
Returns the current location of the device.

### `watchLocation(callback)`
Starts watching for location changes.

### `calculateDistance(lat1, lon1, lat2, lon2)`
Calculates the distance between two coordinates in meters.

## Platform Specific Setup

### iOS
Add the following to your `Info.plist`:
```xml
<key>NSLocationWhenInUseUsageDescription</key>
<string>We need your location to provide location-based services</string>
<key>NSLocationAlwaysAndWhenInUseUsageDescription</key>
<string>We need your location to provide location-based services</string>
```

### Android
Add the following to your `AndroidManifest.xml`:
```xml
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
```

---

# Módulo de Ubicación

Un módulo nativo que proporciona funcionalidad de servicios de ubicación para aplicaciones React Native en el ecosistema Super App. Este módulo está diseñado para ser compartido entre todas las mini apps que requieran servicios de ubicación.

## Características

- Obtener ubicación actual
- Solicitar permisos de ubicación
- Monitorear cambios de ubicación
- Calcular distancia entre coordenadas
- Manejar errores de ubicación

## Instalación

```sh
pnpm add @mrsasuu/react-native-location
```

## Uso

```typescript
import { LocationModule } from '@mrsasuu/react-native-location';

// Solicitar permiso de ubicación
const hasPermission = await LocationModule.requestPermission();

// Obtener ubicación actual
const location = await LocationModule.getCurrentLocation();

// Monitorear cambios de ubicación
const subscription = LocationModule.watchLocation((location) => {
  console.log('Nueva ubicación:', location);
});

// Detener monitoreo de ubicación
subscription.remove();
```

## Referencia de API

### `requestPermission()`
Solicita permiso de ubicación al usuario.

### `getCurrentLocation()`
Devuelve la ubicación actual del dispositivo.

### `watchLocation(callback)`
Inicia el monitoreo de cambios de ubicación.

### `calculateDistance(lat1, lon1, lat2, lon2)`
Calcula la distancia entre dos coordenadas en metros.

## Configuración Específica por Plataforma

### iOS
Añade lo siguiente a tu `Info.plist`:
```xml
<key>NSLocationWhenInUseUsageDescription</key>
<string>Necesitamos tu ubicación para proporcionar servicios basados en ubicación</string>
<key>NSLocationAlwaysAndWhenInUseUsageDescription</key>
<string>Necesitamos tu ubicación para proporcionar servicios basados en ubicación</string>
```

### Android
Añade lo siguiente a tu `AndroidManifest.xml`:
```xml
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
``` 