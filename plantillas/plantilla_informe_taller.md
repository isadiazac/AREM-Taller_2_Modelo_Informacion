# 📄 Informe Técnico del Taller

## 🔖 Nombre del Taller
Taller 2 - Modelo de Información y Diagrama de Contexto

## 👥 Integrantes del equipo
- Isabela Díaz Acosta
- Sebastián Sánchez Sandoval
- Samuel Esteban López Huertas

## 🧠 Descripción general del trabajo
El objetivo del taller fue modelar las entidades principales del dominio del cliente y representar los flujos de información entre actores y sistemas mediante un Modelo Entidad-Relación (ERD) y un Diagrama de Contexto de Negocio.

Durante la clase se trabajó con el caso base “Clínica Salud Viva” para comprender la estructura básica de un modelo ER y cómo identificar actores, sistemas y flujos de información. Posteriormente, el equipo adaptó estos conceptos al dominio real del cliente, enfocado en la gestión de solicitudes de cotización, generación de órdenes de venta, despacho, facturación, control de inventario y registro contable.

---

## 🔧 Proceso de desarrollo
Inicialmente se modeló el caso base en clase utilizando Lucidchart identificando las entidades principales (Paciente, Cita, Médico, Especialidad, Factura) y sus relaciones.

Posteriormente, para el cliente real:

1. Se identificaron los actores principales: Cliente y Asesor Comercial.
2. Se modeló el flujo principal del negocio:
   - Solicitud de cotización
   - Generación de cotización
   - Decisión (aceptada/rechazada)
   - Conversión a orden de venta
   - Despacho
   - Facturación
   - Registro contable
3. Se incluyó la gestión de productos, inventario y ajustes de precio según la información que proporcionó cliente.
4. Se incluyó añadir la razón o feedback del rechazo de una cotización, pues el cliente informó que le gusta añadir esto para entender la opinión de los clientes e intentar acomodarse más a sus necesidades.

Se utilizó Lucidchart para el modelado final y GitHub para el control de versiones del repositorio.

---

## 🧩 Análisis del modelo propuesto

### Estructura del modelo
El modelo está organizado en cuatro grandes bloques:

1. Gestión Comercial:
   - CLIENTE
   - ASESOR_COMERCIAL
   - SOLICITUD_COTIZACION
   - COTIZACION
   - DETALLE_COTIZACION
   - DECISION_COTIZACION

2. Gestión de Productos y Precios:
   - PRODUCTO
   - AJUSTE_PRECIO
   - INVENTARIO

3. Gestión Operativa:
   - ORDEN_VENTA
   - DESPACHO
   - DOCUMENTO_DESPACHO

4. Gestión Financiera:
   - FACTURA
   - MOVIMIENTO_CONTABLE

### Representación de necesidades del cliente
El modelo representa adecuadamente el ciclo completo del negocio:

- Desde que el cliente solicita una cotización,
- Hasta que se convierte en orden de venta,
- Se despacha el producto,
- Se genera factura,
- Y se registra el movimiento contable.

Además, se modelan:
- Estados del proceso (ENVIADA/APROBADA/RECHAZADA, EN_RUTA/ENTREGADO, EMITIDA/PAGADA, etc.).
- Control de inventario.
- Ajustes de precio basados en stock, proyección o promociones.
- Registro estructurado de rechazos con motivo y feedback.

### Supuestos tomados
- Cada cotización pertenece a una única solicitud.
- Una orden de venta solo se genera si la cotización es aceptada.
- Cada factura está asociada a una orden de venta.
- Los movimientos contables dependen directamente de la factura.
- El inventario se controla por producto.
- El registro de rechazo se almacena estructuradamente aunque operativamente pueda exportarse a Excel.

---

## 📈 Diagrama final entregado

### 🏥 Modelo ER - Caso Base (Hospital)

![Modelo ER Hospital](entrega/modelo-final-er-hospital.png)

### 🏢 Modelo ER - Cliente (Empresa)

![Modelo ER Empresa](entrega/modelo-final-er-empresa.png)


---

## 📋 Tabla de actores, entidades o componentes

| Nombre del elemento | Tipo | Descripción | Responsable |
|---------------------|------|-------------|-------------|
| Cliente | Actor | Persona o empresa que solicita cotización | Cliente |
| Asesor Comercial | Actor | Registra y gestiona solicitudes de cotización | Área Comercial |
| Solicitud_Cotizacion | Entidad | Registro inicial de intención de compra | Sistema Comercial |
| Cotizacion | Entidad | Documento formal con precios y vigencia | Sistema Comercial |
| Decision_Cotizacion | Entidad | Resultado de aceptación o rechazo | Cliente |
| Orden_Venta | Entidad | Pedido generado tras aceptación | Operaciones |
| Producto | Entidad | Bien o servicio ofrecido | Inventario |
| Inventario | Entidad | Control de stock actual y reservado | Logística |
| Despacho | Entidad | Proceso de envío del pedido | Logística |
| Factura | Entidad | Documento financiero de cobro | Finanzas |
| Movimiento_Contable | Entidad | Registro contable asociado a factura | Contabilidad |

---

## 🔍 Investigación complementaria

### Tema investigado:
Buenas prácticas en modelado Entidad-Relación y separación de dominios funcionales en arquitectura empresarial.

### Resumen:
El modelado Entidad-Relación permite representar de forma estructurada los datos críticos de un negocio, identificando entidades, atributos, claves primarias y relaciones. Según Chen (1976), el modelo ER facilita la comprensión conceptual antes de implementar bases de datos relacionales.

En arquitectura empresarial, separar dominios (comercial, operativo, financiero) mejora la claridad, escalabilidad y alineación con la estructura organizacional. Esto permite mapear procesos a sistemas y facilitar la interoperabilidad entre ERP, CRM y sistemas contables.

En este taller, la aplicación de estas buenas prácticas permitió estructurar el modelo del cliente en bloques coherentes, asegurando trazabilidad desde la solicitud inicial hasta el registro contable final.

---

## 📚 Referencias
- Chen, P. (1976). The Entity-Relationship Model—Toward a Unified View of Data.
- OMG. UML Specification. https://www.omg.org
- Fuente asistida por IA: ChatGPT, febrero 2026.

---

_Este documento hace parte de la entrega del taller 2 del curso AREM (Arquitectura Empresarial) - Universidad de La Sabana._
