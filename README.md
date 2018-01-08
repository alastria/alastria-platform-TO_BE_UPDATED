# Grupo de Trabajo de Plataforma Alastria

1. OBJETIVOS Y ALCANCE DE ESTE DOCUMENTO

1. INTRODUCCIÓN

    1. [Introducción a Alastria](Introduccion/Introduccion-a-Alastria.md)
    2. [Tecnologías a utilizar](Introduccion/Tecnologias-a-utilizar.md)
    3. [Arquitectura de la red blockchain de Alastria](Introduccion/Arquitectura-de-la-red-blockchain-de-Alastria.md)
    4. [Roadmap técnico de la plataforma de Alastria](Introduccion/Roadmap-tecnico-de-la-plataforma-de-Alastria.md)
    5. [Cómo nos organizamos](Introduccion/Como-nos-organizamos.md)
    6. [Alguna información útil](Introduccion/Alguna-informacion-util.md)

1. REQUERIMIENTOS DE LA PLATAFORMA

    1. Requerimientos generales
        1. Basado en software OpenSource de amplia aceptación en el mercado
            1. No se desarrolla un blockchain en Alastria
            1. No se admiten componentes propietarios
            1. Plataforma construida por comunidades OpenSource lo más grandes y diversas posible
        1. Ecosistema de usuarios del software lo más amplia posible
            1. Ecosistema de desarrolladores usuarios del software lo más amplio posible
            1. Ecosistema de aplicaciones usando el software lo más amplio posible
            1. Ecosistema de conocimiento sobre la plataforma lo más amplio posible
        1. Basado en plataformas de propósito general y multi-industria
        1. Permitir y facilitar el cumplimiento regulatorio por parte de los asociados, en concreto:
            1. Reglamento General de Protección de Datos (RGPD)
            2. Ley de Servicio de Sociedad de la Información y Comercio Electrónico (LSSI)
            3. Reglamento de prevención del blanqueo de capitales y de la financiación del terrorismo
            4. Normas y recomendaciones del Consejo Nacional de Ciberseguridad
            6. Otros

    1. [Requerimientos Técnicos](Requerimientos(Requerimientos-tecnicos.md))
        1. Privacidad
            1. Privacidad de la actividad transaccional
            1. Privacidad de los datos
        1. Tolerancia a fallos
            1. Byzantine Fault Tolerance
            2. Mecanismo modular de modificar algoritmos de consenso
        1. Rendimiento
            1. Alrededor de 1.000 tx/s
            2. Sin degradación de rendimiento por sobrecarga
            3. Capacidad computacional para validación de bloques independiente del tiempo o tamaño del Blockchain
            4. Tiempo requerido para acceso a datos del blockchain constante
            5. Soporta "Pruning" del Blockchain, para facilitar "clientes ligeros"
        1. Settlement Finality
            1. "Transaction finality" debe ser determinista y considerada final en un solo bloque
        1. Sin criptomonedas embebidas: costes de transacción cero
        1. Anti-spam
            1. Mecanismo anti-spam para proteger la red de nodos y direcciones que generan excesiva carga
            2. Mecanismo para parar rápidamente a entidades iniciando transacciones por encima de un nivel determinado
        1. Permisionado
            1. Permisionado de nodos individuales y de direcciones de participantes
            2. Whitelist y blacklist de nodos y direcciones de participantes
        1. Maximizar la descentralización, a pesar de ser una red permisionada
        1. Conectividad entre nodos
            1. Minimizar las necesidades de conectividad directa punto a punto entre los nodos participantes de la red
            2. Minimizar las necesidades de conectividad directa punto a punto entre los nodos participantes en transacciones y contratos privados
        1. Sincronización y Disaster Recovery
            1. Mecanismo de sincronización rápida del blockchain para nodos que se conectan por primera vez, tanto de la parte pública como de la privada
            2. Mecanismo que permita inicializar un nodo nuevo a partir del backup de otro nodo, hasta un bloque determinado

1. ARQUITECTURA TÉCNICA
    1. General
        1. Plataforma
        2. Estructura
        3. Arquitectura Lógica Nodos
        4. Capa de comunicación
        5. Capa de Servicios de Negocio
        6. Capa de Agregación, Transformación y persistencia de Datos
        7. Capa de Conectividad
        8. Puertos conocidos
    1. Entornos
        1. Entorno Desarrollo/ descripción/características
        2. Equipo de desarrollo (PC)
        3. Entorno Preproducción/descripción/características
        4. Entorno Producción/descripción/características
        5. Acceso usuario
        6. Estimación del Sizing Nodos --> Necesario para los diferentes socios que quieren desplegar un nodo
        7. Base de datos
        8. Almacenamiento
        9. Servidor de aplicaciones
        10. Alta disponibilidad

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
    3. Interacción de Alastria con otros servicios
    4. Interacción con otras tecnologías
    5. Conexiones con Bases de Datos
    6. APIs --> a partir de los servicios
    7. Protocolos de conexión/integración Soportados
    8. Intercambio de Ficheros

1. ARQUITECTURA DE DESARROLLO
    1. General
        1. Estructura de Aplicaciones/smart contract
        2. Lenguaje de desarrollo
        3. Metodología de Desarrollo
        4. Modelo de Datos
        5. Interfaz de usuario -->  tiene sentido?
        6. Tecnologías de Creación de Interfaz de Usuario --> Tiene sentido?
        7. Control de Versiones
        8. Paso entre entornos
        9. Jobs

    1. Pruebas
        1. Unitarias
        2. Integradas
        3. Stress
        4. Seguridad

1. INSTALACIÓN Y CONFIGURACIÓN DE NODOS
    1. Requerimientos previos a la instalación
    2. Instalación de Nodo Alastria
    3. Descarga de los componentes
    4. Instalación de los componentes
    5. Asignación de Roles
    6. Conectividad con Nodos de terceros

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

1. GLOSARIO DE TÉRMINOS
