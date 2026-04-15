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

---

# 🔐 Lab: Configuración de API Key para conexión desde ADB

---

## 🎯 Objetivo

En este laboratorio vamos a generar una **API Key de OCI** y utilizarla para crear una **credencial dentro de Autonomous Database (ADB)**.

👉 Esta credencial permitirá a la base de datos autenticarse contra servicios de OCI, como:

- OCI Generative AI  
- Object Storage  
- Otros servicios cloud  

---

## 🧠 ¿Qué es una API Key en OCI?

Una API Key en OCI está compuesta por:

- 🔑 **Llave privada** → se usa para firmar las peticiones  
- 🔓 **Llave pública** → se registra en OCI  
- 🆔 Identificadores (OCIDs) → indican quién eres  

👉 En conjunto, permiten autenticación segura sin usar usuario/password.

---

# 🧭 Paso 1: Ir al usuario en OCI

1. Ir a: **Identity & Security → Domains**
2. Abrir: **Default Domain**
3. Ir a: **User Management**
4. Seleccionar tu usuario

👉 Aquí estás entrando al perfil del usuario que generará la API Key.

---

# 🔑 Paso 2: Crear API Key

1. Ir al tab: **API Keys**
2. Dar clic en: **Add API Key**

---

## 🧭 Paso 3: Generar las llaves

1. Seleccionar: **Generate API Key Pair**
2. Descargar:
   - Private Key
   - Public Key

---

## ⚠️ Importante

- La **llave privada** NO se guarda en OCI  
- Solo se descarga una vez  
- La vas a usar más adelante en la base de datos  

---

# 🧾 Paso 4: Guardar configuración

```ini
[DEFAULT]
user=ocid1.user.oc1..aaaaaaaaxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
fingerprint=aa:bb:cc:dd:ee:ff:11:22:33:44:55:66:77:88:99:00
tenancy=ocid1.tenancy.oc1..aaaaaaaayyyyyyyyyyyyyyyyyyyyyyyy
region=us-ashburn-1
key_file=<path_to_private_key>
```

---

## 🧠 Explicación de cada elemento

| Campo | Descripción |
|------|------------|
| user | OCID del usuario |
| fingerprint | Identificador de la llave |
| tenancy | OCID del tenancy |
| region | Región OCI |
| key_file | Ruta del archivo |

---

# 🔍 Paso 5: Obtener la llave privada

1. Abrir la llave privada descargada con Notepad
2. Copiar contenido completo

```text
-----BEGIN PRIVATE KEY-----
...contenido...
-----END PRIVATE KEY-----
```

---

# 🧭 Paso 6: Crear credencial en ADB

```sql
BEGIN
  DBMS_CLOUD.CREATE_CREDENTIAL(
    credential_name => 'GENAI_CRED_<TUUSUARIO>',
    user_ocid       => 'ocid1.user.oc1..aaaaaaaaxxxxxxxxxxxxxxxxxxxxxxxxxxxxx',
    tenancy_ocid    => 'ocid1.tenancy.oc1..aaaaaaaayyyyyyyyyyyyyyyyyyyyyyyy',
    private_key     => '-----BEGIN PRIVATE KEY-----
<PEGAR_AQUI_TU_LLAVE_PRIVADA>
-----END PRIVATE KEY-----',
    fingerprint     => 'aa:bb:cc:dd:ee:ff:11:22:33:44:55:66:77:88:99:00'
  );
END;
/
```

---

## 🧠 Explicación

- credential_name → nombre lógico  
- user_ocid → identifica usuario  
- tenancy_ocid → tenancy OCI  
- private_key → llave privada  
- fingerprint → identifica llave  

---

# 🚀 Resultado

La credencial queda lista para usar con:

- DBMS_CLOUD  
- DBMS_CLOUD_AI  
- Integraciones OCI  

---

# 🎯 Siguiente paso

Usar esta credencial para configurar **Select AI**




