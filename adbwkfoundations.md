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

# 🔐 Acceso a herramientas de Autonomous Database (ADB)

## 🎯 ¿Qué es esta pantalla?
<img width="376" height="412" alt="image" src="https://github.com/user-attachments/assets/54b4c103-9909-48e3-a26a-3a06fd0304f2" />


Esta pantalla corresponde al acceso a **SQL Developer Web (ORDS)** en Autonomous Database.

Permite:

- Ejecutar consultas SQL  
- Crear tablas  
- Administrar tu esquema  
- Trabajar directamente desde el navegador  

---

## 🌐 URL de acceso

Utiliza la siguiente URL:

```
https://g2b25df4d191947-danielatp.adb.us-ashburn-1.oraclecloudapps.com/ords/sql-developer
```

---

## 🧠 Concepto clave

El acceso requiere:

- Usuario de base de datos: Debes colocar la inicial de tu nombre seguido del primer apellido, todo en mayúscula  
- Password: Será entregado por el entrenador.  
- **Path (alias del schema)**, en este caso, es igual a tu usuario.  
📌 Usuario = identidad real en la base de datos (login), Path = alias web del schema que ORDS usa para enrutar el acceso (/ords/<alias>).
---

# 🧭 Paso a paso

## 1️⃣ Abrir la URL

Abre en tu navegador:

```
https://g2b25df4d191947-danielatp.adb.us-ashburn-1.oraclecloudapps.com/ords/sql-developer
```

---

## 2️⃣ Expandir Advanced

1. En la pantalla de login  
2. Haz clic en: **Advanced**

---

## 3️⃣ Configurar el Path

En el campo **Path**, escribe:

```
<tuusuario>
```

👉 Debe coincidir con el alias definido en ORDS  
👉 Normalmente en minúsculas  

---

## 4️⃣ Ingresar credenciales

- **Username**:
```
<TUUSUARIO>
```

- **Password**:
👉 Tu contraseña de base de datos  

---

## 5️⃣ Iniciar sesión

Haz clic en:

👉 **Sign in**

---

## ✅ Resultado esperado

Accederás a:

👉 SQL Developer Web

---

## ⚠️ Errores comunes

### ❌ Path incorrecto
- Usar mayúsculas o nombre distinto al alias

### ❌ No usar Advanced
- El login falla porque falta el Path

---

## 💡 Tip

El acceso realmente funciona así:

```
https://.../ords/<tuusuario>
```

👉 Ese valor es el mismo que colocas en el campo **Path**




