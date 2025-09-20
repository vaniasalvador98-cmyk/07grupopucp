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

</div>

# Solución de Negocio Cloud con Microsoft Fabric, Power Platform y Power BI
<div style="color:#00796B; font-family: Inter, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial; line-height: 1.5; font-size: 16px;">

  <h2>Solución de Negocio Moderna</h2>

  <p>Este proyecto implementa una arquitectura de datos moderna que integra diversas herramientas para mejorar la gestión, automatización y análisis de la información:</p>

  <ul>
    <li><strong>Microsoft Fabric Warehouse</strong> y <strong>Data Factory</strong> para centralizar, transformar y orquestar los datos empresariales.</li>
    <li><strong>Azure SQL</strong> como base de datos estructurada, confiable y escalable en la nube.</li>
    <li><strong>Power Apps</strong> para crear aplicaciones low-code que agilicen la captura y actualización de datos operativos.</li>
    <li><strong>Power BI</strong> para visualizar indicadores clave y facilitar la toma de decisiones basada en datos.</li>
    <li><strong>Power Automate</strong> para automatizar procesos dentro del flujo de trabajo y aumentar la eficiencia operativa.</li>
  </ul>

</div>

  <h2>Diagrama de la arquitectura de datos</h2>

  <h2>C1:Capa de datos</h2>
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
  A continuación, se presentan las distintas pantallas que conforman la aplicación, junto con su propósito y principales funcionalidades:
</p>
<h4 id="">Pantalla 1: Pantalla de Bienvenida/Inicio</h4>
<img width="1303" height="728" alt="image" src="https://github.com/user-attachments/assets/a4e86d29-b6cc-461a-aaf8-c553049f48c6" />
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
</div>
<h4 id="">Pantalla 2: Pantalla de Buscar Presupuesto</h4>
<img width="1167" height="653" alt="image" src="https://github.com/user-attachments/assets/63a84f64-3ba7-4fc8-8a6a-1d178ec724bc" />
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

</div>
<h4 id="">Pantalla 3: Pantalla Gestionar Presupuestos</h4>
<img width="1314" height="732" alt="image" src="https://github.com/user-attachments/assets/e8c1a910-58a0-42a4-96b1-bbc6956753fa" />
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

</div>
<h4 id="">Pantalla 4: Pantalla Gestionar Presupuesto Detalle</h4>
<img width="1087" height="606" alt="image" src="https://github.com/user-attachments/assets/4f23c548-c687-4139-9bf0-1ca16cb9823e" />


  <h2>C3: Capa de extracción, transformación y carga</h2>
  <h2>C4: Capa de almacén de datos</h2>
  <h2>C5: Capa de presentación</h2>


