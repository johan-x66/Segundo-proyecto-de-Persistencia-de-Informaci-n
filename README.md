# 💊 POCMedicamento V3.1

## 📌 Descripción del Proyecto

**POCMedicamento V3.1** es una aplicación desarrollada en Java que permite gestionar información relacionada con medicamentos y farmacias. El sistema incluye funcionalidades para registrar, buscar y actualizar datos, integrando una interfaz gráfica (GUI) con una capa backend y conexión a base de datos.

Este proyecto sigue una estructura modular basada en separación de responsabilidades:

* **Frontend (GUI)**: Interfaces gráficas para interacción con el usuario.
* **Backend**: Lógica de negocio para manejo de medicamentos y farmacias.
* **Data**: Conexión a base de datos y archivos de apoyo.

---

## 🧱 Estructura del Proyecto

```
POCMedicamentoV3.1/
│
├── data/
│   ├── farmacia.txt
│   └── registros.txt
│
├── src/main/java/
│   ├── Backend/
│   │   ├── ClasesFarmacias/
│   │   └── ClasesMedicamento/
│   │
│   ├── Frontend/
│   │   ├── Interfaces gráficas (GUI)
│   │
│   └── com/mycompany/pocmedicamento/
│       ├── Main (POCMedicamento.java)
│       └── data/DatabaseConnect.java
│
├── pom.xml
└── Script crear tablas.txt
```

---

## ⚙️ Tecnologías Utilizadas

* **Java**
* **Maven** (gestión de dependencias)
* **Swing** (interfaces gráficas)
* **JDBC** (conexión a base de datos)

---

## 🚀 Funcionalidades

### 🏥 Gestión de Farmacias

* Crear farmacias
* Buscar farmacias
* Actualizar información (incluyendo actualización parcial de valores)

### 💊 Gestión de Medicamentos

* Registrar medicamentos
* Asociar medicamentos a farmacias
* Consultar información de medicamentos

### 🔍 Búsquedas

* Búsqueda general
* Búsqueda específica por farmacia

---

## 🖥️ Ejecución del Proyecto

### Requisitos

* Java JDK 8 o superior
* Maven

### Pasos

1. Clonar o descomprimir el proyecto
2. Abrir el proyecto en tu IDE (recomendado: NetBeans o IntelliJ)
3. Compilar con Maven:

```bash
mvn clean install
```

4. Ejecutar la clase principal:

```bash
com.mycompany.pocmedicamento.POCMedicamento
```

---

## 🗄️ Base de Datos

El proyecto incluye un archivo para la creación de tablas:

```
CREATE TABLE FARMACIA (
   NIT NUMBER(10) PRIMARY KEY,
   RAZON_SOCIAL VARCHAR2(255),
   REPRESENTANTE_LEGAL VARCHAR2(255),
   DIRECCION VARCHAR2(255),
   ESTADO VARCHAR2(2)
);



CREATE TABLE MEDICAMENTO (
   ID NUMBER(22) PRIMARY KEY,
   NOMBRE VARCHAR2(255),
   GRAMAJE NUMBER(10,2),
   PRECIO_UNITARIO NUMBER(19,2),
   ESTADO VARCHAR(2),
   NITFARMACIA NUMBER(10),
   FOREIGN KEY (NITFARMACIA) REFERENCES FARMACIA(NIT)
);
```

La conexión a la base de datos se gestiona desde:

```
DatabaseConnect.java
```

Asegúrate de configurar correctamente:

* URL de conexión
* Usuario
* Contraseña

---

## 📂 Archivos de Datos

El sistema también utiliza archivos planos:

* `farmacia.txt`
* `registros.txt`

Estos pueden servir como respaldo o entrada de datos.

---

## 🧩 Arquitectura

El sistema sigue una estructura tipo:

* **MVC simplificado**

  * Modelo: Clases `Farmacia`, `Medicamento`
  * Vista: Interfaces gráficas (GUI)
  * Controlador: Clases de funciones (`FuncionesFarmacia`, `FuncionesMedicamento`)

---

## 📄 Licencia

Uso educativo y demostrativo.
