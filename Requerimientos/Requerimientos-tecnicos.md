# 1. Privacidad

## 1.1 Privacidad de la actividad transaccional
Los asociados que participen en contratos o transacciones privadas deben tener total privacidad de su actividad respecto al resto de los asociados. Es decir, que un asociado no debe poder ver la actividad de ningún otro asociado si no participa de la actividad con ese otro asociado. Este punto no se refiere solo a la visibilidad de los datos, sino también a la actividad transaccional.

## 1.2 Privacidad de los datos
La privacidad de los datos para aplicaciones blockchain es un tema complejo

### 1.2.1 No deben almacenarse datos PII (Personally identifiable information) en el Blockchain

### 1.2.2 Hay que definir arquitectura de referencia de almacenamiento de datos
Hay datos que se pueden guardar en dispositivos móviles propiedad del usuario
Hay datos que se pueden guardar en sistemas como Constellation de Quorum.
Hay datos que se pueden guardar en sistemas distribuidos de almacenamiento sin control de acceso como IPFS
Hay datos que se pueden guardar en sistemas con control de acceso como WebDAV
Hay datos que se deben guardar en sistemas actuales que actúan de custodio (eg. datos bancarios, de salud, etc)

# 2. Tolerancia a fallos

## 2.1 Byzantine Fault Tolerance
El sistema debe tolerar ataques debidos a un cierto número (limitado) de nodos y participantes que se comportan malignamente de manera deliberada

## 2.2 Mecanismo modular de modificar algoritmos de consenso
Los algoritmos de consenso están evolucionando muy rápidamente en el mercado. El sistema debe poder incorporar fácilmente los nuevos algoritmos que aparezcan, si se consideran adecuados para las necesidades de Alastria.

# 3. Rendimiento
    1. Alrededor de 1.000 tx/s
    2. Sin degradación de rendimiento por sobrecarga
    3. Capacidad computacional para validación de bloques independiente del tiempo o tamaño del Blockchain
    4. Tiempo requerido para acceso a datos del blockchain constante
    5. Soporta "Pruning" del Blockchain, para facilitar "clientes ligeros"


# 4. Settlement Finality
    1. "Transaction finality" debe ser determinista y considerada final en un solo bloque


# 5. Sin criptomonedas embebidas: costes de transacción cero


# 6. Anti-spam
    1. Mecanismo anti-spam para proteger la red de nodos y direcciones que generan excesiva carga
    2. Mecanismo para parar rápidamente a entidades iniciando transacciones por encima de un nivel determinado

# 7. Permisionado
    1. Permisionado de nodos individuales y de direcciones de participantes
    2. Whitelist y blacklist de nodos y direcciones de participantes


# 8. Maximizar la descentralización, a pesar de ser una red permisionada

# 9. Conectividad entre nodos
    1. Minimizar las necesidades de conectividad directa punto a punto entre los nodos participantes de la red
    2. Minimizar las necesidades de conectividad directa punto a punto entre los nodos participantes en transacciones y contratos privados

# 10. Sincronización y Disaster Recovery
    1. Mecanismo de sincronización rápida del blockchain para nodos que se conectan por primera vez, tanto de la parte pública como de la privada
    2. Mecanismo que permita inicializar un nodo nuevo a partir del backup de otro nodo, hasta un bloque determinado
