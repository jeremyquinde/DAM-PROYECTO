# 🌾 SiembraPro – Proyecto DAM 

---

## 📚 Tabla de Contenidos

- [🛠 Especificaciones del Proyecto](#-especificaciones-del-proyecto)
- [📦 Estructura del Proyecto](#-estructura-del-proyecto)
- [📂 Detalle de Archivos por Módulo](#-detalle-de-archivos-por-módulo)
- [🧠 Estructura del Núcleo Compartido (`core/`)](#-estructura-del-núcleo-compartido-core)
- [🚀 Uso del Repositorio](#-uso-del-repositorio)
- [🔁 Flujo de Trabajo en GitHub](#-flujo-de-trabajo-en-github)

---

## 🛠 Especificaciones del Proyecto

- **Lenguaje:** Java
- **JDK (link descarga):** [Java 17](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html)
- **Min SDK:** 26
- **Base de datos:** ???
- **Patrones opcionales:** ViewModel, Repositorios

---

## 📦 Estructura del Proyecto

```bash
SiembraPro/
├── app/
│   └── src/main/java/com/grupo12/siembrapro/
│       ├── MainActivity.java
│       ├── modulos/
│       │   ├── insumos/
│       │   │   ├── Insumo.java
│       │   │   ├── InsumoActivity.java
│       │   │   ├── InsumoRepository.java
│       │   │   ├── InsumoViewModel.java (opcional)
│       │   └── ... otros módulos
│       └── core/
│           ├── database/
│           ├── model/
│           └── utils/
└── res/
```

---

## 📂 Detalle de Archivos por Módulo


- `<Modulo>.java`

Representa los datos del módulo. Aquí se definen las clases con los atributos que el módulo necesita, por ejemplo: nombre, fecha, estado, etc.
    ➤  Sirve como un "molde" de los datos que se van a manejar en ese módulo.
    ➤  Si el modelo se comparte con otros módulos, va en core/model/.

- `<Modulo>Activity.java`

Es la pantalla principal del módulo (interfaz gráfica). Aquí se manejan los eventos del usuario, como hacer clic, escribir, navegar, etc.
    ➤  Es la parte visual y de interacción del módulo.

- `<Modulo>Repository.java`

Se encarga de acceder a la base de datos. Aquí van las consultas (SELECT, INSERT, UPDATE, DELETE) específicas del módulo.
    ➤ Sirve como puente entre los datos de la base y el resto de la app.
  
- `<Modulo>ViewModel.java`

Guarda y administra los datos que se muestran en la interfaz. También contiene lógica para preparar esos datos.
    ➤ Ayuda a separar la lógica de la vista, para que el código sea más limpio
---

## 🧠 Estructura del Núcleo Compartido (`core/`)

Contiene lo que es común y útil para todos los módulos, así no se repite el código.

- `core/database/DbConfig.java`
Configura cómo conectarse a la base de datos.

- `core/model/`
Guarda los modelos de datos que son usados en varios módulos, como Usuario.java, Rol.java, etc. Para evitar duplicar modelos.

- `core/utils/`
Aquí van funciones auxiliares que pueden necesitar varios módulos, como validaciones.

---

## 🚀 Uso del Repositorio

Link del repositorio oficial:  
🔗 [https://github.com/jeremyquinde/DAM-PROYECTO.git](https://github.com/jeremyquinde/DAM-PROYECTO.git)

### Rama deberes
La rama deberes contiene un proyecto que servira solo para realizar los deberes que se manden y evitar que estos interfieran con el proyecto principal.
- `No usar el proyecto de esta rama para el desarrollo de sus modulos xddd`

Link de la rama:
https://github.com/jeremyquinde/DAM-PROYECTO/tree/deberes

### Clonar el proyecto

```bash
git clone https://github.com/jeremyquinde/DAM-PROYECTO.git
cd DAM-PROYECTO
```

---

## 🔁 Flujo de Trabajo en GitHub

1. **Crea una rama para tu módulo**

```bash
git checkout -b modulo-nombre_del_modulo
```

Ejemplos:
- `modulo-insumos`
- `modulo-parcelas`

2. **Trabaja solo en tu carpeta de módulo.** No modifiques otros archivos ni módulos.

3. **Guarda y sube tu progreso**

```bash
git add .
git commit -m "Avance módulo insumos"
git push origin modulo-insumos
```

4. **Solicita Pull Request**  
   Cuando termines, crea un _pull request_ desde GitHub para revisar el módulo y se integre al repositorio principal.
