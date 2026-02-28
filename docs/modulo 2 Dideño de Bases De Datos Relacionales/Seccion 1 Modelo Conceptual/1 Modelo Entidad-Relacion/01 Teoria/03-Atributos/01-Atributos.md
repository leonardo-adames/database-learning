<div align="center">
    <kbd>
        <h1><b>CURSO DE BASES DE DATOS- MÓDULO 2<br>DISEÑO & MODELADO DE BASES DE DATOS</b></h1>
        <img width="2064" height="350" alt="Image" src="Ejemplo Visual/los atributos.png" />
    <h2>2.2  LOS ATRIBUTOS</h2>
    </kbd>
</div>

### **¿Qué es un atributo?**

En un Diagrama **`Modelo Entidad-Relación`**, un **`atributo`** es una **`característica`** o **`propiedad`** que describe a una **`entidad`** (*un objeto del mundo real, como un `Estudiante` o un `Producto`*), y se representa visualmente como un óvalo unido a la entidad. Los atributos almacenan detalles específicos como *`Nombre`, `DNI`, `Email`*, y existen tipos como los clave *`identificadores`,`únicos`, `subrayados`*, etc.

<br>

### **PROPOSITO DE LOS ATRIBUTOS**

Los atributos tienen varios propósitos fundamentales en el diseño de bases de datos:

1.  **Describir Entidades:** Permiten detallar las características de cada entidad. Por ejemplo, una entidad `Estudiante` puede tener atributos como `ID_Estudiante`, `Nombre`, `Apellido`, `Fecha_Nacimiento`, `Dirección`, etc.<br>

2.  **Almacenar Información:** Son los contenedores donde se guarda la información específica de cada instancia de una entidad.<br>

3.  **Identificación Única:** Algunos atributos, como las claves primarias, sirven para identificar de forma única a cada instancia de una entidad, lo cual es crucial para la integridad y recuperación de datos.<br>

4.  **Establecer Relaciones:** A través de claves foráneas (que son atributos), se establecen vínculos entre diferentes entidades, permitiendo la conexión y consulta de datos relacionados.<br>

5.  **Validación y Restricciones:** Los atributos pueden tener restricciones (como tipos de datos, rangos de valores, obligatoriedad) que aseguran la calidad y consistencia de los datos.<br>

6.  **Organización y Estructura:** Contribuyen a organizar la información de manera lógica y estructurada dentro de la base de datos.   

---

<br>
<br>

---

<div align="center">
    <kbd>
        <h1><b>CURSO DE BASES DE DATOS- MÓDULO 2<br>TIPOS DE ATRIBUTOS</b></h1>
        <img width="2064" height="350" alt="Image" src="Ejemplo Visual/tipos de atributos.png" />
    </kbd>
</div>

<br>

## **ATRIBUTOS SIMPLES**

Son aquellos que no se pueden dividir en partes más pequeñas con significado propio. Representan un valor único e indivisible para una entidad.

<br>

### **Características:**

*   **Indivisibles:** No se pueden descomponer en otros atributos.
*   **Valor Único:** Cada instancia de la entidad tiene un solo valor para este atributo.

### **Ejemplos:**

*   `ID_Cliente`: Un número de identificación único para cada cliente.
*   `Fecha_Nacimiento`: La fecha de nacimiento de una persona.

**Los atributos simples se representan por un Obalo y el nombre de la propiedad de dicho atributo dentro del Obalo subrayado con una línea discontinua para identificar que es un valor único**.

<div align="center">

<img src="Ejemplo Visual/1.3.2-atributos.jpg" width="100%"/>
</div>

---
<br>

---

## **ATRIBUTOS COMPUESTOS**

En el Modelo Entidad-Relación **`MER`**, un atributo compuesto es una propiedad de una entidad que puede ser desglosada en componentes más pequeños y significativos, como una "Dirección" que se divide en `Calle`, `Número`, `Ciudad`, `Código Postal`etc., o un `Nombre Completo` que se separa en `Nombre`, `Primer Apellido` y `Segundo Apellido`. Estos atributos compuestos ayudan a organizar mejor los datos, permitiendo almacenar y consultar sus partes atómicas de forma individual, y se representan en el diagrama MER con un óvalo conectado a óvalos más pequeños que representan sus sub-atributos.

<br>

### **CARASTERISTICAS**

**Descomposición:**

    Se puede dividir en atributos más simples (atómicos).

**Organización:**

    Mejora la estructura del modelo, facilitando el diseño de la base de datos.

**Ejemplos:**

Dirección: `Calle`, `Número`, `Ciudad, `, `Código Postal`º.

Nombre: `Nombre`, `Primer Apellido`, `Segundo Apellido`.

Fecha: `Día`, `Mes`, `Año`.

<br>

### **Representación en el Diagrama MER**

**El atributo compuesto** se dibuja como un `óvalo` conectado a `otros óvalos` **sus componentes.**

**Los óvalos** de los componentes ej: **`Calle`, `Número`, `Ciudad`, `Código Postal`** se conectan al **óvalo** del **atributo compuesto** ej: `Dirección`.**

<div align="center">

<img src="Ejemplo Visual/1.3.4-atributos-compuesto.jpg" width="100%"/>
</div>

<br>

### **Utilidad**

En la implementación de la base de datos, se crean columnas separadas para cada componente atómico (ej: **`ciudad`, `calle`**), no para el atributo compuesto completo (ej: **`direccion`**).

Permite realizar consultas más específicas (ej. buscar todos los clientes de `**Madrid**`).

---
<br>

---

## **ATRIBUTOS MULTIVALUADOS**

En un **Modelo Entidad-Relación (MER)**, los **atributos multivaluados** son aquellos que pueden tener múltiples valores para una misma instancia **(ocurrencia)** de una entidad, a diferencia de los monovaluados que tienen un solo valor (ej. DNI). Se representan con un doble óvalo en el diagrama y, comúnmente, un asterisco (o doble óvalo) indica que un atributo, como un teléfono o un correo electrónico, puede tener varias entradas para una sola persona.

### Características Clave:

**Múltiples Valores:**

* Una entidad puede tener varios valores para ese atributo. Por ejemplo, una persona puede tener varios números de teléfono o direcciones de correo electrónico.

### **Representación Gráfica:**

* Se dibujan con un óvalo doble o un óvalo con un asterisco al lado, conectado a la entidad.

**Ejemplos:**

* **Teléfonos** (para un Cliente).

* **Idiomas** (para un Empleado).

* **Títulos** (para un Libro).

<div align="center">

<img src="Ejemplo Visual/1.3.6-atributos-multivaluados.jpg" width="100%"/>
</div>

<br>

### **Implementación en Bases de Datos (Modelo Relacional):**

    No se recomienda guardar múltiples valores en una sola celda (columna) de una tabla, ya que dificulta las consultas.
    Se suelen convertir en una nueva tabla, donde la clave primaria de la tabla original se usa como clave foránea, creando una **relación uno-a-muchos** para almacenar cada valor por separado.

**En resumen, son una forma de modelar datos donde una propiedad de una entidad no es única, permitiendo flexibilidad en el diseño conceptual de la base de datos.**

---
<br>

---

## **ATRIBUTOS CALCULADOS / DERIVADOS**

Por contra, los atributos derivados son aquellos que son obtenidos a partir del valor de uno o varios atributos existentes en la misma o en otras entidades. Se representan mediante círculos discontinuos.

Este tipo de atributo no están presente de forma física dentro del **`MER`** de una base de datos, pero pueden derivarse fácilmente de otros atributos. Se calculan en tiempo de ejecución, por lo que sus valores varían.

### **Ejemplo:**

Tomemos como ejemplo una entidad de **EMPLEADO** únicamente. Supongamos que tiene atributos como  *`DNI`, `Nombre`, `Apellido`, `Puesto` y `Fecha de Nacimiento`*, como se muestra en la siguiente figura.

<div align="center">

<img src="Ejemplo Visual/1.3.8-atributos-calculados.jpg" width="100%"/>
</div>

Si tomamos otro atributo, la **edad**, podemos derivarlo del atributo **fecha de nacimiento**. La **edad** no necesita estar presente Fisicamente en la base de datos. Los **atributos derivados se representan con la elipse punteada o descontinua**, como se muestra en la figura.

<br>

### **Características del atributo derivado**

    1- No se almacenan físicamente, se calculan utilizando el otro atributo, lo que resulta en un costo cero de almacenamiento

    2- Dependen de los demás atributos de la base de datos.

    3- Varían según los cambios en los atributos de los que dependen. Por lo tanto, no es necesario realizar cambios explícitos en los atributos derivados.

<br>

### **Desventajas del atributo derivado**

    1- El cálculo aumenta cada vez que tenemos que realizar un conjunto de cálculos para obtener los valores del atributo derivado

    2- Aumento del tiempo para realizar acciones sencillas ya que se necesitan cálculos.

    3- La complejidad del lenguaje de consulta "AUMENTA" con la implementación simple con el atributo derivado, ya que tenemos que calcular el atributo derivado cada vez.

---
<br>

---

## **RESTRIGCIONES EN LOS ATRIBUTOS**

Las `restricciones` en los **atributos** son `reglas` que se aplican a los valores que pueden tomar los atributos de una entidad con las cuales se determinan que `valores se pueden almacenar` en cada atributo de una `entidad o relación`. Estas restricciones son fundamentales para mantener Y la `integridad`, `consistencia` y `validez` de los datos en una base de datos.

<br>

## **Tipos de Restricciones Comunes:**

### 1️⃣ **Restricción de Dominio (Domain Constraint):**

**¿Qué es?**

Es el conjunto de valores válidos que puede tomar un atributo.

**Cómo se representa en la notación MER**

El `dominio` no tiene un símbolo gráfico específico estándar, pero se indica de estas formas:

    Anotación textual junto al atributo

    Especificación entre paréntesis

    Documentación adicional del modelo

**Ejemplo conceptual:**

<div align="center">

<img src="Ejemplo Visual/restrigcion0.png" width="100%"/>
</div>
 
---
<br>

---

### 2️⃣ **Atributo obligatorio u opcional (Nulabilidad):**

**¿Qué significa?**

Indica si el atributo debe tener valor en todas las entidades.

**Representación en MER**

En la notación clásica:

    No existe un símbolo universal obligatorio.

Puede indicarse mediante:

    Un marcador especial

    Una anotación como (obligatorio)

    Documentación externa

Algunas variantes modernas usan:

    Línea sólida (obligatorio)

    Línea discontinua (opcional)

Pero esto depende del estándar gráfico adoptado.

**Ejemplo Conceptual**

<div align="center">

<img src="Ejemplo Visual/restrigcion1.png" width="100%"/>
</div>

---
<br>

---
### 3️  **Restricción de Unicidad:**

**¿Qué significa?**

Indica que el atributo no puede repetiB=rse entre instancias de la entidad.

**Representación en MER**

Cuando el atributo es identificador `clave`, se representa:

Subrayando el nombre del atributo

<div align="center">

<img src="Ejemplo Visual/1.3.2-atributos.jpg" width="100%"/>
</div>

El subrayado indica:

    Unicidad

    No ambigüedad

    Función identificadora

Si hay más de un atributo identificador, se subrayan todos (clave compuesta).

---
<br>

---

### 4️⃣ **Clave primaria (Identificador)**

**Qué es**

Atributo (o conjunto) que identifica de manera única cada entidad.

**Representación gráfica**

Se subraya el atributo.

Si es compuesta → se subrayan todos los atributos participantes.

Ejemplo:

<div align="center">

<img src="Ejemplo Visual/restrigcion2.png" width="100%"/>
</div>

---
<br>

---

### **Importancia de las Restricciones:**

Las restricciones son vitales para:

*   **Integridad de Datos:** Aseguran que los datos sean precisos y consistentes.

*   **Calidad de Datos:** Previenen la entrada de datos erróneos o inválidos.

*   **Fiabilidad del Sistema:** Ayudan a mantener la base de datos en un estado coherente y funcional.

*   **Lógica de Negocio:** Reflejan las reglas y políticas del mundo real en el modelo de datos.

*   **Seguridad:** Contribuyen a proteger los datos al evitar manipulaciones no autorizadas o incorrectas.

*   **Rendimiento:** Al asegurar la validez de los datos, se optimizan las operaciones y consultas.
