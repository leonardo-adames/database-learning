<div align="center">
    <kbd>
        <h1><b>CURSO DE BASES DE DATOS- MÓDULO 2<br>DISEÑO & MODELADO DE BASES DE DATOS</b></h1>
        <img width="2064" height="400" alt="Image" src="https://github.com/user-attachments/assets/11953be5-c26f-4448-9949-77fd399f63ed" />
    </kbd>
    <br>
    <br>
    <h2>2.2  LAS ENTIDADES</h2>
</div>

### **¿QUÉ ES UAN ENTIDAD?**

 Son elementos distinguibles del universo de datos que forman el sistema de información, ya sean tangibles `un coche` o abstractos `una cuenta bancaria` y se representan gráficamente con `rectángulos`, siendo el pilar fundamental para diseñar estructuras de datos funcionales y optimizadas, identificando sus propiedades `atributos` y cómo se conectan `relaciones`.

### **Ejemplo Práctico:**

<div align="center">

<img src="Ej Visual/1.2.1-entidades.jpg" width="100%"/>
</div>

### **Propósito:**

Constituyen las futuras `tablas` en la base de datos, almacenando registros o instancias de esos objetos, como:

* En una biblioteca: `Libro`, `Usuario`, `Préstamo`. 

* En una tienda: `Cliente`, `Pedido`, `Artículo`.

<br>

---

<br>
<br>

---

<div align="center">
    <kbd>
        <h1><b>CURSO DE BASES DE DATOS- MÓDULO 2<br>DISEÑO & MODELADO DE BASES DE DATOS</b></h1>
        <img width="2064" height="512" alt="Image" src="https://github.com/user-attachments/assets/079d9314-bea0-4cef-8523-41ce493743c2" />
    <h2>2.2  LAS ENTIDADES DEBILES</h2>
    </kbd>
</div>

**¿Qué es una Entidad Debil?**

Una **`entidad débil`** en el **`Modelo Entidad-Relación (MER)`** es aquella cuya `existencia` y/o `identificación` depende de otra entidad, llamada e`ntidad fuerte`, porque no tiene una `clave primaria` propia y necesita la `clave` de la entidad fuerte más sus propios atributos para formar una clave compuesta única, representándose con un doble rectángulo en los diagramas ER. Ejemplos comunes son `Detalle de Pedido` depende de `Pedido` o `Sección` depende una `revista`.

<br>

## **Características clave**

* **Ésta se puede manifestar en dos tipos:**

### **Identificaión**

    Carece de clave primaria propia; se identifica por una clave compuesta formada por sus atributos y la clave primaria de la entidad fuerte, es decir, que su clave depende obligatoriamente de la clave de la Entidad fuerte a la que esta relacionada. **SI NECESITA A LA ENTIDAD FUERTE PARA IDENTIFICARE

### **Existencia O Dependencia**

    No puede existir sin la entidad fuerte a la que está relacionada (dependencia existencial), y su clave depende de la suya propia y de la clave de la entidad fuerte a la que esta relacionada. **NO NECESITA DE LA ENTIDAD DEBIL PARA IDENTIFICARSE, SOLO PARA EXISTIR**

<br>

## **Otras Características**

### **Representación**:

Se dibuja con un rectángulo de doble línea en diagramas MER.

### **Relación:** 

La relación con la entidad fuerte se representa con un rombo de doble línea y la cardinalidad suele ser **1:N** `uno a muchos` del lado débil.

**EJEMPLOS DE UNA ENTIDAD DE TIPO ESXISTENCIAL O DEPENDIENTE Y UNA ENTIDAD DEBIL IDENTIFICATIVA**

<div align="center">

<img src="Ej Visual/1.2.2-entidades-débiles.jpg" width="100%"/>
</div>
