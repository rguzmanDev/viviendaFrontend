# 🏠 Módulo HOME

## 📋 Descripción
Módulo principal de la página de inicio donde los usuarios pueden buscar propiedades.

## 📁 Pantallas (Pages)

### `home-page/`
- **Descripción**: Página principal del sitio
- **Funcionalidad**: 
  - Buscador de casas con filtros visibles
  - Banner principal
  - Secciones informativas
- **Comando**: `ng generate component features/home/pages/home-page`

## 🧩 Componentes (Components)

### `property-search/`
- **Descripción**: Componente buscador de propiedades
- **Funcionalidad**: 
  - Filtros de búsqueda (precio, ubicación, tipo)
  - Botón de búsqueda
  - Validaciones
- **Comando**: `ng generate component features/home/components/property-search`

### `hero-banner/` (opcional)
- **Descripción**: Banner principal de la página
- **Comando**: `ng generate component features/home/components/hero-banner`

### `feature-section/` (opcional)
- **Descripción**: Sección de características destacadas
- **Comando**: `ng generate component features/home/components/feature-section`

## 🔧 Servicios (Services)

### `home.service.ts`
- **Descripción**: Servicio para datos de la página principal
- **Comando**: `ng generate service features/home/services/home`

## 📄 Modelos (Models)

### `search-filters.interface.ts`
- **Descripción**: Interface para filtros de búsqueda
- **Propiedades**: precio, ubicación, tipo de propiedad, etc.

## 🛠️ Utilidades (Utils)

### `search-validators.ts`
- **Descripción**: Validadores personalizados para el buscador