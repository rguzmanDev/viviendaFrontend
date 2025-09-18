# 🔐 Módulo Auth (Autenticación)

## 📋 Descripción
Módulo encargado de la autenticación y autorización de usuarios y administradores.

## 📱 Pantallas

### 🚪 **login** (Inicio de Sesión Usuario)
- **Tipo:** Página
- **Descripción:** Login para usuarios compradores
- **Funcionalidades:**
  - Email/contraseña
  - Integración con redes sociales (Google, Facebook)
  - Recordar sesión
  - Enlace a registro
  - Recuperar contraseña

### 📝 **register** (Registro de Usuario)
- **Tipo:** Página
- **Descripción:** Registro para nuevos usuarios compradores
- **Funcionalidades:**
  - Formulario de registro completo
  - Validaciones en tiempo real
  - Términos y condiciones
  - Confirmación por email
  - Registro con redes sociales

### 🛡️ **admin-login** (Inicio de Sesión Admin)
- **Tipo:** Página
- **Descripción:** Login específico para administradores/agentes
- **Funcionalidades:**
  - Autenticación con mayor seguridad
  - Captcha o 2FA
  - Sesión con tiempo limitado
  - Acceso al panel administrativo

## 🧩 Componentes Compartidos

### 📱 **login-form**
- **Descripción:** Formulario reutilizable de login
- **Uso:** En login y admin-login
- **Campos:** Email, contraseña, recordar sesión

### 🔗 **social-login**
- **Descripción:** Botones de login con redes sociales
- **Uso:** En login y register
- **Opciones:** Google, Facebook, Apple

### ✅ **password-strength**
- **Descripción:** Indicador de fortaleza de contraseña
- **Uso:** En register y cambio de contraseña

## 🔧 Servicios

### 🔐 **auth.service.ts**
- Login de usuario
- Registro de usuario
- Logout
- Verificar token
- Refrescar token
- Recuperar contraseña

### 👤 **user.service.ts**
- Obtener perfil de usuario
- Actualizar perfil
- Gestión de preferencias

### 🛡️ **admin-auth.service.ts**
- Login de administrador
- Verificar permisos de admin
- Gestión de roles

## 🎯 Modelos/Interfaces

### 👤 **User**
```typescript
interface User {
  id: string;
  email: string;
  firstName: string;
  lastName: string;
  phone?: string;
  avatar?: string;
  preferences: UserPreferences;
  role: 'user' | 'admin' | 'agent';
  isActive: boolean;
  createdAt: Date;
}
```

### 🔑 **LoginRequest**
```typescript
interface LoginRequest {
  email: string;
  password: string;
  rememberMe?: boolean;
}
```

### 📝 **RegisterRequest**
```typescript
interface RegisterRequest {
  email: string;
  password: string;
  firstName: string;
  lastName: string;
  phone?: string;
  acceptTerms: boolean;
}
```

### 🎫 **AuthResponse**
```typescript
interface AuthResponse {
  user: User;
  accessToken: string;
  refreshToken: string;
  expiresIn: number;
}
```

## 🚀 Comandos para crear componentes

```bash
# Páginas
ng generate component features/auth/pages/login
ng generate component features/auth/pages/register
ng generate component features/auth/pages/admin-login

# Componentes
ng generate component features/auth/components/login-form
ng generate component features/auth/components/social-login
ng generate component features/auth/components/password-strength

# Servicios
ng generate service features/auth/services/auth
ng generate service features/auth/services/user
ng generate service features/auth/services/admin-auth
```