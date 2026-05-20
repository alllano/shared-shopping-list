# 🛒 MarketSync

**MarketSync** es una aplicación móvil diseñada para simplificar y optimizar la gestión de compras de mercado en entornos compartidos (como grupos familiares o comunidades), conectando las necesidades de los usuarios con un flujo de administración y consolidación logística en tiempo real. 

Este proyecto fue desarrollado como parte de mi portafolio profesional para demostrar habilidades avanzadas en arquitectura móvil, sincronización de datos y optimización de recursos en la nube.

---

## 🚀 Características Principales

### 👤 Para Usuarios (Módulo Familiar)
*   **Gestión Multi-inquilino (Familias):** Los usuarios se agrupan en núcleos familiares para armar listas de mercado colaborativas, manteniendo la privacidad y separación total entre diferentes familias.
*   **Modo Offline-First:** Los usuarios pueden buscar productos, clasificar por categorías y armar su mercado sin conexión a internet. La aplicación gestiona los datos localmente y sincroniza de forma transparente al recuperar la red.
*   **Sugerencia de Productos:** Si un producto no existe en el catálogo, el usuario puede proponer su creación (quedando en estado *pendiente* hasta la revisión del administrador).
*   **Plantillas Reutilizables:** Permite duplicar listas de periodos anteriores para agilizar el proceso de compra mensual o quincenal, permitiendo solo editar las variaciones.

### 👑 Para el Administrador (Módulo de Control y Logística)
*   **Consolidación Inteligente (Totales Globales):** El administrador puede visualizar un resumen consolidado de las cantidades de productos solicitadas por *todas* las familias antes de ir a la tienda.
*   **Flujo de Despacho en Dos Pasos:**
    1.  **Fase de Compra:** Control para tachar los productos masivos que ya se adquirieron en las tiendas físicas.
    2.  **Fase de Separación:** Desglose interactivo por familia para empaquetar y distribuir las cantidades exactas correspondientes a cada pedido.
*   **Auditoría Digital:** Herramienta para registrar y almacenar imágenes de las facturas físicas de las compras.
*   **Analítica de Precios:** Gráficos interactivos con el histórico de variación de precios por producto y por tienda a lo largo del tiempo.

---

## ⚡ Enfoque Técnico y Buenas Prácticas

Este proyecto va más allá de un CRUD tradicional, implementando soluciones a retos reales de ingeniería de software:

*   **Sincronización Delta Eficiente:** Para mitigar el consumo de datos y batería, el dispositivo local no descarga todo el catálogo en cada sesión; solo solicita al servidor los registros modificados a partir de su última marca de tiempo (*Timestamp*).
*   **Inmutabilidad Histórica:** El precio de los productos se congela en el detalle de cada pedido al momento de la confirmación. Esto garantiza que las métricas financieras del usuario no se alteren si el administrador modifica los precios del catálogo en el futuro.
*   **Optimización de Almacenamiento:** Las imágenes de las facturas pasan por un proceso de compresión en el dispositivo móvil antes de ser subidas a un almacenamiento de objetos en la nube, guardando únicamente URLs optimizadas en el servidor para mantener la agilidad de las consultas.
*   **Notificaciones en Tiempo Real:** Implementación de eventos y notificaciones *Push* automáticas para alertar a los usuarios cuando el administrador ha procesado su mercado o actualizado los totales de su cuenta.
