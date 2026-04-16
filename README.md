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
# 📥 Lab: Carga de datos en ADB usando Data Load

---

## 🎯 Objetivo

En esta sección del laboratorio vamos a cargar el archivo **BCR_ES_Dataset.xlsx** dentro de Autonomous Database utilizando la herramienta **Data Load**.

👉 Esto permitirá crear automáticamente las tablas en tu esquema para luego consultarlas con **Select AI**.

---

## 🧠 ¿Qué hace Data Load?

La herramienta **Data Load**:

- Permite cargar archivos Excel o CSV directamente desde el navegador  
- Detecta automáticamente las hojas (tabs) del archivo  
- Crea tablas automáticamente en tu esquema  
- Inserta los datos sin necesidad de escribir SQL  

👉 Es la forma más rápida de preparar datos para el laboratorio.

---

## 🧭 Paso a paso

### 1️⃣ Ir a Data Load

1. En el menú principal de ADB (SQL Developer Web)
2. Da clic en:
   👉 **Data Studio → Data Load**

---

### 2️⃣ Iniciar carga de datos

1. Da clic en:
   👉 **Load Data**

---

### 3️⃣ Seleccionar archivo local

1. Selecciona:
   👉 **Local Files**
2. Da clic en:
   👉 **Select Files**

---

### 4️⃣ Seleccionar el archivo

1. Busca y selecciona el archivo:

```text
BCR_ES_Dataset.xlsx
```

👉 Puedes descargarlo desde la guía del laboratorio.

---

### 5️⃣ Validar detección de hojas

Después de seleccionar el archivo:

- Verás que aparecen **3 registros**
- Cada uno corresponde a una hoja del Excel

👉 Esto significa que:

- Se crearán **3 tablas automáticamente**
- Cada hoja = una tabla en tu esquema

---

### 6️⃣ Iniciar la carga

1. Da clic en:
   👉 **Start**

---

### 7️⃣ Ejecutar el proceso

1. Confirma la configuración
2. Da clic en:
   👉 **Run**

---

### 8️⃣ Monitorear la carga

1. Ve a la sección:
   👉 **Table and View Loads**

Aquí podrás ver:

- El progreso de carga de cada tabla  
- El estado del job  

---

## ✅ Resultado esperado

Una vez finalizado el proceso:

- Verás un **mensaje de éxito**
- Las tablas estarán disponibles en tu esquema

Ejemplo:

```text
INDICADORES_MACRO
SISTEMA_BANCARIO
TRANSACCIONES_FINANCIERAS
```

---

## 🚀 Siguiente paso

Con las tablas cargadas ya puedes:

- Consultar datos con SQL  
- Usar **SELECT AI** en lenguaje natural  

---

## 💡 Tip para el laboratorio

Si no ves las tablas:

- Refresca el esquema  
- Verifica que estás en el usuario correcto  

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

---

# 🤖 Lab: Configuración de Select AI con OCI Generative AI en ADB

---

## 🎯 Objetivo

En este laboratorio vamos a preparar **Select AI** dentro de Autonomous Database para que pueda interpretar preguntas en lenguaje natural y traducirlas a consultas SQL usando **OCI Generative AI**.

Al finalizar, el usuario podrá:

- Crear y validar un **AI Profile**
- Confirmar que ADB puede usar el proveedor de AI configurado
- Probar consultas con tres modos:
  - `showsql` → mostrar el SQL generado
  - `runsql` → ejecutar la consulta generada
  - `narrate` → explicar el resultado en lenguaje natural

---

## 🧠 ¿Qué es un AI Profile?

Un **AI Profile** es la configuración que le dice a Autonomous Database:

- qué proveedor de AI usar,
- qué credencial utilizar para autenticarse,
- qué modelo de lenguaje invocar,
- y qué objetos de la base de datos puede consultar.

👉 En otras palabras, el AI Profile es el puente entre tu esquema de datos y el servicio de AI.

---

# 1️⃣ Ir al área de SQL en ADB

## 🎯 ¿Qué vamos a hacer?

Vamos a abrir el espacio donde ejecutaremos comandos SQL y PL/SQL dentro de Autonomous Database.

👉 Desde aquí vamos a crear el profile, validar que quedó registrado y después probar Select AI con preguntas reales.

## 🧭 Paso a paso

1. Ir al menú principal de ADB.
2. Seleccionar:
   **Development → SQL**

## 💡 Qué debes entender

Esta sección es el editor de SQL del navegador. Aquí no instalas nada localmente: todo se ejecuta directamente contra tu base de datos en la nube.

---

# 2️⃣ Crear el AI Profile

## 🎯 ¿Qué vamos a hacer?

Vamos a crear el perfil que Select AI usará para conectarse a OCI Generative AI.

Este perfil define:

- el proveedor: `oci`
- la credencial que autenticará la conexión
- la región donde corre el servicio
- el modelo de AI
- las tablas que podrán ser consultadas

## 🧾 Código

```sql
BEGIN
  DBMS_CLOUD_AI.CREATE_PROFILE(
    profile_name   => 'OCIGenAI_<TUUSUARIO>',
    attributes     =>'{
      "provider": "oci",
      "credential_name": "GENAI_CRED_<TUUSUARIO>",
      "region": "us-ashburn-1",
      "model": "xai.grok-4",
      "object_list": [
        {"owner": "<TUUSUARIO>", "name": "INDICADORES_MACRO"},
        {"owner": "<TUUSUARIO>", "name": "SISTEMA_BANCARIO"},
        {"owner": "<TUUSUARIO>", "name": "TRANSACCIONES"}
      ]
    }'
  );
END;
/
```

## 🧠 Explicación de cada parte

- `profile_name`  
  Es el nombre lógico del AI Profile dentro de la sesión y del esquema.

- `provider`  
  Indica que el servicio de AI que se usará pertenece a OCI.

- `credential_name`  
  Es la credencial que ya creaste previamente en ADB para autenticarte contra OCI.

- `region`  
  Define la región donde se invocará el servicio de AI. En este lab usamos `us-ashburn-1`.

- `model`  
  Es el modelo que se utilizará para interpretar el lenguaje natural.

- `object_list`  
  Lista los objetos del esquema que Select AI puede consultar. Aquí se autorizan las tres tablas del laboratorio.

## 💡 Qué debes entender

Este paso no ejecuta consultas todavía. Solo prepara la configuración para que Select AI sepa:

- dónde consultar,
- con qué credenciales,
- y sobre qué tablas trabajar.

---

# 3️⃣ Validar que el AI Profile quedó bien creado

## 🎯 ¿Qué vamos a hacer?

Vamos a comprobar que el profile sí existe en la sesión actual y que sus atributos quedaron almacenados correctamente.

## 🧾 Validación 1

```sql
SELECT *
FROM USER_CLOUD_AI_PROFILES;
```

## 🧾 Validación 2

```sql
SELECT *
FROM USER_CLOUD_AI_PROFILE_ATTRIBUTES;
```

## 🧠 Explicación de cada consulta

- `USER_CLOUD_AI_PROFILES`  
  Muestra los perfiles de AI creados para tu esquema.

- `USER_CLOUD_AI_PROFILE_ATTRIBUTES`  
  Muestra los parámetros internos del profile, como proveedor, modelo, región y credencial.

## ✅ Resultado esperado

Debes ver:

- el profile `OCIGenAI_<TUUSUARIO>`
- los atributos que configuraste en el paso anterior

👉 Si no aparece, el profile no quedó activo o fue creado en otro esquema/sesión.

---

# 4️⃣ Probar Select AI con preguntas reales

## 🎯 ¿Qué vamos a hacer?

Ahora vamos a usar lenguaje natural para pedirle a Select AI que:

- muestre el SQL que generaría,
- ejecute la consulta,
- o explique el resultado.

## 🧠 Qué hace cada action

- `showsql`  
  Genera y devuelve el SQL, pero no lo ejecuta.

- `runsql`  
  Genera el SQL y lo ejecuta contra las tablas disponibles.

- `narrate`  
  Usa el resultado para responder en lenguaje natural.

## 💡 Importante

En todas las consultas de este bloque se usa:

```text
profile_name => 'OCIGenAI_TUUSUARIO'
```

👉 Sustituye ese valor por el nombre real del profile que creaste, por ejemplo `OCIGenAI_DHERNANDEZ`.

---

## 4.1 Promedio de inflación por año

### ¿Qué vamos a hacer?
Vamos a pedirle a Select AI que interprete una pregunta de análisis macroeconómico sobre la evolución de la inflación.

### a) Mostrar el SQL generado

```sql
SELECT DBMS_CLOUD_AI.GENERATE(
  prompt => '¿Cuál es el promedio de inflación por año?',
  action => 'showsql',
  profile_name => 'OCIGenAI_TUUSUARIO'
) FROM dual;
```

### b) Ejecutar la consulta generada

```sql
SELECT DBMS_CLOUD_AI.GENERATE(
  prompt => '¿Cuál es el promedio de inflación por año?',
  action => 'runsql',
  profile_name => 'OCIGenAI_TUUSUARIO'
) FROM dual;
```

### c) Narrar el resultado

```sql
SELECT DBMS_CLOUD_AI.GENERATE(
  prompt => '¿Cuál es el promedio de inflación por año?',
  action => 'narrate',
  profile_name => 'OCIGenAI_TUUSUARIO'
) FROM dual;
```

---

## 4.2 Banco con mayor cantidad de activos

### ¿Qué vamos a hacer?
Vamos a consultar cuál banco presenta el valor más alto en la columna de activos.

### a) Mostrar el SQL generado

```sql
SELECT DBMS_CLOUD_AI.GENERATE(
  prompt => '¿Qué banco tiene la mayor cantidad de activos?',
  action => 'showsql',
  profile_name => 'OCIGenAI_TUUSUARIO'
) FROM dual;
```

### b) Ejecutar la consulta generada

```sql
SELECT DBMS_CLOUD_AI.GENERATE(
  prompt => '¿Qué banco tiene la mayor cantidad de activos?',
  action => 'runsql',
  profile_name => 'OCIGenAI_TUUSUARIO'
) FROM dual;
```

### c) Narrar el resultado

```sql
SELECT DBMS_CLOUD_AI.GENERATE(
  prompt => '¿Qué banco tiene la mayor cantidad de activos?',
  action => 'narrate',
  profile_name => 'OCIGenAI_TUUSUARIO'
) FROM dual;
```

---

## 4.3 Total de remesas registradas en 2023

### ¿Qué vamos a hacer?
Vamos a sumar las transacciones de remesas correspondientes al año 2023.

### a) Mostrar el SQL generado

```sql
SELECT DBMS_CLOUD_AI.GENERATE(
  prompt => '¿Cuál es el total de remesas registradas en el año 2023?',
  action => 'showsql',
  profile_name => 'OCIGenAI_TUUSUARIO'
) FROM dual;
```

### b) Ejecutar la consulta generada

```sql
SELECT DBMS_CLOUD_AI.GENERATE(
  prompt => '¿Cuál es el total de remesas registradas en el año 2023?',
  action => 'runsql',
  profile_name => 'OCIGenAI_TUUSUARIO'
) FROM dual;
```

### c) Narrar el resultado

```sql
SELECT DBMS_CLOUD_AI.GENERATE(
  prompt => '¿Cuál es el total de remesas registradas en el año 2023?',
  action => 'narrate',
  profile_name => 'OCIGenAI_TUUSUARIO'
) FROM dual;
```

---

## 4.4 Evolución de reservas internacionales

### ¿Qué vamos a hacer?
Vamos a revisar cómo han cambiado las reservas internacionales a lo largo del tiempo.

### a) Mostrar el SQL generado

```sql
SELECT DBMS_CLOUD_AI.GENERATE(
  prompt => '¿Cómo han evolucionado las reservas internacionales a lo largo de los años?',
  action => 'showsql',
  profile_name => 'OCIGenAI_TUUSUARIO'
) FROM dual;
```

### b) Ejecutar la consulta generada

```sql
SELECT DBMS_CLOUD_AI.GENERATE(
  prompt => '¿Cómo han evolucionado las reservas internacionales a lo largo de los años?',
  action => 'runsql',
  profile_name => 'OCIGenAI_TUUSUARIO'
) FROM dual;
```

### c) Narrar el resultado

```sql
SELECT DBMS_CLOUD_AI.GENERATE(
  prompt => '¿Cómo han evolucionado las reservas internacionales a lo largo de los años?',
  action => 'narrate',
  profile_name => 'OCIGenAI_TUUSUARIO'
) FROM dual;
```

---

## 4.5 Diferencia entre depósitos y préstamos por banco

### ¿Qué vamos a hacer?
Vamos a comparar depósitos y préstamos para entender la relación entre ambas métricas por cada banco.

### a) Mostrar el SQL generado

```sql
SELECT DBMS_CLOUD_AI.GENERATE(
  prompt => '¿Cuál es la diferencia entre depósitos y préstamos por banco?',
  action => 'showsql',
  profile_name => 'OCIGenAI_TUUSUARIO'
) FROM dual;
```

### b) Ejecutar la consulta generada

```sql
SELECT DBMS_CLOUD_AI.GENERATE(
  prompt => '¿Cuál es la diferencia entre depósitos y préstamos por banco?',
  action => 'runsql',
  profile_name => 'OCIGenAI_TUUSUARIO'
) FROM dual;
```

### c) Narrar el resultado

```sql
SELECT DBMS_CLOUD_AI.GENERATE(
  prompt => '¿Cuál es la diferencia entre depósitos y préstamos por banco?',
  action => 'narrate',
  profile_name => 'OCIGenAI_TUUSUARIO'
) FROM dual;
```

---

# ✅ Resultado esperado

Al terminar este laboratorio deberías poder:

- Ver el AI Profile creado en tu esquema
- Validar sus atributos
- Ejecutar consultas con Select AI
- Comparar el comportamiento de:
  - `showsql`
  - `runsql`
  - `narrate`

---

# 💡 Recomendación final

Antes de ejecutar las consultas, confirma siempre que:

- el profile existe,
- el nombre del profile coincide exactamente,
- estás conectado con el usuario correcto,
- y las tablas indicadas en `object_list` existen en tu esquema.

---

# 🚀 LAB: Configuración de Oracle APEX con Generative AI

> 📄 Basado en el flujo del documento original (GenAI on APEX)

------------------------------------------------------------------------

## 🎯 Objetivo del Laboratorio

Este laboratorio tiene como objetivo integrar Oracle APEX con los
servicios de **Generative AI en OCI**, permitiendo:

-   🧠 Generación de SQL con lenguaje natural\
-   ⚙️ Configuración de servicios AI dentro del workspace\
-   🏗️ Creación de aplicaciones completas asistidas por IA

------------------------------------------------------------------------

## 🧭 Paso 1: Acceso a Workspace Utilities

<img width="787" height="499" alt="image" src="https://github.com/user-attachments/assets/0bd171ae-580a-4d2d-9a87-0f68e64ca4ea" />


### 🔎 Navegación

`App Builder → Workspace Utilities`

### 💡 ¿Qué está pasando aquí?

Se accede al panel de administración del workspace, donde viven las
configuraciones clave:

-   🔐 Web Credentials (credenciales externas)
-   🤖 Generative AI
-   🔗 Integraciones REST

👉 Este es el punto de entrada para habilitar capacidades AI dentro de
APEX.

------------------------------------------------------------------------

## 🔐 Paso 2: Crear Web Credentials

<img width="1668" height="665" alt="image" src="https://github.com/user-attachments/assets/faecea1b-fe32-4737-a263-564eacb99a00" />

<img width="1678" height="355" alt="image" src="https://github.com/user-attachments/assets/67e901d7-0db3-429c-8926-f2979f22f7fd" />

<img width="581" height="267" alt="image" src="https://github.com/user-attachments/assets/67db5d45-6b49-4489-ab71-985b69960abc" />


### 🛠️ Configuración

Se registran credenciales OCI:

-   🆔 OCID de usuario *(ofuscado)*
-   🏢 OCID del tenancy *(ofuscado)*
-   🔑 Private Key *(ofuscada)*
-   🧾 Fingerprint

### 🧠 ¿Por qué importa?

Estas credenciales permiten que APEX **se autentique contra OCI** y
consuma servicios como:

-   Generative AI\
-   APIs REST\
-   Servicios cloud protegidos

👉 Sin esto, APEX no puede "hablar" con OCI.

------------------------------------------------------------------------

## 🤖 Paso 3: Configurar Generative AI Service

<img width="1673" height="602" alt="image" src="https://github.com/user-attachments/assets/613fa6aa-beab-4d98-ae82-9799113b28e9" />

<img width="583" height="281" alt="image" src="https://github.com/user-attachments/assets/11cbb2c7-fe77-4fe1-b702-a1e390fd18c6" />


### ⚙️ Parámetros clave

-   🧩 Provider: OCI Generative AI\
-   📦 Compartment OCID *(ofuscado)*\
-   🌎 Región (ej: `us-ashburn-1`)\
-   🧠 Modelo (ej: `gpt-4`)\
-   🔗 Endpoint URL\
-   🔐 Credencial creada previamente

### 🧪 Validación

Se ejecuta **Test Connection** → ✔ Conexión exitosa

<img width="587" height="289" alt="image" src="https://github.com/user-attachments/assets/30179fec-1b83-4b6a-98eb-65bbb5ac7467" />


### 💡 ¿Qué hace esto?

Registra el servicio AI dentro de APEX para que pueda ser usado en:

-   SQL Assistant\
-   Generación de aplicaciones\
-   Automatización de tareas

------------------------------------------------------------------------

## 💬 Paso 4: Uso de APEX Assistant en SQL Workshop

<img width="510" height="146" alt="image" src="https://github.com/user-attachments/assets/941cf6a3-e000-4c0a-8777-9b09abe4a032" />

<img width="398" height="158" alt="image" src="https://github.com/user-attachments/assets/d5930a0e-9ad3-42cc-8bac-d68ee44c8818" />


### 🧭 Navegación

`SQL Workshop → SQL Commands`

### ⚡ Acción

Se activa el **APEX Assistant** y se acepta el disclaimer.

<img width="383" height="240" alt="image" src="https://github.com/user-attachments/assets/74f66dfe-f73a-4440-acaf-43ad2eeec031" />


### 🗣️ Ejemplo de Prompt

``` text
Quiero una sentencia SQL que me muestre los indicadores macro
```

### 🤯 Resultado

<img width="774" height="421" alt="image" src="https://github.com/user-attachments/assets/16698905-20a0-4012-9eb2-9b5c663eac60" />

<img width="1919" height="684" alt="image" src="https://github.com/user-attachments/assets/9647a1c6-292b-443c-9be1-4d1bb3d6109e" />

El sistema genera automáticamente una consulta SQL.

### 🧠 ¿Qué significa esto?

Estás usando AI para convertir lenguaje natural en SQL ejecutable.

------------------------------------------------------------------------

## 📊 Paso 5: Ejecución de la consulta

<img width="1911" height="783" alt="image" src="https://github.com/user-attachments/assets/fabda373-8363-4c8d-b0ec-a9acf9352cd4" />


### ▶️ Acción

Se ejecuta la consulta generada.

### 📈 Resultado

Se obtienen datos como:

-   📉 Inflación\
-   💰 PIB\
-   🌍 Reservas internacionales\
-   📊 Tasas de interés

### 💡 Insight

Validación real del uso de AI sobre datos existentes.

------------------------------------------------------------------------

## 🏗️ Paso 6: Crear aplicación con Generative AI

<img width="434" height="413" alt="image" src="https://github.com/user-attachments/assets/648cd178-05de-47fa-9d64-073e676fed7d" />

<img width="1908" height="614" alt="image" src="https://github.com/user-attachments/assets/ed4fe661-8938-4d2e-8f25-433860d6ce77" />

<img width="905" height="685" alt="image" src="https://github.com/user-attachments/assets/b6316db5-372e-44a9-911a-493727800810" />

<img width="1236" height="755" alt="image" src="https://github.com/user-attachments/assets/9cf3bd8f-c064-42d2-9d6e-5bd61495d69c" />


### 🧭 Navegación

`App Builder → Create Application → Create App Using Generative AI`

### 🗣️ Prompt de ejemplo

Quiero una aplicación que permita mostrar la inflación por año. 
Además quiero otra pantalla que me muestre un reporte interactivo para validar los datos de activos, depósitos y préstamos del sistema bancario.
Por último quiero un mantenimiento que muestre todos los datos de las transacciones bancarias.

### 🤖 Resultado

APEX genera automáticamente:

-   Estructura de aplicación\
-   Páginas\
-   Componente

<img width="1682" height="769" alt="image" src="https://github.com/user-attachments/assets/c59343d4-9316-4af4-a215-20a36ce75f00" />
   

------------------------------------------------------------------------

## 🧩 Paso 7: Configuración de la Aplicación

📍 *Referencia: Página 6*

### 🧱 Componentes generados

-   🏦 Vista Anual de Inflación \
-   🔄 Validador de Datos Bancarios \
-   📜 Gestor de Transacciones

### 💡 ¿Qué pasó aquí?

La IA no solo genera lógica, también define UX/UI inicial.

------------------------------------------------------------------------

## ▶️ Paso 8: Ejecución de la Aplicación

### 🔐 Pantalla de Login

<img width="1264" height="831" alt="image" src="https://github.com/user-attachments/assets/397bed70-108e-4de8-beaf-48a69d78ee04" />

Acceso autenticado al sistema

### 🏠 Dashboard

Vista Anual de Inflación

<img width="1292" height="625" alt="image" src="https://github.com/user-attachments/assets/5fec4f99-4204-4934-8199-88a08e5432bc" />


### 🔄 Módulo de Transacciones

Validador de Datos Bancarios

<img width="960" height="274" alt="image" src="https://github.com/user-attachments/assets/8552662e-3d49-49ef-a6ba-bee34e12bef1" />

Gestor de Transacciones

<img width="954" height="287" alt="image" src="https://github.com/user-attachments/assets/79847251-5b48-4dd1-af96-0a9f44fc64d1" />


### 🎯 Resultado final

Aplicación completamente funcional creada con ayuda de AI.

------------------------------------------------------------------------

## 🔒 Consideraciones de Seguridad

-   ❌ No exponer OCIDs reales\
-   ❌ No publicar llaves privadas\
-   ✅ Usar variables de entorno / vaults

------------------------------------------------------------------------

## 🧠 Conclusión

Este laboratorio demuestra cómo:

-   🔗 Integrar OCI + APEX + Generative AI\
-   💬 Generar SQL con lenguaje natural\
-   🏗️ Crear aplicaciones completas automáticamente\
-   ⚡ Acelerar el desarrollo low-code

------------------------------------------------------------------------
