![Título](https://img.shields.io/badge/FORMA%20RETAIL%20S.A.-00796B?style=for-the-badge&logoColor=white)

# Building Cloud Business Applications

📌 **Descripción y contexto de la empresa**

  <ul>
    <li>📦 Forma Retail Proyectos es una empresa especializada en la implementación de mobiliario comercial para tiendas del canal retail.</li>
    <li>🛠️ Cada mes, ejecuta diversos proyectos de instalación de góndolas, estanterías y equipamiento, adaptados a los requerimientos específicos de sus clientes.</li>
    <li>🏪 Actualmente, el 80% de los ingresos de la empresa proviene de un solo cliente: la cadena de tiendas de conveniencia "Facilito", que mantiene un ritmo constante de expansión con un promedio de 30 aperturas mensuales a nivel nacional.</li>
    <li>📐 Estas tiendas, de aproximadamente 200 m², requieren una solución integral que incluye el suministro de mobiliario, transporte e instalación.</li>
    <li>📊 Dado el peso estratégico de este cliente, es fundamental monitorear la facturación por proyecto de tienda, entendida como el monto promedio facturado por implementación.</li>
    <li>💡 Este indicador permite evaluar la consistencia en los precios, la eficiencia operativa y detectar oportunidades de mejora que impacten directamente en el resultado económico de la empresa.</li>
  </ul>
</div>

📌 **Descripción General del Proyecto - Arquitectura de Datos para FORMA RETAIL S.A.** 

  <ul>
    <li>El presente proyecto tiene como objetivo implementar una arquitectura moderna de datos para la empresa <strong>FORMA RETAIL S.A.</strong>, que permita gestionar de forma eficiente, automatizada y escalable la información generada en sus proyectos de implementación de mobiliario comercial para tiendas del canal retail.</li>
    <li>La arquitectura está pensada para centralizar los datos operativos y financieros de cada proyecto, optimizar su procesamiento mediante herramientas de ETL, y ofrecer acceso flexible y seguro a través de interfaces como Power BI, Excel y Power Apps.</li>
    <li>Se emplearán tecnologías en la nube como Azure SQL y Microsoft Fabric, brindando a FORMA RETAIL S.A. una solución robusta, integrada y lista para el análisis avanzado y la toma de decisiones estratégicas en tiempo real.</li>
  </ul>

📌 **Objetivos Principales**
  <ul>
    <li>Centralizar datos de los proyectos de implementación (costos, facturación, tiempos).</li>
    <li>Automatizar flujos ETL con Microsoft Fabric para mejorar la eficiencia operativa.</li>
    <li>Integrar Power Apps como capa de entrada y actualización de datos de campo.</li>
    <li>Consolidar un Data Warehouse para generar reportes confiables y oportunos.</li>
    <li>Facilitar el análisis de KPIs con Power BI y su distribución a las áreas clave.</li>
  </ul>

# Solución de Negocio Cloud con Microsoft Fabric, Power Platform y Power BI
  <h2>Solución de Negocio Moderna</h2>

  <p>Este proyecto implementa una arquitectura de datos moderna que integra diversas herramientas para mejorar la gestión, automatización y análisis de la información:</p>

  <ul>
    <li><strong>Microsoft Fabric Warehouse</strong> y <strong>Data Factory</strong> para centralizar, transformar y orquestar los datos empresariales.</li>
    <li><strong>Azure SQL</strong> como base de datos estructurada, confiable y escalable en la nube.</li>
    <li><strong>Power Apps</strong> para crear aplicaciones low-code que agilicen la captura y actualización de datos operativos.</li>
    <li><strong>Power BI</strong> para visualizar indicadores clave y facilitar la toma de decisiones basada en datos.</li>
    <li><strong>Power Automate</strong> para automatizar procesos dentro del flujo de trabajo y aumentar la eficiencia operativa.</li>
  </ul>

  <h2>Diagrama de la arquitectura de datos</h2>
  <img width="1281" height="674" alt="image" src="https://github.com/user-attachments/assets/ccf259cd-dd20-41ad-a5e4-fb20f18bb6ad" />


  <h2>C1:Capa de datos</h2>
<p>
  Como primera etapa del proyecto se organizó el conjunto de tablas que contienen los datos que describen nuestro caso de negocio. 
  Las tablas y las columnas que las conforman son las siguientes:
</p>

<ul>
  <li><strong>Presupuesto_detalle</strong> (Id_presupuesto_detalle, Id_presupuesto, Id_articulo, Cantidad, Costo_unitario, Precio_base, Costo_total_articulo, Precio_total_articulo)</li>
  <li><strong>Referencias</strong> (Id_articulo, descripcion)</li>
  <li><strong>Factura</strong> (cod_factura, cod_tienda, cod_cliente, id_presupuesto, importe_total_factura, fecha_facturacion)</li>
  <li><strong>EstadoPpto</strong> (Id_estado_ppto, descripcion)</li>
  <li><strong>Factura_detalle</strong> (cod_factura, id_articulo, cantidad, precio_unitario, monto_total_articulo)</li>
  <li><strong>Tienda</strong> (cod_tienda, nombre_tienda, Id_cliente, dirección_envío, id_proyectista, id_comercial, metros_cuadrados, departamento, provincia, distrito)</li>
  <li><strong>Comerciales</strong> (Id_comercial, Nombre)</li>
  <li><strong>Proyectista</strong> (Id_Proyectista, Nombre)</li>
  <li><strong>Presupuesto</strong> (id_presupuesto, cod_tienda, coste_total, importe_total, id_estado_ppto, id_comercial, fecha_emision)</li>
  <li><strong>Clientes</strong> (Id_cliente, nombre_empresa, RUC)</li>
</ul>

<p>
  Para trabajar todo en la nube, se procedió a crear un servidor en <strong>Azure</strong> y dentro de este una base de datos <strong>SQL</strong>. 
  Posteriormente, se cargaron todas las tablas para continuar con la implementación.
</p>
<img width="600" height="150" alt="Fig 1" src="https://github.com/user-attachments/assets/769a756e-bdf5-4669-8204-27d3dccc0232" />

<img width="600" height="500" alt="Fig 2" src="https://github.com/user-attachments/assets/ad6d3002-ace9-4ac5-b770-4e2b2ba20a9a" />

<p>
  Una vez cargadas las tablas en el servidor de <strong>Azure</strong>, se generaron flujos de datos en <strong>Fabric</strong> para cada una de ellas. 
</p>
<p>
  A continuación, se creó un <strong>Data Warehouse</strong> que servirá como almacenamiento relacional para nuestro proyecto. 
  Posteriormente, se configuraron los destinos de datos de los flujos creados en el paso anterior hacia este almacén.
</p>

<img width="600" height="150" alt="Fig 3" src="https://github.com/user-attachments/assets/1fbbee8e-61d8-4942-956f-35ed38937448" />


<img width="600" height="150" alt="Fig 4" src="https://github.com/user-attachments/assets/42efcc09-7284-4621-805c-3c538e89c1ab" />


<img width="800" height="500" alt="Fig 5" src="https://github.com/user-attachments/assets/2fca82e7-4852-49f7-8288-47272f7661af" />

<p>
  Luego de realizar los pasos anteriores, se obtuvo un esquema como el siguiente:
</p>

<img width="749" height="585" alt="Fig 6" src="https://github.com/user-attachments/assets/5b7e55e6-30c4-45af-80db-83087630b28a" />

<p>
  Se procedió a relacionar las tablas de acuerdo al modelo de datos planteado anteriormente.
</p>

<img width="800" height="500" alt="Fig 7" src="https://github.com/user-attachments/assets/23455bc0-0aa3-42f5-937d-364da82076bf" />

<p>
  Finalmente, se creó un <strong>modelo semántico</strong> que permitió enlazar todo lo ya creado en <strong>Fabric</strong> con el informe de <strong>Power BI</strong> elaborado en el curso anterior.
</p>

<img width="868" height="213" alt="Fig 8" src="https://github.com/user-attachments/assets/c0bce53c-f5d5-4bbf-814e-e22ee83a7887" />

<p>
  Adicionalmente a todo lo descrito, nuestro informe de <strong>Power BI</strong> cuenta con medidas para mostrar los <strong>KPI</strong> que son esenciales para describir nuestro caso de negocio. 
  Por ello, se procedió a generar una tabla que contiene todos estos indicadores, denominada <strong>G7_med</strong>, la cual cuenta con las columnas: <em>day, month, year, fecha_calculada, Meta_ticket_promedio, Rango_1, Rango_2, Valor_inicial, Valor_final</em>.
</p>
<img width="224" height="548" alt="Fig 9" src="https://github.com/user-attachments/assets/6b332a5f-a1cf-46fa-a2c4-a13e37f69c1a" />

<p>
  Las medidas se crearon con fórmulas <strong>DAX</strong> y tienen las siguientes expresiones:
</p>

<pre>
Amarillo = 'G7_med'[Meta]*1
KPI 2 = CALCULATE([KPI_Ticket_Promedio_Mensual(2)], 
          'G7_Factura_detalle'[id_articulo] <> "REF00001003",
          'G7_Factura_detalle'[id_articulo] <> "REF00001004",
          'G7_Factura_detalle'[id_articulo] <> "REF00001005")
KPI_Ticket_Promedio_Mensual = DIVIDE([TotalFacturado], [TiendasImplementadas], 0)
KPI_Ticket_Promedio_Mensual(2) = DIVIDE([MontoTotal_2],[TiendasImplementadas],0)
MontoTotal_2 = SUM('G7_Factura_detalle'[monto_total_articulo])
Rojo = 'G7_med'[Meta]*0.714285
TiendasImplementadas = DISTINCTCOUNT('G7_Factura'[cod_tienda])
TotalFacturado = SUM('G7_Factura'[importe_total_factura])
</pre>

  <h2>C2: Capa de aplicación</h2>
  
  📌 **Preámbulo** 

  <p>
    Como paso inicial del desarrollo de la aplicación para <strong>FORMA RETAIL S.A.</strong>, elaboramos un diagrama de flujo de funcionamiento con el objetivo de construir un primer bosquejo de cómo operaría el sistema. Este enfoque nos permitió tener una visión global del proceso, facilitando la planificación y creación de las pantallas de la aplicación.
  </p>

  <p>
    Además, este diagrama resultó clave para comprender correctamente el negocio y asegurar que el diseño de la aplicación refleje de forma adecuada sus procesos y necesidades reales.
  </p>
</div>
<h4 id="">Diagrama de Flujo del funcionamiento del Negocio</h4>
<p>
  <img width="1231" height="1369" alt="image" src="https://github.com/user-attachments/assets/caf08612-2cff-4de0-a729-abffd12a33b3" />

  A continuación, se presentan las distintas pantallas que conforman la aplicación, junto con su propósito y principales funcionalidades:
</p>
<h4 id="">Pantalla 1️⃣: Pantalla de Bienvenida/Inicio</h4>
<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/a4e86d29-b6cc-461a-aaf8-c553049f48c6" />
  <p>
    Esta pantalla actúa como punto de entrada principal a la aplicación, permitiendo al usuario seleccionar la acción que desea realizar dentro del sistema. La función transaccional principal disponible desde aquí es <strong>Gestionar Presupuesto</strong>.
  </p>

  <h4>🎯 Propósito</h4>
  <p>
    Centralizar el acceso a las diferentes funciones de la aplicación y ofrecer una navegación clara, visual e intuitiva para el usuario.
  </p>

  <h4>⚙️ Funcionalidades</h4>
  <ul>
    <li>Seleccionar la acción a realizar desde el menú principal.</li>
    <li>Acceso directo a <strong>Gestionar Presupuesto</strong> para visualizar presupuestos existentes o crear nuevos.</li>
    <li>Acceso a la administración de los distintos maestros del sistema:
      <ul>
        <li>Gestionar Tiendas</li>
        <li>Gestionar Referecias</li>
        <li>Gestionar Comerciales</li>
        <li>Gestionar Facturas</li>
        <li>Gestionar Clientes</li>
        <li>Gestionar Proyectistas</li>
      </ul>
    </li>
  </ul>

<h4 id="">Pantalla 2️⃣: Pantalla de Buscar Presupuesto</h4>
<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/63a84f64-3ba7-4fc8-8a6a-1d178ec724bc" />

  <h4>🎯 Propósito</h4>
  <p>
    Facilitar la búsqueda y selección de presupuestos existentes, permitiendo filtrar por cliente y tienda para acceder de forma ágil al presupuesto que se desea gestionar.
  </p>

  <h4>⚙️ Funcionalidades</h4>
  <ul>
    <li>Buscar presupuestos existentes filtrando primero por <strong>Cliente</strong> y luego por <strong>Tienda</strong> asociada.</li>
    <li>Acceder directamente a la <strong>galería de tiendas</strong> y seleccionar una tienda para visualizar sus presupuestos creados en el panel derecho.</li>
    <li>Utilizar el botón <strong>“Ver todos los presupuestos”</strong> para acceder directamente a la pantalla de gestión de presupuestos de la tienda seleccionada.</li>
    <li>Si no existe una tienda registrada, usar el botón <strong>“Gestionar Tienda”</strong> para crear una nueva tienda y continuar con el proceso de creación de un nuevo presupuesto.</li>
  </ul>

<h4 id="">Pantalla 3️⃣: Pantalla Gestionar Presupuestos</h4>
<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/e8c1a910-58a0-42a4-96b1-bbc6956753fa" />

  <h4>🎯 Propósito</h4>
  <p>
    Administrar los presupuestos asociados a una tienda específica, permitiendo tanto la creación de nuevos presupuestos como la visualización, consulta y acciones adicionales sobre los ya existentes.
  </p>

  <h4>⚙️ Funcionalidades</h4>
  <ul>
    <li>Visualizar en la <strong>galería lateral izquierda</strong> todos los presupuestos relacionados con la tienda seleccionada previamente.</li>
    <li>Seleccionar un presupuesto en la galería para ver sus principales campos y datos registrados.</li>
    <li>Crear un nuevo presupuesto mediante el botón <strong>“Crear nuevo presupuesto”</strong>, lo que habilita en el panel derecho los campos a completar para su registro.</li>
    <li>Acceder al detalle completo de un presupuesto existente con la opción <strong>“Ver detalle presupuesto”</strong>, que abre una nueva ventana con la información ampliada.</li>
    <li>Enviar por correo la información de un presupuesto seleccionado mediante el botón <strong>“PA: Enviar_ppto”</strong>, el cual notifica automáticamente a los usuarios programados.</li>
    <li>Gestionar las facturas relacionadas con un presupuesto existente o recién creado a través del botón <strong>“Gestionar Facturas”</strong>, que permite crear o visualizar facturas vinculadas.</li>
  </ul>

<h4 id="">Pantalla 4️⃣: Pantalla Gestionar Presupuesto Detalle</h4>
<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/4f23c548-c687-4139-9bf0-1ca16cb9823e" />

  <h4>🎯 Propósito</h4>
  <p>
    Administrar las referencias o artículos que conforman el detalle de un presupuesto específico, permitiendo visualizar, consultar y adicionar nuevas referencias según corresponda.
  </p>

  <h4>⚙️ Funcionalidades</h4>
  <ul>
    <li>Visualizar en la <strong>galería de la derecha</strong> todas las referencias que integran el detalle del presupuesto seleccionado en la pantalla anterior.</li>
    <li>Activar la visualización de los campos asociados a una referencia mediante el botón de la <strong>flechita verde</strong>.</li>
    <li>Adicionar nuevas referencias al detalle de presupuesto, validando previamente su existencia.</li>
    <li>En caso de que la referencia no exista, crearla a través del botón <strong>“Gestionar Referencias”</strong>.</li>
    <li>Si la referencia ya existe, añadirla al presupuesto detalle con el botón <strong>“+”</strong> ubicado en la parte superior de la galería de referencias.</li>
  </ul>

<h4 id="">Pantalla 5️⃣: Pantalla Gestionar Factura</h4>
<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/7faa1160-b73e-4d74-9b27-0054962c8a56" />
<h4>🎯 Propósito</h4>
<p>
  Administrar las facturas relacionadas a un presupuesto específico o visualizarlas de manera general desde la pantalla de inicio, permitiendo crear nuevas facturas y modificar las existentes.
</p>

<h4>⚙️ Funcionalidades</h4>
<ul>
  <li>Visualizar en la <strong>galería de la derecha</strong> todas las facturas asociadas al presupuesto seleccionado en la pantalla <strong>“Gestionar Presupuestos”</strong>.</li>
  <li>Crear una nueva factura mediante el botón <strong>“+”</strong> ubicado en la parte superior de la galería, completando los campos habilitados en el lado derecho para su registro.</li>
  <li>Modificar una factura existente seleccionándola en la galería, editando sus campos a través del ícono de <strong>lapicito</strong> y guardando los cambios con el botón de <strong>check azul</strong>.</li>
  <li>Acceder desde la <strong>Pantalla de Bienvenida/Inicio</strong> para consultar todas las facturas sin filtros aplicados.</li>
</ul>

<h4 id="">Pantalla 6️⃣: Pantalla Gestionar Factura Detalle</h4>
<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/618e528b-2f6c-4029-984b-059ade17bfb3" />
<h4>🎯 Propósito</h4>
<p>
  Administrar las referencias o artículos que conforman el detalle de una factura específica, permitiendo visualizar, adicionar o modificar la información relacionada a cada línea de la factura.
</p>

<h4>⚙️ Funcionalidades</h4>
<ul>
  <li>Visualizar en la <strong>galería izquierda</strong> todas las referencias asociadas a la factura seleccionada.</li>
  <li>Al seleccionar una referencia en la galería, consultar sus <strong>campos detallados</strong> en la parte derecha de la pantalla.</li>
  <li>Adicionar nuevas referencias al detalle de la factura mediante el botón <strong>“+ Insertar referencia o artículo a factura detalle”</strong>, completando los campos requeridos en la parte derecha y guardando con el <strong>check azul</strong>.</li>
  <li>Modificar referencias existentes seleccionándolas en la galería, editando sus campos con el <strong>icono de lápiz azul</strong> y guardando los cambios con el <strong>check azul</strong>.</li>
</ul>

<h4 id="">Pantalla 7️⃣: Pantalla Gestionar Clientes</h4>
<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/da0d3770-af50-42fb-89c8-0c2958cdf75d" />
<h4>🎯 Propósito</h4>
<p>
  Crear y gestionar los datos de nuevos Clientes.
</p>

<h4>⚙️ Funcionalidades</h4>
<ul>
  <li>Registrar los datos del Cliente como el RUC y el nombre.</li>
  <li>Crear un nuevo código por cada Cliente con el nombre y RUC que le corresponde.</li>
</ul>

<h4 id="">Pantalla 8️⃣: Pantalla Gestionar Tiendas</h4>
<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/9d29520b-9ce9-4cf4-8093-64e5f1bbd225" />
<h4>🎯 Propósito</h4>
<p>
  Crear y gestionar las Tiendas a las que se asignarán los presupuestos.
</p>

<h4>⚙️ Funcionalidades</h4>
<ul>
  <li>Visualizar el código por el cual se identifica cada Tienda.</li>
  <li>Crear un nuevo código por cada Tienda con el nombre que le corresponde.</li>
  <li>Registrar los datos de cada Tienda: dirección, provincia, distrito, departamento y metros cuadrados.</li>
  <li>Asignar el Proyectista, Comercial y Cliente mediante el ID de cada uno.</li>
  <li>Desde esta screen se puede acceder, mediante un botón, a la pantalla de creación/modificación de Proyectistas, Comerciales o Clientes en caso sea necesario registrarlos.</li>
</ul>

<h4 id="">Pantalla 9️⃣: Pantalla Gestionar Comerciales</h4>
<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/d7c6bfe7-3bb8-4fee-82b0-d7f48d3904b3" />
<h4>🎯 Propósito</h4>
<p>
  Crear y gestionar los datos de nuevos Comerciales, para asignarlos a cada tienda para su desarrollo.
</p>

<h4>⚙️ Funcionalidades</h4>
<ul>
  <li>Visualizar el código por el cual se identifica cada Comercial.</li>
  <li>Crear un nuevo código por cada Comercial con el nombre que le corresponde.</li>
</ul>

<h4 id="">Pantalla 🔟: Pantalla Gestionar Proyectistas</h4>
<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/68be84d0-2096-497e-bdf1-c2965437c012" />
<h4>🎯 Propósito</h4>
<p>
  Crear y gestionar los datos de nuevos Proyectistas, para asignarlos a cada tienda para su desarrollo.
</p>

<h4>⚙️ Funcionalidades</h4>
<ul>
  <li>Visualizar el código por el cual se identifica cada Proyectista.</li>
  <li>Crear un nuevo código por cada Proyectista con el nombre que le corresponde.</li>
</ul>

<h4 id="">Pantalla 1️⃣1️⃣: Pantalla Gestionar Referencias</h4>
<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/3164bb0c-581e-44a9-898b-74ad7c1b2891" />
<h4>🎯 Propósito</h4>
<p>
  Crear y gestionar las referencias de los artículos que se van a incluir en los presupuestos.
</p>

<h4>⚙️ Funcionalidades</h4>
<ul>
  <li>Visualizar el código por el cual se identifica cada Referencia (Artículo).</li>
  <li>Crear un nuevo código por cada Referencia con el nombre que le corresponde.</li>
</ul>

<h2>C3: Capa de extracción, transformación y carga</h2>

<p>
  Para esta capa se trabajó en una función que permite mantenerse actualizado sobre el estado del negocio. 
  Para ello, se desarrolló un código en <strong>Python</strong> que realiza una búsqueda en las tablas <strong>Presupuestos</strong> y <strong>Facturas</strong>. 
  Si se detectan nuevos registros, se extrae la información relacionada y se genera un informe que se envía por correo a los involucrados. 
  En caso de no existir nuevos presupuestos ni facturas, también se envía un correo notificando que no hay registros nuevos.
</p>

<p>
  Para lograr este objetivo se definieron las siguientes funciones:
</p>

<ol>
  <li><strong>Obtener nuevos presupuestos:</strong></li>
<img width="736" height="685" alt="C3 - Fig 1" src="https://github.com/user-attachments/assets/144cee3d-6c73-49a6-b1e4-84aac6e54984" />
  
  <li><strong>Obtener nuevas facturas:</strong></li>
<img width="762" height="669" alt="C3 - Fig 2" src="https://github.com/user-attachments/assets/f41a0257-db81-48ad-bd97-c98878842b23" />

<li><strong>Generar cuerpo del mail:</strong></li>

<img width="666" height="499" alt="C3 - Fig 3 1" src="https://github.com/user-attachments/assets/6ef33895-5d3d-420f-9940-cddfe10b356f" />

<img width="859" height="690" alt="C3 - Fig 3 2" src="https://github.com/user-attachments/assets/de1d78e9-d72b-4bd4-96de-166d026b471f" />

<img width="869" height="495" alt="C3 - Fig 3 3" src="https://github.com/user-attachments/assets/422c28e0-de3d-430c-87f9-edc669bd7bcc" />

<li><strong>Generar cuerpo del mail sin registros:</strong></li>
<img width="550" height="650" alt="C3 - Fig 4" src="https://github.com/user-attachments/assets/e0d2d837-5a5c-45ab-91fd-f634e131c605" />

<li><strong>Enviar correo:</strong></li>
<img width="534" height="345" alt="C3 - Fig 5" src="https://github.com/user-attachments/assets/2b4a3462-e580-4db8-9b03-8ab80414690e" />

<li><strong>Main (función principal que ejecuta todo el código):</strong></li>
<img width="736" height="724" alt="C3 - Fig 6" src="https://github.com/user-attachments/assets/6d1542c9-6f80-4a38-a4cb-1990fa76732b" />
</ol>

<p>
  De acuerdo con la forma de trabajo de <strong>Fabric</strong>, este tipo de procedimientos debe almacenarse en un 
  <strong>Data Lakehouse</strong>, para lo cual se creó uno llamado <strong>G7_automatizacion</strong>. 
  Además, se añadió el pipeline diseñado para la actualización de datos, el cual recoge tanto este 
  <strong>Notebook</strong> como los flujos de datos generados en la <em>Capa 1</em>.
</p>

<img width="1046" height="326" alt="C3 - Fig 7" src="https://github.com/user-attachments/assets/d172167c-e0bd-4652-8299-e7c3c4c12c3f" />

<p>
  Finalmente, se agregó una programación en el <strong>Notebook</strong> creado para que este informe se envíe de forma diaria a las 
  <strong>22:30</strong>, hora local.
</p>
<img width="784" height="554" alt="C3 - Fig 8" src="https://github.com/user-attachments/assets/d21b4abd-4f14-41e3-8ada-10e767568854" />


<h2>C4: Capa de almacén de datos</h2>

<p>
  La <strong>capa de almacén de datos</strong> constituye el corazón del ecosistema analítico, ya que concentra, organiza y optimiza la información proveniente de la capa de integración (ETL). 
  En esta fase, los datos son depurados, normalizados y estructurados dentro de un repositorio central, como <strong>Microsoft Fabric</strong>, garantizando su disponibilidad para el análisis empresarial.
</p>

<p>
  En esta capa se construyen relaciones entre tablas principales (<strong>G7_Factura</strong>, <strong>G7_Presupuesto</strong>, <strong>G7_Tienda</strong>, entre otras), 
  así como medidas calculadas clave que permiten dar contexto a la información (<strong>G7_med</strong>).
</p>

<p>
  Una tabla fundamental es la <strong>tabla calendario (df_Calendario)</strong>, que habilita análisis temporales detallados y comparativos, esenciales para evaluar tendencias, 
  comportamientos de tiendas y desempeño por periodos o sedes.
</p>

<p>
  Gracias a su diseño robusto, el <strong>Data Warehouse</strong> asegura la consistencia, escalabilidad y trazabilidad de los datos, 
  convirtiéndose en la base confiable sobre la cual se soportan los procesos de análisis y la generación de reportes en <strong>Power BI</strong>. 
  Esta capa no solo aporta eficiencia operativa, sino que también impulsa la toma de decisiones estratégicas basadas en información clara y oportuna.
</p>

<h4> 🔴 Data Warehouse en Microsoft Fabric</h4>
<img width="786" height="436" alt="MODEL LAYAOUT" src="https://github.com/user-attachments/assets/27af6d7f-734f-444e-bfae-e85a79978270" />

<h4> 🔴 Relaciones creadas</h4>
<img width="500" height="320" alt="RELACIONES" src="https://github.com/user-attachments/assets/b101bb80-7f57-4f0f-96b9-d1a0ed41c4aa" />

<p>
  Dentro de esta capa se ha utilizado <strong>Power Automate</strong> para implementar una automatización en el envío de datos de presupuesto. 
  El presupuesto es ingresado mediante la pantalla de <strong>“Gestionar Presupuestos”</strong> del <strong>Power Apps</strong>. 
  Mediante la selección del botón <strong>“PA: Enviar_ppto”</strong>, la data del presupuesto es cargada a una lista creada en <strong>SharePoint</strong> llamada <em>“Presupuestos Facilito”</em> 
  y, a su vez, es enviada de forma automática por correo electrónico a los destinatarios notificados.
</p>

<h4> 🔴 Flujo de Power Automate</h4>

<p>
  En la siguiente imagen se observa el flujo creado llamado <strong>“power”</strong>, 
  con los pasos que incluyen la obtención de datos desde <strong>Power Apps</strong>, 
  el envío de dichos datos a la lista de <strong>SharePoint</strong> creada, 
  y la configuración para el envío automático de correos electrónicos.
</p>
<img width="900" height="300" alt="FLUJO EN POWER AUTOMATE" src="https://github.com/user-attachments/assets/9d4e3149-5fb4-40d1-97b7-7863ed2a9a26" />

<h4> 🔴 Entorno de Power Apps y su vínculo con Power Automate</h4>

<p>
  En la siguiente imagen se visualiza el flujo de <strong>Power Automate</strong> creado llamado <strong>“power”</strong>, 
  el cual está vinculado al botón <strong>PA: Enviar_ppto</strong>.
</p>
<img width="800" height="350" alt="PA EN POWER APPS" src="https://github.com/user-attachments/assets/8db1819f-4f9b-4009-8082-5d7303b509e1" />

<h4> 🔴 Visualización en lista de SharePoint</h4>

<img width="800" height="380" alt="SHAREPOINT" src="https://github.com/user-attachments/assets/e9f4b446-bddf-48b5-8d40-5104dd402f25" />

<h4> 🔴 Visualización del envío del correo electrónico</h4>

<img width="387" height="269" alt="CORREO ELECTRONICO" src="https://github.com/user-attachments/assets/511e73f9-2282-4c67-acdc-00f771b05d6f" />


<h2>C5: Capa de presentación</h2>

  <h4>📝 Descripción General</h4>
  <p>
    Los reportes generados en <strong>Power BI</strong> representan la capa de presentación de la solución empresarial, 
    ya que transforman información compleja en visualizaciones claras, comprensibles y orientadas a la acción. 
    Estos reportes están diseñados con un enfoque ejecutivo, cuidando los detalles y priorizando la experiencia del usuario 
    mediante una interfaz moderna e intuitiva.
  </p>

  <h4>⚙️ Principales Características</h4>
  <ul>
    <li>📖 <strong>Storytelling con datos</strong>: cada reporte sigue una secuencia lógica que facilita la lectura 
        y comprensión de los resultados, vinculando métricas con decisiones estratégicas.</li>
    <li>📈 <strong>Análisis descriptivo y predictivo</strong>: los reportes incluyen indicadores como ticket promedio mensual, 
        tendencias de ventas y segmentación por ubicación.</li>
    <li>🎛️ <strong>Filtros dinámicos e interacción cruzada</strong>: los usuarios pueden personalizar la vista aplicando 
        filtros por fechas, sedes u otros criterios, enriqueciendo el análisis de forma flexible.</li>
    <li>🔄 <strong>Actualización automatizada</strong>: la información se alimenta desde el <strong>Data Warehouse</strong> 
        mediante procesos automáticos, garantizando datos precisos y en tiempo real.</li>
  </ul>

  <h4>🚀 Impacto</h4>
  <p>
    Esta capa convierte el ecosistema de datos de <strong>Forma Retail SAC</strong> en un soporte estratégico para la toma de 
    decisiones basadas en evidencia. La claridad visual, sumada al análisis predictivo y contextualizado, contribuye a mejorar 
    la eficiencia operativa y detectar nuevas oportunidades de optimización continua.
  </p>
  <h4>📊 Reportes con Microsoft Power BI</h4>
  <h4>🔴Caso de Negocio <h4> 
    <img width="800" height="400" alt="CASO DE NEGOCIO" src="https://github.com/user-attachments/assets/54fa07d1-4a0d-460e-ace9-531d7e92b63b" />
  <h4>🔴Indicadores<h4> 
   <img width="800" height="400" alt="INDICADORES" src="https://github.com/user-attachments/assets/4f8f370f-bdb4-4e46-8b45-6bfd88ec9c61" />
  <h4>🔴Dashboard<h4> 
   <img width="800" height="400" alt="DASHBOARD" src="https://github.com/user-attachments/assets/20e0f143-e2a9-41e2-9c48-68df051911a7" />
  <h4>🔴Reporte<h4> 
   <img width="800" height="400" alt="REPORTE" src="https://github.com/user-attachments/assets/81ce8a56-796f-4042-8bcc-6867085b1e04" />
  <h4>🔴Informe 1<h4> 
   <h5>➡️Pantalla <h5> 
   <img width="800" height="400" alt="INFORME 1" src="https://github.com/user-attachments/assets/dcfd5200-1b5b-46fa-8ce3-e935535a9a4d" />
   <h5>➡️Pantalla-Selección <h5> 
   <img width="800" height="400" alt="INFORME 1_SELECCION" src="https://github.com/user-attachments/assets/e7b0d867-ac58-4f50-a54e-7d1c180f1eb1" />
   <h5>➡️Pantalla-Drill Through <h5> 
   <img width="800" height="400" alt="INFORME 1_DRILL THROUGH" src="https://github.com/user-attachments/assets/84047554-414c-4baa-af95-3fe5a0915194" />
  <h4>🔴Informe 2<h4> 
   <h5>➡️Pantalla <h5> 
   <img width="800" height="400" alt="INFORME 2" src="https://github.com/user-attachments/assets/3ffc936a-5847-41ff-adfc-7eb38beb861f" />
    <h5>➡️Pantalla-Selección <h5> 
   <img width="800" height="400" alt="INFORME 2_SELECCION" src="https://github.com/user-attachments/assets/e3f9564a-a048-4230-be8b-e3869037f4e8" />
    <h5>➡️Pantalla-Drill Through <h5> 
   <img width="800" height="400" alt="INFORME 2_DRILL THROUGH" src="https://github.com/user-attachments/assets/9226d888-06ca-41bc-8fa5-461ecf99a8a0" />
  <h4>🔴Informe 3<h4>
   <h5>➡️Pantalla <h5> 
   <img width="800" height="400" alt="INFORME 3" src="https://github.com/user-attachments/assets/0864879a-6ec3-48da-b032-9f58a61a8581" />
    <h5>➡️Pantalla-Selección <h5> 
   <img width="800" height="400" alt="INFORME 3_SELECCION" src="https://github.com/user-attachments/assets/c82b9fa1-a722-4776-aa69-774abad4ef4c" />
   <h5>➡️Pantalla-Drill Through <h5>
   <img width="800" height="400" alt="INFORME 3_DRILL THROUGH" src="https://github.com/user-attachments/assets/c888f5bf-a313-45d4-aa82-8b92f8949ce7" />
  <h4>🔴Informe 4<h4>
   <h5>➡️Pantalla <h5> 
   <img width="800" height="400" alt="INFORME 4" src="https://github.com/user-attachments/assets/b3fe13d6-9701-469f-bd00-41bcbdf6ae61" />
    <h5>➡️Pantalla-Selección <h5> 
   <img width="800" height="400" alt="INFORME 4_SELECCION" src="https://github.com/user-attachments/assets/4d9b9775-2b9f-4c88-85bc-f1f370e3335f" />
    <h5>➡️Pantalla-Drill Through <h5>
   <img width="800" height="400" alt="INFORME 4_DRILL THROUGH" src="https://github.com/user-attachments/assets/c7f159fd-a80b-4a0a-a9e0-17a42fb41342" />
  <h4>🔴Informe 5<h4>
    <h5>➡️Pantalla <h5> 
   <img width="800" height="400" alt="INFORME 5" src="https://github.com/user-attachments/assets/0d1096cb-c533-48e4-87a5-7577a5d3e85f" />
    <h5>➡️Pantalla-Selección <h5> 
   <img width="800" height="400" alt="INFORME 5_SELECCION" src="https://github.com/user-attachments/assets/9f8ac525-ba43-433a-b7fe-619455216623" />
    <h5>➡️Pantalla-Drill Through <h5>
   <img width="800" height="400" alt="INFORME 5_DRILL THROUGH" src="https://github.com/user-attachments/assets/9f025eef-b191-41bf-8345-378d36392a78" />
   <h4>🔴Informe 6<h4>
     <h5>➡️Pantalla <h5> 
   <img width="800" height="400" alt="INFORME 6" src="https://github.com/user-attachments/assets/168c3492-d4d5-46f5-928f-6e44de768c55" />
    <h5>➡️Pantalla-Selección <h5> 
   <img width="800" height="400" alt="INFORME 6_SELECCION" src="https://github.com/user-attachments/assets/91d34e3d-a1a1-4c51-9a63-406f9ca89a21" />
    <h5>➡️Pantalla-Drill Through <h5>
   <img width="800" height="400" alt="INFORME 6_DRILL THROUGH" src="https://github.com/user-attachments/assets/aedee43a-6b8b-4e6a-a9c0-976b3db93c46" />
  <h4>🔴Informe 7<h4>
   <h5>➡️Pantalla <h5> 
   <img width="800" height="400" alt="INFORME 7" src="https://github.com/user-attachments/assets/10afde1a-e92b-4806-b8af-f85534c75a96" />
    <h5>➡️Pantalla-Selección <h5> 
   <img width="800" height="400" alt="INFORME 7_SELECCION" src="https://github.com/user-attachments/assets/14a4d5bb-1cac-4f2b-bf91-b05fbc800bad" />
    <h5>➡️Pantalla-Drill Through <h5>
   <img width="800" height="400" alt="INFORME 7_DRILL THROUGH" src="https://github.com/user-attachments/assets/2ab816dd-92f9-4e5b-9418-ff1cfc5ceb29" />
  <h4>🔴Informe 8<h4>
   <h5>➡️Pantalla <h5> 
   <img width="800" height="400" alt="INFORME 8" src="https://github.com/user-attachments/assets/a14f5c78-b793-4b45-ae17-0035292d8f72" />
    <h5>➡️Pantalla-Selección <h5> 
   <img width="800" height="400" alt="INFORME 8_SELECCION" src="https://github.com/user-attachments/assets/654b98d6-a239-4f93-92ab-a3257e7445ba" />
    <h5>➡️Pantalla-Drill Through <h5>
   <img width="800" height="400" alt="INFORME 8_DRILL THROUGH" src="https://github.com/user-attachments/assets/2d5fa5b6-246e-4cdc-b5ad-75dcb5acb164" />
  <h4>🔴Informe 9<h4>
   <h5>➡️Pantalla <h5> 
   <img width="800" height="400" alt="INFORME 9" src="https://github.com/user-attachments/assets/a2cd062a-ea4d-493c-a936-a52f779d96e0" />
    <h5>➡️Pantalla-Selección <h5> 
   <img width="800" height="400" alt="INFORME 9_SELECCION" src="https://github.com/user-attachments/assets/4f549205-3e1d-4984-a49f-503f65deab52" />
   <h5>➡️Pantalla-Drill Through <h5>
   <img width="800" height="400" alt="INFORME 9_DRILL THROUGH" src="https://github.com/user-attachments/assets/c493a1ed-d38f-4566-b8cd-5882fa29d702" />
  <h4>🔴Informe 10<h4>
   <h5>➡️Pantalla <h5> 
   <img width="800" height="400" alt="INFORME 10" src="https://github.com/user-attachments/assets/21ded5f0-483d-4efb-a512-871eb13f3bbd" />
    <h5>➡️Pantalla-Selección <h5> 
   <img width="800" height="400" alt="INFORME 10_SELECCION" src="https://github.com/user-attachments/assets/4ae2c779-e1af-4546-9206-8bbb5efdcbb7" />
   <h5>➡️Pantalla-Drill Through <h5>
   <img width="800" height="400" alt="INFORME 10_DRILL THROUGH" src="https://github.com/user-attachments/assets/c6eea698-f83f-48e9-acab-e06c71a11de9" />

  # Conlusión
<p>
  La construcción de esta aplicación marca un avance significativo para <strong>Forma Retail S.A.</strong>, al permitir centralizar y simplificar procesos clave como la gestión de presupuestos y facturación en un entorno digital unificado.
</p>
<p>
  Más allá de la digitalización, el diseño y desarrollo de las pantallas se convirtieron en un ejercicio clave para comprender mejor la lógica del negocio, estructurar los flujos de trabajo y asegurar que cada módulo aporte valor práctico a los usuarios.
</p>
<p>
  Con una capa de presentación soportada en <strong>Power BI</strong> y procesos automatizados con herramientas del ecosistema Microsoft, la solución no solo incrementa la eficiencia diaria, sino que sienta las bases para escalar con el mismo ritmo de expansión que caracteriza a los clientes estratégicos de la empresa.
</p>

<h2>🎯 Logros alcanzados</h2>
<p>
  Entre los principales logros alcanzados destacan la optimización de los procesos internos y la mejora en la experiencia de los usuarios que gestionan presupuestos y facturación.
</p>
<ul>
  <li>➡️ La reducción del tiempo de elaboración de presupuestos, pasando de un proceso manual y fragmentado a uno dinámico y centralizado.</li>  
  <li>➡️ La trazabilidad completa entre presupuesto y factura, garantizando coherencia y minimizando inconsistencias.</li>  
  <li>➡️ La integración con el ecosistema Microsoft, lo que facilita la escalabilidad y el uso de herramientas ya adoptadas por la organización.</li>  
  <li>➡️ El empoderamiento de los usuarios mediante pantallas intuitivas y reportes visuales que simplifican la gestión y el seguimiento.</li>  
</ul>





   



   


   





   

