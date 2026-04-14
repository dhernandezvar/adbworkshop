# 🧪 Lab: Creación de Autonomous Database (ADB) Serverless en OCI

## 📌 Objetivo
Crear una **Autonomous Database Serverless** en Oracle Cloud Infrastructure (OCI) utilizando la consola web.

---

## 🔹 Paso 1: Navegar al servicio

1. Inicia sesión en OCI
2. Ir a:
   ```
   ☰ Menu → Oracle Database → Autonomous Database
   ```
3. Click en:
   ```
   Create Autonomous Database
   ```

---

## 🔹 Paso 2: Configuración básica

Completa los siguientes campos:

- **Display Name:**
  ```
  ADB-LAB
  ```

- **Database Name:**
  ```
  ADBLAB
  ```

- **Compartment:**
  ```
  TuNombre-OCI
  ```

---

## 🔹 Paso 3: Seleccionar tipo de workload

Selecciona:

```
Transaction Processing
```

📌 Este tipo es ideal para:
- Aplicaciones transaccionales
- OLTP
- Cargas de trabajo concurrentes

---

## 🔹 Paso 4: Configuración de la base de datos

### Always Free
- Deshabilitado

### Choose Database Version
```
26ai
```

### ECPU Count
```
2 ECPU
```

### Compute Auto Scaling
- Deshabilitado

### Storage
```
20 GB
```

### Storage Auto Scaling
- Deshabilitado

---

## 🔹 Paso 5: Opciones avanzadas

Expandir **Advanced options**:

- **Automatic Backup Retention:**
  ```
  1 day
  ```

- **Backup Retention Lock:**
  - No habilitar

---

## 🔹 Paso 6: Credenciales de administrador

- **Username:**
  ```
  ADMIN
  ```

- **Password:**
  Definir una contraseña segura

---

## 🔹 Paso 7: Crear la base de datos

```
Create Autonomous Database
```

---

## 🔹 Paso 8: Verificar estado

Esperar a que el estado sea:

```
Available
```

---

## ✅ Resultado esperado

- Autonomous Database creada correctamente
- Lista para conexiones
- Disponible para herramientas como Database Actions y APEX

---



