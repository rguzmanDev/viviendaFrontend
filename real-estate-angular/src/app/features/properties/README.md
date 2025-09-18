# 🏠 Módulo Properties (Propiedades)

## 📋 Descripción
Módulo encargado de la gestión, búsqueda y visualización de propiedades inmobiliarias.

## 📱 Pantallas

### 🔍 **property-list** (Resultados de Búsqueda)
- **Tipo:** Página
- **Descripción:** Listado de propiedades en formato de tarjetas con filtros
- **Funcionalidades:**
  - Grid/lista de propiedades
  - Filtros avanzados
  - Paginación
  - Ordenamiento por precio, fecha, etc.

### 🏡 **property-detail** (Detalle de Propiedad)
- **Tipo:** Página
- **Descripción:** Vista detallada de una propiedad específica
- **Funcionalidades:**
  - Galería de fotos
  - Descripción completa
  - Precio y características
  - Ubicación en mapa
  - Información del agente
  - Formulario de contacto integrado

## 🧩 Componentes Compartidos

### 📧 **contact-form**
- **Descripción:** Formulario para contactar al agente
- **Uso:** Integrado en property-detail o como modal
- **Campos:** Nombre, email, teléfono, mensaje

### 🏠 **property-card**
- **Descripción:** Tarjeta individual de propiedad
- **Uso:** En property-list y otros listados
- **Muestra:** Foto, precio, ubicación, características básicas

### 🔧 **property-filters**
- **Descripción:** Panel de filtros de búsqueda
- **Uso:** En property-list
- **Filtros:** Precio, ubicación, tipo, habitaciones, etc.

## 🔧 Servicios

### 📊 **property.service.ts**
- Obtener listado de propiedades
- Buscar propiedades con filtros
- Obtener detalle de propiedad
- Gestionar favoritos (si aplica)

### 📍 **location.service.ts**
- Servicios de geolocalización
- Integración con mapas
- Búsqueda por ubicación

## 🎯 Modelos/Interfaces

### 🏡 **Property**
```typescript
interface Property {
  id: string;
  title: string;
  price: number;
  location: Location;
  bedrooms: number;
  bathrooms: number;
  area: number;
  images: string[];
  description: string;
  status: 'available' | 'sold' | 'reserved';
  agent: Agent;
}
```

### 🔍 **SearchFilters**
```typescript
interface SearchFilters {
  priceMin?: number;
  priceMax?: number;
  location?: string;
  bedrooms?: number;
  bathrooms?: number;
  propertyType?: string;
}
```

## 🚀 Comandos para crear componentes

```bash
# Páginas
ng generate component features/properties/pages/property-list
ng generate component features/properties/pages/property-detail

# Componentes
ng generate component features/properties/components/contact-form
ng generate component features/properties/components/property-card
ng generate component features/properties/components/property-filters

# Servicios
ng generate service features/properties/services/property
ng generate service features/properties/services/location
```