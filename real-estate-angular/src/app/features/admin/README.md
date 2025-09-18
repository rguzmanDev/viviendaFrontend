# 🛡️ Módulo Admin (Administración)

## 📋 Descripción
Módulo del panel administrativo para gestión completa de propiedades y sistema.

## 📱 Pantallas

### 📊 **admin-dashboard** (Dashboard Principal)
- **Tipo:** Página
- **Descripción:** Panel principal con resumen y métricas
- **Funcionalidades:**
  - Estadísticas de propiedades
  - Gráficos de ventas
  - Actividad reciente
  - Accesos rápidos al CRUD
  - Notificaciones importantes

### 📋 **property-management** (Gestión de Propiedades)
- **Tipo:** Página
- **Descripción:** Tabla completa de todas las propiedades
- **Funcionalidades:**
  - Lista/tabla de propiedades
  - Filtros y búsqueda avanzada
  - Acciones: editar, eliminar, marcar como vendida
  - Exportar datos
  - Paginación y ordenamiento

### ➕ **property-create** (Crear Propiedad)
- **Tipo:** Página
- **Descripción:** Formulario para agregar nueva propiedad
- **Funcionalidades:**
  - Formulario completo de propiedad
  - Subida múltiple de imágenes
  - Validaciones en tiempo real
  - Guardado como borrador
  - Vista previa

### ✏️ **property-edit** (Editar Propiedad)
- **Tipo:** Página
- **Descripción:** Formulario para actualizar propiedad existente
- **Funcionalidades:**
  - Formulario pre-cargado con datos
  - Gestión de imágenes existentes
  - Historial de cambios
  - Vista previa de cambios

## 🧩 Componentes Compartidos

### 📝 **property-form**
- **Descripción:** Formulario reutilizable de propiedad
- **Uso:** En property-create y property-edit
- **Campos:** Título, precio, ubicación, características, descripción

### 📊 **stats-widget**
- **Descripción:** Widget de estadísticas reutilizable
- **Uso:** En admin-dashboard
- **Tipos:** Contador, gráfico, progreso

### 📋 **property-table**
- **Descripción:** Tabla avanzada de propiedades
- **Uso:** En property-management
- **Funciones:** Filtros, ordenamiento, acciones por fila

### 📷 **image-upload**
- **Descripción:** Componente para subir y gestionar imágenes
- **Uso:** En property-form
- **Funciones:** Drag & drop, preview, eliminar, reordenar

### 🏷️ **property-status-badge**
- **Descripción:** Badge de estado de propiedad
- **Uso:** En tablas y tarjetas
- **Estados:** Disponible, vendida, reservada

## 🔧 Servicios

### 🏠 **property-admin.service.ts**
- CRUD completo de propiedades
- Cambiar estado de propiedades
- Subir/eliminar imágenes
- Exportar datos

### 📊 **dashboard.service.ts**
- Obtener estadísticas generales
- Gráficos de rendimiento
- Actividad reciente
- Métricas de ventas

### 🔧 **admin.service.ts**
- Funciones generales de administración
- Gestión de usuarios
- Configuraciones del sistema
- Logs de actividad

## 🎯 Modelos/Interfaces

### 🏠 **PropertyAdmin**
```typescript
interface PropertyAdmin extends Property {
  createdBy: string;
  updatedBy: string;
  createdAt: Date;
  updatedAt: Date;
  viewsCount: number;
  contactsCount: number;
  status: 'draft' | 'published' | 'sold' | 'reserved' | 'archived';
}
```

### 📊 **DashboardStats**
```typescript
interface DashboardStats {
  totalProperties: number;
  activeProperties: number;
  soldProperties: number;
  totalViews: number;
  monthlyStats: MonthlyStats[];
  recentActivity: Activity[];
}
```

### 📋 **PropertyFilters**
```typescript
interface PropertyFilters {
  status?: PropertyStatus[];
  priceRange?: { min: number; max: number };
  dateRange?: { start: Date; end: Date };
  location?: string;
  agent?: string;
}
```

## 🚀 Comandos para crear componentes

```bash
# Páginas
ng generate component features/admin/pages/admin-dashboard
ng generate component features/admin/pages/property-management
ng generate component features/admin/pages/property-create
ng generate component features/admin/pages/property-edit

# Componentes
ng generate component features/admin/components/property-form
ng generate component features/admin/components/stats-widget
ng generate component features/admin/components/property-table
ng generate component features/admin/components/image-upload
ng generate component features/admin/components/property-status-badge

# Servicios
ng generate service features/admin/services/property-admin
ng generate service features/admin/services/dashboard
ng generate service features/admin/services/admin
```

## 🔐 Consideraciones de Seguridad

- Todas las rutas requieren autenticación de admin
- Validación de permisos en cada acción
- Logs de todas las operaciones CRUD
- Confirmación para acciones destructivas