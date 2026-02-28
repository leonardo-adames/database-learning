<div align="center">
    <kbd>
        <h1><b>CURSO DE BASES DE DATOS- MÓDULO 2<br>DISEÑO & MODELADO DE BASES DE DATOS</b></h1>
        <img src="normalizacion.png" alt="Normalización" width="100%" />
    </kbd>
    <br>
    <br>
    <h2>4 NORMALIZACIÓN DE BASES DE DATOS</h2>
</div>

<br>

**La normalización de bases de datos** es un proceso que se utiliza para organizar y optimizar la estructura de una base de datos para asegurar su integridad, evitar la redundancia y mejorar el rendimiento. La normalización consiste en la división de las entidades en varias entidades más pequeñas y relacionarlas mediante llaves foráneas.

<br>

**La normalización** se realiza a través de varios niveles o formas, cada uno de los cuales representa un grado de descomposición de la entidad original. Los tres niveles más comunes de normalización son la Primera Forma Normal **(1FN)**, la Segunda Forma Normal **(2FN)** y la Tercera Forma Normal **(3FN)**, aunque existen otros 2 niveles.

<br>

**El objetivo de la normalización** es reducir la redundancia y garantizar la integridad de los datos al asegurar que cada dato solo se almacene en un solo lugar y que los datos sean consistentes y coherentes. La normalización también ayuda a mejorar el rendimiento de la base de datos, ya que reduce el tamaño y la complejidad de las entidades, lo que facilita la indexación y la búsqueda de información.

<br>

**Es importante** tener en cuenta que la **normalización** puede tener un impacto en el rendimiento de la aplicación, ya que puede requerir una mayor cantidad de consultas y una complejidad adicional para recuperar y manipular datos. Por lo tanto, es importante encontrar un equilibrio entre la normalización y la eficiencia en el diseño de la base de datos.

<br>
<br>

## **Formas Normales**
Las formas normales son estándares para la organización y modelamiento de datos en una base de datos relacional. En total existen 5 formas normales.

<br>

* **Primera Forma Normal **`1FN`**: Cada atributo de una entidad debe contener solo valores atómicos, es decir, valores indivisibles que no pueden ser divididos en atributos más pequeños.

* **Segunda Forma Normal **`2FN`**: Además de cumplir con la 1FN, cada atributo que no dependiente funcionalmente de la llave principal debe estar en una entidad separada.

* **Tercera Forma Normal **`3FN`**: Además de cumplir con la 2FN, todas las dependencias funcionales deben ser eliminadas, es decir, no deben existir dependencias funcionales transitorias.

* **Cuarta Forma Normal **`4FN`**: También llamada de Forma Normal de **Boyce-Codd (FNBC)**, es una forma más restrictiva que la **3FN**, donde se garantiza que no existan dependencias funcionales parciales o transitivas en la entidad.

* **Quinta Forma Normal **`5FN`**: También conocida como Forma Normal de **Domino-Clave (FNDC)**, en ella se debe garantizar que no haya dependencias múltiples de conjuntos en las entidades.

<br>

Al aplicar las formas normales a un modelo de base de datos, se puede asegurar que los datos sean consistentes, que no haya redundancia y que sea fácil de mantener y escalar.

Sin embargo, también es importante tener en cuenta que la aplicación de formas normales más rigurosas puede resultar en una estructura de base de datos más compleja y menos eficiente en términos de rendimiento. Por lo tanto, es importante encontrar un equilibrio entre la integridad de los datos y la eficiencia en el diseño de un modelo de base de datos.

<br>

* **Primera Forma Normal**: En la `1FN`, cada columna de una tabla debe contener únicamente valores atómicos, es decir, valores simples que no pueden ser divididos en partes más pequeñas.

* **Segunda Forma Normal**: La `2FN` requiere que cada columna no dependiente funcionalmente de la clave primaria de una tabla sea movida a una tabla separada. Esto significa que cada tabla debe representar un solo hecho o concepto.

* **Tercera Forma Normal**: La `3FN` requiere que todas las dependencias funcionales sean removidas de la tabla, es decir, que no haya redundancia de información.

* **Forma Normal de Boyce-Codd**: La `FNBC` es una forma normal más rigurosa que la anteriores y requiere que cada dependencia funcional sea una clave candidata única.

* **Forma Normal de Dominio-Clave**: Esta forma normal `FNDC` es una extensiones de la `FNBC` y se utiliza para asegurar la integridad de los datos en modelos de datos más complejos. No debe haber dependencias funcionales múltiples, es decir, una dependencia funcional en la que varios atributos dependen de una clave externa.

<br>
<br>

## **Normalizando una base de datos**

Veamos un ejemplo de normalización de base de datos.

Tenemos una entidad desnormalizada de "Ventas" de una tienda con la siguiente información:

Puedes normalizarme el siguiente modelo de datos

<br>

<div style="display: flex; justify-content: center; margin-top: 20px;">
  <table border="1" cellpadding="8" cellspacing="0">
    <thead>
      <tr>
        <th><kbd>Venta</kbd></th>
        <th><kbd>Fecha</kbd></th>
        <th><kbd>Cliente</kbd></th>
        <th><kbd>Correo</kbd></th>
        <th><kbd>Teléfono</kbd></th>
        <th><kbd>Dirección</kbd></th>
        <th><kbd>Ciudad</kbd></th>
        <th><kbd>País</kbd></th>
        <th><kbd>Producto</kbd></th>
        <th><kbd>Precio</kbd></th>
        <th><kbd>Cantidad</kbd></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><kbd>1</kbd></td>
        <td><kbd>01/01</kbd></td>
        <td><kbd>Juan Perez</kbd></td>
        <td><kbd><a href="mailto:juan.perez@gmail.com">juan.perez@gmail.com</a></kbd></td>
        <td><kbd>5512345678</kbd></td>
        <td><kbd>Calle 1 No. 58-1 CP 03100</kbd></td>
        <td><kbd>CDMX</kbd></td>
        <td><kbd>México</kbd></td>
        <td><kbd>Laptop</kbd></td>
        <td><kbd>25,000.00</kbd></td>
        <td><kbd>2</kbd></td>
      </tr>
      <tr>
        <td><kbd>2</kbd></td>
        <td><kbd>02/01</kbd></td>
        <td><kbd>Pedro Gomez</kbd></td>
        <td><kbd><a href="mailto:pedro.gomez@gmail.com">pedro.gomez@gmail.com</a></kbd></td>
        <td><kbd>3387654321</kbd></td>
        <td><kbd>Calle 2 No. 85-6 CP 44100</kbd></td>
        <td><kbd>Guadalajara</kbd></td>
        <td><kbd>México</kbd></td>
        <td><kbd>Celular</kbd></td>
        <td><kbd>12,000.00</kbd></td>
        <td><kbd>3</kbd></td>
      </tr>
      <tr>
        <td><kbd>3</kbd></td>
        <td><kbd>03/01</kbd></td>
        <td><kbd>Ana Silva</kbd></td>
        <td><kbd><a href="mailto:ana.silva@gmail.com">ana.silva@gmail.com</a></kbd></td>
        <td><kbd>8109128734</kbd></td>
        <td><kbd>Calle 3 No. 33-3 CP 64000</kbd></td>
        <td><kbd>Monterrey</kbd></td>
        <td><kbd>México</kbd></td>
        <td><kbd>Micrófono</kbd></td>
        <td><kbd>2,500.00</kbd></td>
        <td><kbd>1</kbd></td>
      </tr>
      <tr>
        <td><kbd>4</kbd></td>
        <td><kbd>04/01</kbd></td>
        <td><kbd>Ana Silva</kbd></td>
        <td><kbd><a href="mailto:ana.silva@gmail.com">ana.silva@gmail.com</a></kbd></td>
        <td><kbd>8109128734</kbd></td>
        <td><kbd>Calle 3 No. 33-3 CP 64000</kbd></td>
        <td><kbd>Monterrey</kbd></td>
        <td><kbd>México</kbd></td>
        <td><kbd>Laptop</kbd></td>
        <td><kbd>25,000.00</kbd></td>
        <td><kbd>1</kbd></td>
      </tr>
      <tr>
        <td><kbd>5</kbd></td>
        <td><kbd>05/01</kbd></td>
        <td><kbd>Juan Perez</kbd></td>
        <td><kbd><a href="mailto:juan.perez@gmail.com">juan.perez@gmail.com</a></kbd></td>
        <td><kbd>5512345678</kbd></td>
        <td><kbd>Calle 4 45-3 CP 03920</kbd></td>
        <td><kbd>CDMX</kbd></td>
        <td><kbd>México</kbd></td>
        <td><kbd>Micrófono</kbd></td>
        <td><kbd>2,500.00</kbd></td>
        <td><kbd>3</kbd></td>
      </tr>
    </tbody>
  </table>
</div>

<br>
<br>

**La primera forma normal** busca tener valores atómicos, es decir datos simples que no puedan ser divididos en parte más pequeñas, por lo que en el modelo anterior podríamos atomizar el nombre del cliente y su dirección quedando de la siguiente forma:

<br>

<div style="display: flex; justify-content: center; margin-top: 20px;">
  <table border="1" cellpadding="8" cellspacing="0">
    <thead>
      <tr>
        <th><kbd>Venta</kbd></th>
        <th><kbd>Fecha</kbd></th>
        <th><kbd>Nombre</kbd></th>
        <th><kbd>Apellido</kbd></th>
        <th><kbd>Correo</kbd></th>
        <th><kbd>Teléfono</kbd></th>
        <th><kbd>Calle</kbd></th>
        <th><kbd>Número</kbd></th>
        <th><kbd>CP</kbd></th>
        <th><kbd>Ciudad</kbd></th>
        <th><kbd>País</kbd></th>
        <th><kbd>Producto</kbd></th>
        <th><kbd>Precio</kbd></th>
        <th><kbd>Cantidad</kbd></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><kbd>1</kbd></td>
        <td><kbd>01/01</kbd></td>
        <td><kbd>Juan</kbd></td>
        <td><kbd>Perez</kbd></td>
        <td><kbd><a href="mailto:juan.perez@gmail.com">juan.perez@gmail.com</a></kbd></td>
        <td><kbd>5512345678</kbd></td>
        <td><kbd>Calle 1</kbd></td>
        <td><kbd>58-1</kbd></td>
        <td><kbd>03100</kbd></td>
        <td><kbd>CDMX</kbd></td>
        <td><kbd>México</kbd></td>
        <td><kbd>Laptop</kbd></td>
        <td><kbd>25,000.00</kbd></td>
        <td><kbd>2</kbd></td>
      </tr>
      <tr>
        <td><kbd>2</kbd></td>
        <td><kbd>02/01</kbd></td>
        <td><kbd>Pedro</kbd></td>
        <td><kbd>Gomez</kbd></td>
        <td><kbd><a href="mailto:pedro.gomez@gmail.com">pedro.gomez@gmail.com</a></kbd></td>
        <td><kbd>3387654321</kbd></td>
        <td><kbd>Calle 2</kbd></td>
        <td><kbd>85-6</kbd></td>
        <td><kbd>44100</kbd></td>
        <td><kbd>Guadalajara</kbd></td>
        <td><kbd>México</kbd></td>
        <td><kbd>Celular</kbd></td>
        <td><kbd>12,000.00</kbd></td>
        <td><kbd>3</kbd></td>
      </tr>
      <tr>
        <td><kbd>3</kbd></td>
        <td><kbd>03/01</kbd></td>
        <td><kbd>Ana</kbd></td>
        <td><kbd>Silva</kbd></td>
        <td><kbd><a href="mailto:ana.silva@gmail.com">ana.silva@gmail.com</a></kbd></td>
        <td><kbd>8109128734</kbd></td>
        <td><kbd>Calle 3</kbd></td>
        <td><kbd>33-3</kbd></td>
        <td><kbd>64000</kbd></td>
        <td><kbd>Monterrey</kbd></td>
        <td><kbd>México</kbd></td>
        <td><kbd>Micrófono</kbd></td>
        <td><kbd>2,500.00</kbd></td>
        <td><kbd>1</kbd></td>
      </tr>
      <tr>
        <td><kbd>4</kbd></td>
        <td><kbd>04/01</kbd></td>
        <td><kbd>Ana</kbd></td>
        <td><kbd>Silva</kbd></td>
        <td><kbd><a href="mailto:ana.silva@gmail.com">ana.silva@gmail.com</a></kbd></td>
        <td><kbd>8109128734</kbd></td>
        <td><kbd>Calle 3</kbd></td>
        <td><kbd>33-3</kbd></td>
        <td><kbd>64000</kbd></td>
        <td><kbd>Monterrey</kbd></td>
        <td><kbd>México</kbd></td>
        <td><kbd>Laptop</kbd></td>
        <td><kbd>25,000.00</kbd></td>
        <td><kbd>1</kbd></td>
      </tr>
      <tr>
        <td><kbd>5</kbd></td>
        <td><kbd>05/01</kbd></td>
        <td><kbd>Juan</kbd></td>
        <td><kbd>Perez</kbd></td>
        <td><kbd><a href="mailto:juan.perez@gmail.com">juan.perez@gmail.com</a></kbd></td>
        <td><kbd>5512345678</kbd></td>
        <td><kbd>Calle 4</kbd></td>
        <td><kbd>45-3</kbd></td>
        <td><kbd>03920</kbd></td>
        <td><kbd>CDMX</kbd></td>
        <td><kbd>México</kbd></td>
        <td><kbd>Micrófono</kbd></td>
        <td><kbd>2,500.00</kbd></td>
        <td><kbd>3</kbd></td>
      </tr>
    </tbody>
  </table>
</div>

<br>

**La segunda** forma normal se refiere a la eliminación de las dependencias funcionales parciales. En este caso, podemos identificar que los datos del cliente se duplican en las ventas.

Por lo tanto, podemos crear una entidad separada llamada "Clientes" que almacene estos datos y en la entidad principal "Ventas" agregamos la llave foránea que haga referencia al cliente.

<br>

<div style="display: flex; justify-content: center; margin-top: 20px;">
  <table border="1" cellpadding="8" cellspacing="0">
    <thead>
      <tr>
        <th><kbd>Venta</kbd></th>
        <th><kbd>Fecha</kbd></th>
        <th><kbd>Cliente</kbd></th>
        <th><kbd>Producto</kbd></th>
        <th><kbd>Precio</kbd></th>
        <th><kbd>Cantidad</kbd></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><kbd>1</kbd></td>
        <td><kbd>01/01</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>Laptop</kbd></td>
        <td><kbd>25,000.00</kbd></td>
        <td><kbd>2</kbd></td>
      </tr>
      <tr>
        <td><kbd>2</kbd></td>
        <td><kbd>02/01</kbd></td>
        <td><kbd>2</kbd></td>
        <td><kbd>Celular</kbd></td>
        <td><kbd>12,000.00</kbd></td>
        <td><kbd>3</kbd></td>
      </tr>
      <tr>
        <td><kbd>3</kbd></td>
        <td><kbd>03/01</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>Micrófono</kbd></td>
        <td><kbd>2,500.00</kbd></td>
        <td><kbd>1</kbd></td>
      </tr>
      <tr>
        <td><kbd>4</kbd></td>
        <td><kbd>04/01</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>Laptop</kbd></td>
        <td><kbd>25,000.00</kbd></td>
        <td><kbd>1</kbd></td>
      </tr>
      <tr>
        <td><kbd>5</kbd></td>
        <td><kbd>05/01</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>Micrófono</kbd></td>
        <td><kbd>2,500.00</kbd></td>
        <td><kbd>3</kbd></td>
      </tr>
    </tbody>
  </table>
</div>  

<br>

<div style="display: flex; justify-content: center; margin-top: 20px;">
  <table border="1" cellpadding="8" cellspacing="0">
    <thead>
      <tr>
        <th><kbd>Cliente</kbd></th>
        <th><kbd>Nombre</kbd></th>
        <th><kbd>Apellido</kbd></th>
        <th><kbd>Correo</kbd></th>
        <th><kbd>Teléfono</kbd></th>
        <th><kbd>Calle</kbd></th>
        <th><kbd>Número</kbd></th>
        <th><kbd>CP</kbd></th>
        <th><kbd>Ciudad</kbd></th>
        <th><kbd>País</kbd></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><kbd>1</kbd></td>
        <td><kbd>Juan</kbd></td>
        <td><kbd>Perez</kbd></td>
        <td><kbd><a href="mailto:juan.perez@gmail.com">juan.perez@gmail.com</a></kbd></td>
        <td><kbd>5512345678</kbd></td>
        <td><kbd>Calle 1</kbd></td>
        <td><kbd>58-1</kbd></td>
        <td><kbd>03100</kbd></td>
        <td><kbd>CDMX</kbd></td>
        <td><kbd>México</kbd></td>
      </tr>
      <tr>
        <td><kbd>2</kbd></td>
        <td><kbd>Pedro</kbd></td>
        <td><kbd>Gomez</kbd></td>
        <td><kbd><a href="mailto:pedro.gomez@gmail.com">pedro.gomez@gmail.com</a></kbd></td>
        <td><kbd>3387654321</kbd></td>
        <td><kbd>Calle 2</kbd></td>
        <td><kbd>85-6</kbd></td>
        <td><kbd>44100</kbd></td>
        <td><kbd>Guadalajara</kbd></td>
        <td><kbd>México</kbd></td>
      </tr>
      <tr>
        <td><kbd>3</kbd></td>
        <td><kbd>Ana</kbd></td>
        <td><kbd>Silva</kbd></td>
        <td><kbd><a href="mailto:ana.silva@gmail.com">ana.silva@gmail.com</a></kbd></td>
        <td><kbd>8109128734</kbd></td>
        <td><kbd>Calle 3</kbd></td>
        <td><kbd>33-3</kbd></td>
        <td><kbd>64000</kbd></td>
        <td><kbd>Monterrey</kbd></td>
        <td><kbd>México</kbd></td>
      </tr>
      <tr>
        <td><kbd>1</kbd></td>
        <td><kbd>Juan</kbd></td>
        <td><kbd>Perez</kbd></td>
        <td><kbd><a href="mailto:juan.perez@gmail.com">juan.perez@gmail.com</a></kbd></td>
        <td><kbd>5512345678</kbd></td>
        <td><kbd>Calle 4</kbd></td>
        <td><kbd>45-3</kbd></td>
        <td><kbd>03920</kbd></td>
        <td><kbd>CDMX</kbd></td>
        <td><kbd>México</kbd></td>
      </tr>
    </tbody>
  </table>
</div>

<br>

**Observación técnica (importante)**

**El Cliente = 1** aparece dos veces con distinta dirección.
Esto es correcto solo si:

Un cliente puede tener múltiples direcciones (modelo normalizado).

En un modelo de datos bien diseñado, lo habitual sería:

Clientes (datos únicos del cliente)

Direcciones (una o varias por cliente)

Si quieres, en el siguiente paso puedo:

Normalizar esta tabla correctamente.

Separarla en Clientes y Direcciones.

**Adaptarla a Excel, Power BI o SQL (modelo relacional).**

Sin embargo al extraer los datos del cliente se genera duplicidad de información, ya que se detecta que un cliente puede tener más de una dirección, por lo que es necesario crear una entidad separada llamada "Direcciones" que almacene estos datos y en la entidad principal "Ventas" agregamos la llave foránea que haga referencia a dicha dirección y finalmente la entidad "Clientes" sólo quedaría con la información personal de la persona.

Por lo que el modelo quedaría de la siguiente forma:

**CORRECTA #1**

<br>

<div style="display: flex; justify-content: center; margin-top: 20px;">
  <table border="1" cellpadding="8" cellspacing="0">
    <thead>
      <tr>
        <th><kbd>Venta</kbd></th>
        <th><kbd>Fecha</kbd></th>
        <th><kbd>Cliente</kbd></th>
        <th><kbd>Dirección</kbd></th>
        <th><kbd>Producto</kbd></th>
        <th><kbd>Precio</kbd></th>
        <th><kbd>Cantidad</kbd></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><kbd>1</kbd></td>
        <td><kbd>01/01</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>Laptop</kbd></td>
        <td><kbd>25,000.00</kbd></td>
        <td><kbd>2</kbd></td>
      </tr>
      <tr>
        <td><kbd>2</kbd></td>
        <td><kbd>02/01</kbd></td>
        <td><kbd>2</kbd></td>
        <td><kbd>2</kbd></td>
        <td><kbd>Celular</kbd></td>
        <td><kbd>12,000.00</kbd></td>
        <td><kbd>3</kbd></td>
      </tr>
      <tr>
        <td><kbd>3</kbd></td>
        <td><kbd>03/01</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>Micrófono</kbd></td>
        <td><kbd>2,500.00</kbd></td>
        <td><kbd>1</kbd></td>
      </tr>
      <tr>
        <td><kbd>4</kbd></td>
        <td><kbd>04/01</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>Laptop</kbd></td>
        <td><kbd>25,000.00</kbd></td>
        <td><kbd>1</kbd></td>
      </tr>
      <tr>
        <td><kbd>5</kbd></td>
        <td><kbd>05/01</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>4</kbd></td>
        <td><kbd>Micrófono</kbd></td>
        <td><kbd>2,500.00</kbd></td>
        <td><kbd>3</kbd></td>
      </tr>
    </tbody>
  </table>
</div>

<br>

**🔎 Lectura técnica del modelo (correcta):**

Venta → identificador de la transacción.

Cliente → clave foránea hacia la tabla Clientes.

Dirección → clave foránea hacia la tabla Direcciones.

Permite que un cliente tenga múltiples direcciones y que cada venta quede asociada a la dirección usada en esa compra.

Este diseño ya está normalizado (3FN) y es válido para:

* **Excel** (tablas dinámicas)

* **Power BI** (modelo estrella)

* **SQL** (relaciones con claves foráneas)

<br>

<div style="display: flex; justify-content: center; margin-top: 20px;">
  <table border="1" cellpadding="8" cellspacing="0">
    <thead>
      <tr>
        <th><kbd>Cliente</kbd></th>
        <th><kbd>Nombre</kbd></th>
        <th><kbd>Apellido</kbd></th>
        <th><kbd>Correo</kbd></th>
        <th><kbd>Teléfono</kbd></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><kbd>1</kbd></td>
        <td><kbd>Juan</kbd></td>
        <td><kbd>Perez</kbd></td>
        <td><kbd><a href="mailto:juan.perez@gmail.com">juan.perez@gmail.com</a></kbd></td>
        <td><kbd>5512345678</kbd></td>
      </tr>
      <tr>
        <td><kbd>2</kbd></td>
        <td><kbd>Pedro</kbd></td>
        <td><kbd>Gomez</kbd></td>
        <td><kbd><a href="mailto:pedro.gomez@gmail.com">pedro.gomez@gmail.com</a></kbd></td>
        <td><kbd>3387654321</kbd></td>
      </tr>
      <tr>
        <td><kbd>3</kbd></td>
        <td><kbd>Ana</kbd></td>
        <td><kbd>Silva</kbd></td>
        <td><kbd><a href="mailto:ana.silva@gmail.com">ana.silva@gmail.com</a></kbd></td>
        <td><kbd>8109128734</kbd></td>
      </tr>
    </tbody>
  </table>
</div>

<br>

**Observación técnica (verificable):**

**Esta tabla representa correctamente una entidad Clientes con:**

* Clave primaria: Cliente

* Atributos atómicos (1FN)

* Sin duplicados ni dependencias parciales (3FN)

* Este diseño es el adecuado como tabla maestra para relacionarla con:

* Ventas (Cliente como clave foránea)

* Direcciones (1 cliente → N direcciones)

**Si deseas, el siguiente paso natural es:**

* Crear la tabla Direcciones.

* Definir relaciones (Excel, Power BI o SQL).

* Calcular métricas (ventas por cliente, ticket promedio, etc.).

**EJEMPLO:**

<br>

<div style="display: flex; justify-content: center; margin-top: 20px;">
  <table border="1" cellpadding="8" cellspacing="0">
    <thead>
      <tr>
        <th><kbd>Dirección</kbd></th>
        <th><kbd>Cliente</kbd></th>
        <th><kbd>Calle</kbd></th>
        <th><kbd>Número</kbd></th>
        <th><kbd>CP</kbd></th>
        <th><kbd>Ciudad</kbd></th>
        <th><kbd>País</kbd></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><kbd>1</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>Calle 1</kbd></td>
        <td><kbd>58-1</kbd></td>
        <td><kbd>03100</kbd></td>
        <td><kbd>CDMX</kbd></td>
        <td><kbd>México</kbd></td>
      </tr>
      <tr>
        <td><kbd>2</kbd></td>
        <td><kbd>2</kbd></td>
        <td><kbd>Calle 2</kbd></td>
        <td><kbd>85-6</kbd></td>
        <td><kbd>44100</kbd></td>
        <td><kbd>Guadalajara</kbd></td>
        <td><kbd>México</kbd></td>
      </tr>
      <tr>
        <td><kbd>3</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>Calle 3</kbd></td>
        <td><kbd>33-3</kbd></td>
        <td><kbd>64000</kbd></td>
        <td><kbd>Monterrey</kbd></td>
        <td><kbd>México</kbd></td>
      </tr>
      <tr>
        <td><kbd>4</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>Calle 4</kbd></td>
        <td><kbd>45-3</kbd></td>
        <td><kbd>03920</kbd></td>
        <td><kbd>CDMX</kbd></td>
        <td><kbd>México</kbd></td>
      </tr>
    </tbody>
  </table>
</div>

<br>

**🔎 Validación del modelo (objetiva):**

* Dirección es la clave primaria.

* Cliente actúa como clave foránea hacia la tabla Clientes.

* El cliente 1 tiene dos direcciones → relación 1 a N, correcta.

* Todos los campos son atómicos → Primera Forma Normal (1FN).

* No hay dependencias parciales ni transitivas → 3FN.

**Este esquema es el correcto para:**

* Modelado relacional (SQL)

* Modelo estrella en Power BI

* Buenas prácticas en Excel estructurado

**La tercer forma normal** exige que no haya transparencias funcionales. Esto se logra removiendo todas las dependencias transitivas, es decir, aquellas dependencias en las que un atributo depende indirectamente de otro a través de un tercer atributo.

En este caso, la entidad "Ventas" ya está en la segunda forma normal, así que podemos continuar con la eliminación de dependencias transitivas.

La entidad "Ventas" depende transitoriamente del "Producto" a través de "Precio". Por lo tanto, debemos crear una entidad adicional para los "Productos" que incluya la información de estos.

Por lo cual nuestro modelo quedaría de la siguiente forma:

<br>

<div style="display: flex; justify-content: center; margin-top: 20px;">
  <table border="1" cellpadding="8" cellspacing="0">
    <thead>
      <tr>
        <th><kbd>Venta</kbd></th>
        <th><kbd>Fecha</kbd></th>
        <th><kbd>Cliente</kbd></th>
        <th><kbd>Dirección</kbd></th>
        <th><kbd>Producto</kbd></th>
        <th><kbd>Cantidad</kbd></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><kbd>1</kbd></td>
        <td><kbd>01/01</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>2</kbd></td>
      </tr>
      <tr>
        <td><kbd>2</kbd></td>
        <td><kbd>02/01</kbd></td>
        <td><kbd>2</kbd></td>
        <td><kbd>2</kbd></td>
        <td><kbd>2</kbd></td>
        <td><kbd>3</kbd></td>
      </tr>
      <tr>
        <td><kbd>3</kbd></td>
        <td><kbd>03/01</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>1</kbd></td>
      </tr>
      <tr>
        <td><kbd>4</kbd></td>
        <td><kbd>04/01</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>1</kbd></td>
      </tr>
      <tr>
        <td><kbd>5</kbd></td>
        <td><kbd>05/01</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>4</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>3</kbd></td>
      </tr>
    </tbody>
  </table>
</div>

<br>


<div style="display: flex; justify-content: center; margin-top: 20px;">
  <table border="1" cellpadding="8" cellspacing="0">
    <thead>
      <tr>
        <th><kbd>Producto</kbd></th>
        <th><kbd>Nombre</kbd></th>
        <th><kbd>Precio</kbd></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><kbd>1</kbd></td>
        <td><kbd>Laptop</kbd></td>
        <td><kbd>25,000.00</kbd></td>
      </tr>
      <tr>
        <td><kbd>2</kbd></td>
        <td><kbd>Celular</kbd></td>
        <td><kbd>12,000.00</kbd></td>
      </tr>
      <tr>
        <td><kbd>3</kbd></td>
        <td><kbd>Micrófono</kbd></td>
        <td><kbd>2,500.00</kbd></td>
      </tr>
    </tbody>
  </table>
</div>

<br>

<div style="display: flex; justify-content: center; margin-top: 20px;">
  <table border="1" cellpadding="8" cellspacing="0">
    <thead>
      <tr>
        <th><kbd>Cliente</kbd></th>
        <th><kbd>Nombre</kbd></th>
        <th><kbd>Apellido</kbd></th>
        <th><kbd>Correo</kbd></th>
        <th><kbd>Teléfono</kbd></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><kbd>1</kbd></td>
        <td><kbd>Juan</kbd></td>
        <td><kbd>Perez</kbd></td>
        <td><kbd><a href="mailto:juan.perez@gmail.com">juan.perez@gmail.com</a></kbd></td>
        <td><kbd>5512345678</kbd></td>
      </tr>
      <tr>
        <td><kbd>2</kbd></td>
        <td><kbd>Pedro</kbd></td>
        <td><kbd>Gomez</kbd></td>
        <td><kbd><a href="mailto:pedro.gomez@gmail.com">pedro.gomez@gmail.com</a></kbd></td>
        <td><kbd>3387654321</kbd></td>
      </tr>
      <tr>
        <td><kbd>3</kbd></td>
        <td><kbd>Ana</kbd></td>
        <td><kbd>Silva</kbd></td>
        <td><kbd><a href="mailto:ana.silva@gmail.com">ana.silva@gmail.com</a></kbd></td>
        <td><kbd>8109128734</kbd></td>
      </tr>
    </tbody>
  </table>
</div>

<br>

<div style="display: flex; justify-content: center; margin-top: 20px;">
  <table border="1" cellpadding="8" cellspacing="0">
    <thead>
      <tr>
        <th><kbd>Dirección</kbd></th>
        <th><kbd>Cliente</kbd></th>
        <th><kbd>Calle</kbd></th>
        <th><kbd>Número</kbd></th>
        <th><kbd>CP</kbd></th>
        <th><kbd>Ciudad</kbd></th>
        <th><kbd>País</kbd></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><kbd>1</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>Calle 1</kbd></td>
        <td><kbd>58-1</kbd></td>
        <td><kbd>03100</kbd></td>
        <td><kbd>CDMX</kbd></td>
        <td><kbd>México</kbd></td>
      </tr>
      <tr>
        <td><kbd>2</kbd></td>
        <td><kbd>2</kbd></td>
        <td><kbd>Calle 2</kbd></td>
        <td><kbd>85-6</kbd></td>
        <td><kbd>44100</kbd></td>
        <td><kbd>Guadalajara</kbd></td>
        <td><kbd>México</kbd></td>
      </tr>
      <tr>
        <td><kbd>3</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>Calle 3</kbd></td>
        <td><kbd>33-3</kbd></td>
        <td><kbd>64000</kbd></td>
        <td><kbd>Monterrey</kbd></td>
        <td><kbd>México</kbd></td>
      </tr>
      <tr>
        <td><kbd>4</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>Calle 4</kbd></td>
        <td><kbd>45-3</kbd></td>
        <td><kbd>03920</kbd></td>
        <td><kbd>CDMX</kbd></td>
        <td><kbd>México</kbd></td>
      </tr>
    </tbody>
  </table>
</div>

<br>

**La cuarta forma normal** **(Boyce-Codd)**, es más restrictiva con las dependencias transitivas, por lo que analizando la información del modelo detectamos que la entidad "Direcciones" sigue dependiendo del "País", por lo que debemos crear una entidad adicional que contenga la información de dicho atributo.

Finalmente la quinta forma normal (Dominio-Clave) exige eliminar cualquier dependencia funcional múltiple, pero en este modelo no existen por lo que también cumple con esta última forma normal.

Al final de la normalización el modelo quedo de la siguiente manera:

<br>

<div style="display: flex; justify-content: center; margin-top: 20px;">
  <table border="1" cellpadding="8" cellspacing="0">
    <thead>
      <tr>
        <th><kbd>Venta</kbd></th>
        <th><kbd>Fecha</kbd></th>
        <th><kbd>Cliente</kbd></th>
        <th><kbd>Dirección</kbd></th>
        <th><kbd>Producto</kbd></th>
        <th><kbd>Cantidad</kbd></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><kbd>1</kbd></td>
        <td><kbd>01/01</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>2</kbd></td>
      </tr>
      <tr>
        <td><kbd>2</kbd></td>
        <td><kbd>02/01</kbd></td>
        <td><kbd>2</kbd></td>
        <td><kbd>2</kbd></td>
        <td><kbd>2</kbd></td>
        <td><kbd>3</kbd></td>
      </tr>
      <tr>
        <td><kbd>3</kbd></td>
        <td><kbd>03/01</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>1</kbd></td>
      </tr>
      <tr>
        <td><kbd>4</kbd></td>
        <td><kbd>04/01</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>1</kbd></td>
      </tr>
      <tr>
        <td><kbd>5</kbd></td>
        <td><kbd>05/01</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>4</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>3</kbd></td>
      </tr>
    </tbody>
  </table>
</div>

<br>

<div style="display: flex; justify-content: center; margin-top: 20px;">
  <table border="1" cellpadding="8" cellspacing="0">
    <thead>
      <tr>
        <th><kbd>Producto</kbd></th>
        <th><kbd>Nombre</kbd></th>
        <th><kbd>Precio</kbd></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><kbd>1</kbd></td>
        <td><kbd>Laptop</kbd></td>
        <td><kbd>25,000.00</kbd></td>
      </tr>
      <tr>
        <td><kbd>2</kbd></td>
        <td><kbd>Celular</kbd></td>
        <td><kbd>12,000.00</kbd></td>
      </tr>
      <tr>
        <td><kbd>3</kbd></td>
        <td><kbd>Micrófono</kbd></td>
        <td><kbd>2,500.00</kbd></td>
      </tr>
    </tbody>
  </table>
</div>

<br>

<div style="display: flex; justify-content: center; margin-top: 20px;">
  <table border="1" cellpadding="8" cellspacing="0">
    <thead>
      <tr>
        <th><kbd>Cliente</kbd></th>
        <th><kbd>Nombre</kbd></th>
        <th><kbd>Apellido</kbd></th>
        <th><kbd>Correo</kbd></th>
        <th><kbd>Teléfono</kbd></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><kbd>1</kbd></td>
        <td><kbd>Juan</kbd></td>
        <td><kbd>Perez</kbd></td>
        <td><kbd><a href="mailto:juan.perez@gmail.com">juan.perez@gmail.com</a></kbd></td>
        <td><kbd>5512345678</kbd></td>
      </tr>
      <tr>
        <td><kbd>2</kbd></td>
        <td><kbd>Pedro</kbd></td>
        <td><kbd>Gomez</kbd></td>
        <td><kbd><a href="mailto:pedro.gomez@gmail.com">pedro.gomez@gmail.com</a></kbd></td>
        <td><kbd>3387654321</kbd></td>
      </tr>
      <tr>
        <td><kbd>3</kbd></td>
        <td><kbd>Ana</kbd></td>
        <td><kbd>Silva</kbd></td>
        <td><kbd><a href="mailto:ana.silva@gmail.com">ana.silva@gmail.com</a></kbd></td>
        <td><kbd>8109128734</kbd></td>
      </tr>
    </tbody>
  </table>
</div>

<br>

<div style="display: flex; justify-content: center; margin-top: 20px;">
  <table border="1" cellpadding="8" cellspacing="0">
    <thead>
      <tr>
        <th><kbd>Dirección</kbd></th>
        <th><kbd>Cliente</kbd></th>
        <th><kbd>Calle</kbd></th>
        <th><kbd>Número</kbd></th>
        <th><kbd>CP</kbd></th>
        <th><kbd>Ciudad</kbd></th>
        <th><kbd>País</kbd></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><kbd>1</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>Calle 1</kbd></td>
        <td><kbd>58-1</kbd></td>
        <td><kbd>03100</kbd></td>
        <td><kbd>CDMX</kbd></td>
        <td><kbd>1</kbd></td>
      </tr>
      <tr>
        <td><kbd>2</kbd></td>
        <td><kbd>2</kbd></td>
        <td><kbd>Calle 2</kbd></td>
        <td><kbd>85-6</kbd></td>
        <td><kbd>44100</kbd></td>
        <td><kbd>Guadalajara</kbd></td>
        <td><kbd>1</kbd></td>
      </tr>
      <tr>
        <td><kbd>3</kbd></td>
        <td><kbd>3</kbd></td>
        <td><kbd>Calle 3</kbd></td>
        <td><kbd>33-3</kbd></td>
        <td><kbd>64000</kbd></td>
        <td><kbd>Monterrey</kbd></td>
        <td><kbd>1</kbd></td>
      </tr>
      <tr>
        <td><kbd>4</kbd></td>
        <td><kbd>1</kbd></td>
        <td><kbd>Calle 4</kbd></td>
        <td><kbd>45-3</kbd></td>
        <td><kbd>03920</kbd></td>
        <td><kbd>CDMX</kbd></td>
        <td><kbd>1</kbd></td>
      </tr>
    </tbody>
  </table>
</div>

<br>

<div style="display: flex; justify-content: center; margin-top: 20px;">
  <table border="1" cellpadding="8" cellspacing="0">
    <thead>
      <tr>
        <th><kbd>País</kbd></th>
        <th><kbd>Nombre</kbd></th>
        <th><kbd>Dominio</kbd></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><kbd>1</kbd></td>
        <td><kbd>México</kbd></td>
        <td><kbd>mx</kbd></td>
      </tr>
    </tbody>
  </table>
</div>


