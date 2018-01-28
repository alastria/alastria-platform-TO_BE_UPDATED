# Reference architecture of a blockchain
![](https://docs.google.com/drawings/d/e/2PACX-1vQnYqNAfekzwVrKIwAkchLN2D9m99WJdeZNpjgm2xxN_4cldvGrVAgG7QIaW_JN0A0UVnWzC9QobB9W/pub?w=1130&h=660)

![](https://docs.google.com/drawings/d/e/2PACX-1vT93ch52Ep-6YkqFiOZpPRUyv5-fDhEwki9itMILAAg6_g3ZF0DaSRu4pGUBc3-z_OudckU4j4Vr_v5/pub?w=1071&h=798)

# Technical Architecture

1. ARQUITECTURA TÉCNICA
    1. General
        1. Plataforma
        2. Estructura
        3. Arquitectura Lógica Nodos
        4. Capa de comunicación
        5. Capa de Servicios
        6. Capa de Datos
        7. Capa de Conectividad
        8. Puertos conocidos

    1. Entornos

        1. Entorno Desarrollo (descripción/características)
        1. Equipo (máquina) de desarrollo (recomendaciónes)
        1. Proceso de desarrollo
        1. Proceso de Pruebas (descripción/características)
        1. Entornos Preproducción/Producción (descripción/características)
        1. Acceso usuario
        1. Estimación del Sizing Nodos por tipos de nodo
        1. Base de datos
        1. Almacenamiento
        1. Servidor de aplicaciones
        1. Alta disponibilidad

1. ARQUITECTURA DE SEGURIDAD
    1. General
        1. Roles
        2. Seguridad acceso a Fuentes de Datos
        3. Configuración de cifrado
        4. Almacén de Credenciales
        5. Seguridad transacciones
        6. Datos - Cifrado
        7. Datos - Privacidad
        8. Datos - Auditoría
        9. Red - Autenticación
        10. Red - Gestión
        11. Red - Autorizaciones
        12. Puertos conocidos
        13. Bastionado de equipos y electrónica de red
        14. Filtrado de tráfico

    1. Certificados
        1. Gestión de certificados
        2. Autoridad de Certificación
        3. Firma Digital de documentos
        4. Certificados para Servidores Web

1. ARQUITECTURA DE INTEGRACION
    1. Interacción de Alastria con sistemas backend/core de negocio
    2. Interacción de Alastria con otras redes (interoperabilidad)
    3. Interacción de Alastria con otros servicios (por ejemplo almacenamiento)
    4. Interacción con otras tecnologías
    5. Conexiones con Bases de Datos (por ejemplo cache de transacciones)
    6. APIs para acceder a los servicios proporcionados
    7. Protocolos de conexión/integración Soportados
    8. Intercambio de Ficheros (por ejemplo de configuración de los nodos)

1. ARQUITECTURA DE DESARROLLO
    1. General
        1. Estructura de Aplicaciones/smart contract
        2. Lenguaje de desarrollo
        3. Metodología de Desarrollo
        4. Modelo de Datos
        5. Interfaz de usuario
        6. Tecnologías de Creación de Interfaz de Usuario
        7. Control de Versiones
        8. Paso entre entornos
        9. Jobs

    1. Pruebas
        1. Unitarias de nodo
        1. Integradas de nodo
        1. Integradas de red
        1. Stress de nodo
        1. Stress de red
        1. Seguridad

1. INSTALACIÓN Y CONFIGURACIÓN DE NODOS
    1. Requerimientos previos a la instalación
    1. Instalación de Nodo Alastria
    1. Descarga de los componentes
    1. Instalación de los componentes
    1. Asignación de Roles
    1. Alta del nuevo nodo en Validadores o Regulares
    1. Conectividad con Nodos de terceros

1. POLITICA DE DESPLIEGUE Y MANTENIMIENTO
    1. Despliegue
        1. Tareas previas de despliegue
        2. Gestión de incidencias
        3. Gestión Incidencias de Usuario
        4. Gestión Incidencias de Producto
        5. Políticas de actualización
        6. Aplicación de parches
        7. Plan de cambio de versión

    1. Operación
        1. ANS e Indicadores de operación
        2. Procedimientos de Back Up

    1. Procedimientos rutinarios
        1. Logs: Revisión/Protección/Retención
        2. Auditoria

    1. Monitorización
        1. Monitorización común en los elementos de red
        2. Monitorización de la capacidad de los recursos
        3. Monitorización de la disponibilidad
        4. Transferencia de ficheros
        5. Conexiones B2B
        6. Certificados digitales
        7. Servidores Web
        8. Conexiones de usuarios desde el exterior
        9. Servidores y Electrónica de Red
        10. Control de acceso
        11. Acceso de administración a los SSII
        12. Usuarios especiales
        13. Entorno LAN
        14. Informes de gestión de vulnerabilidades
