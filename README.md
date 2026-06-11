# 1. Nombre de la aplicación
SkullGamer AI

# 2. Descripción del problema
En el mercado local de insumos de tecnología y hardware, los pequeños comercios y técnicos independientes suelen gestionar la atención y sus presupuestos de forma completamente manual a través de aplicaciones de mensajería como WhatsApp. Envían catálogos en archivos estáticos (PDF o Excel) que quedan obsoletos rápidamente debido a la constante variación de precios. Esto provoca una saturación de consultas repetitivas de los usuarios sobre compatibilidad de componentes (procesadores, placas madre, placas de video, memorias, almacenamiento y gabinetes) o recomendaciones para ejecutar software específico, ralentizando la atención y provocando la pérdida de clientes potenciales por falta de respuestas dinámicas.

# 3. Usuario objetivo
* **Clientes / Entusiastas del Hardware**: Usuarios que necesitan armar una computadora completa desde cero o actualizar sus componentes de forma óptima según sus necesidades específicas de juego o presupuestos acotados.
* **Comerciantes / Técnicos de PC locales**: Pequeños negocios que buscan automatizar la etapa inicial de asesoramiento y filtrado de stock para agilizar las ventas.

# 4. Solución propuesta
**SkullGamer AI** es una plataforma web Full-Stack que funciona como un asistente inteligente de hardware. Integra un modelo de Inteligencia Artificial (Gemini 2.5 Flash) configurado a través de un servidor backend. El sistema actúa como un técnico virtual interactivo: interpreta los requisitos del cliente (presupuesto disponible o juegos/programas que desea ejecutar) y genera al instante un presupuesto personalizado completo, sumando de forma exacta los costos de los componentes en stock (incluyendo CPU, GPU, Motherboard, RAM, SSD, Gabinete y Fuente) y garantizando la compatibilidad técnica.

# 5. Demo o prototipo
La propuesta cuenta con un prototipo funcional interactivo e integrado. Se adjunta la URL de despliegue generada y capturas de pantalla de la interfaz de usuario en producción, donde se documenta un flujo real en el que un cliente solicita una configuración de $600 USD para correr juegos como Red Dead Redemption 2, Valheim y League of Legends a 1080p, recibiendo asesoramiento inmediato basado en las existencias del comercio.

*(Aquí sumás tu captura de pantalla de la interacción y el enlace que te dé Vercel o GitHub).*

# 6. Funcionalidades construidas
* **Interfaz Gamer Inmersiva**: UI desarrollada con modo oscuro de alto contraste y acentos en rojo carmesí para conectar con el público objetivo.
* **Control Remoto de Contexto (System Instructions)**: Configuración del backend que restringe las respuestas del modelo para que se limite estrictamente al catálogo oficial.
* **Presupuestador Automatizado Integral**: Capacidad de procesar los precios del hardware y devolver cálculos precisos sumando mothers, micros, discos, etc., mostrando el monto total acumulado.
* **Filtro Semántico por Perfil de Uso**: El asistente procesa el lenguaje natural del usuario y determina qué componentes mitigan cuellos de botella según el juego solicitado.

# 7. Herramientas utilizadas
* **Project IDX**: Entorno de desarrollo en la nube utilizado para codificar el espacio de trabajo.
* **Google AI Studio / Gemini API**: Para la generación de la clave de acceso segura (GEMINI_API_KEY) y el consumo del modelo de lenguaje en el servidor.
* **Vite & React / HTML / JS**: Para la estructura, estilos y dinamismo de la interfaz de chat en el Frontend.
* **Node.js & Express**: Framework del lado del servidor empleado para canalizar las consultas de la API de forma segura mediante variables de entorno (.env).
* **Vercel & GitHub**: Herramientas utilizadas para el control de versiones y el despliegue de la aplicación web en producción.

# 8. Conceptos vistos en clase que fueron aplicados
* **Frontend**: Diseño de pantallas responsivas, contenedores de chat adaptativos y manejo de estados visuales para la interacción del usuario.
* **Backend**: Arquitectura de servidor con Express para gestionar peticiones HTTP POST de manera segura y proteger las credenciales privadas.
* **Variables de Entorno y Seguridad**: Uso de archivos `.env` para la inyección en tiempo de ejecución de claves de API, separando la configuración del código fuente.
* **Gestión de Datos**: Modelado de un catálogo estructurado de hardware (dividido por categorías de componentes con sus respectivos precios en USD) para simular la persistencia y control de inventario.

# 9. Limitaciones actuales
* Los datos de stock y precios están acoplados al prompt del sistema en el servidor, lo que significa que el comerciante debe editar el código fuente si cambian los valores.
* No cuenta con conexión en tiempo real a una base de datos externa persistente (como MongoDB) para automatizar el inventario.
* La versión actual carece de un sistema de login/registro (Auth) para guardar el historial de presupuestos de los clientes.

# 10. Posibles mejoras futuras
* **Persistencia con MongoDB**: Migrar el catálogo estático del servidor hacia una base de datos NoSQL para permitir actualizaciones dinámicas desde un panel administrador.
* **Módulo de Autenticación**: Incorporar inicio de sesión seguro para separar el flujo de los clientes del panel de gestión del técnico.
* **Integración de Cierre de Venta (API WhatsApp)**: Agregar un botón automatizado que recopile el desglose final generado por la IA y lo envíe estructurado en un solo clic al WhatsApp del local para consolidar la compra instantáneamente.
