# Alastria es una asociación agnóstica con respecto a la tecnología
* Y además es importante entender que las tecnologías de blockchain se encuentran en plena evolución, y seguramente no 100% preparadas para su uso a nivel “enterprise”
* Como comienzo, Alastria ha desplegado una primera red (testnet) de tipo Ethereum utilizando la tecnología de Quorum, y la complementará con una red de producción (mainnet) paralela
* A futuro, es previsible que Alastria despliegue nuevas redes en otras tecnologías, tanto de tipo Ethereum (e.g. Parity, Clearmatics) como de otro tipo (e.g. Hyperledger Fabric). Para ello será crucial la involucración activa de más miembros de Alastria

# Introducción a Quorum
* Un fork “lightweight” de geth => compatibilidad total con ethereum
* Basado en algoritmos de consenso, en lugar de “proof of work” => mejores prestaciones (~800 tx/s), sin “forks” en la cadena
* Diseñado para construir redes permisionadas, en las que los participantes son conocidos y tienen reputación
* Sin una criptomoneda intrínseca, aunque manteniendo el concepto de “gas”
* Adicionalmente a geth se añade constellation, un sistema para almacenar y ejecutar smart contracts privados
Implementando ZSL, un sistema de “zero-knowledge proofs”, que permite ofuscar los datos numéricos de los smart contracts

Hay mucha más información sobre Quorum en su Github: [Quorum](https://github.com/jpmorganchase/quorum)

# Algoritmos de consenso en Quorum
### QuorumChain
Nodos “blockmakers” que proponen bloques y “voters” que votan su validez según un quorum (no BFT)
### RAFT
Nodo “leader” elegido por consenso que propone bloques (no BFT)
### Istambul
Nodo “proposer” designado por rotación en modo round-robin entre una serie de nodos “validators”, que comprueban la validez de los bloques (BFT)

![](https://docs.google.com/drawings/d/e/2PACX-1vQi7KLyyOJvYTYXxSdkR-adG-6OkMVMqunwrFWha3huX_UBtMYjMfPqzpn7Hqu52HnMoModiSoonis4/pub?w=496&h=403)

# Modelo de permisionamiento en Quorum
![](https://docs.google.com/drawings/d/e/2PACX-1vTKAjcYE_wY8wqhOQ9h23gdiWGPRFJJbSIcG4VZCFStmWx0GR7OG_F2oZyByoGJ9MGxdWjBvTReIN3c/pub?w=493&h=325)

* Los nodos se identifican por su “enode”, su IP pública y su puerto
* Cada nodo de Quorum especifica los nodos que permite que se conecten a él a través del fichero “permissioned-nodes.json”
* Por tanto, el modelo actual de permisionamiento de Quorum se basa en nodos, no en “addresses”
* Es habitual disponer de un conjunto de “bootnodes” oficiales, que mantengan la lista oficial de enodos permisionados

```
[
"enode://5afe866a3dbff3cd8f12a0553da765c60a54eedc018df7aa8376ae923d59fedd2ae9d0252b26a7d254b04d941d338949103ef9f41c6f421fc11ba0d7d5da0e21@52.18.188.91:8002",
"enode://f00aa65a8e547bb5f2bb382aa857591e4bb2bd80421554984b248c46370c03e2a4c97d011748ba7db24d646a1ebde56f1316307901fbfe71ff00b90f2f90299d@52.14.141.30:8002",
"enode://efe68efb0126767b015f1a04813561b019f64c5fe36f957bd66a5e60f4c94c82a5ad79d70aa96064b672ba60da89a3f695361eb56d6d1fdf97b1e5693135e2ef@52.5.9.18:8002"
]
```
# Ether y Gas en Quorum
### Gas
Es una medidaa de la carga de computación al realizar cualquier transacción en la red de blockchain que consuma recursos (ciclos de la máquina virtual, espacio de memoria).

El protocolo establece límites de gas por transacción y por bloque, de forma que la red está protegida ante cargas de trabajo excesivas (e.g. un bucle infinito).

### Ether
Es la criptomoneda nativa de la red de ethereum, utilizada para pagar por el gas consumido al ejecutar transacciones o alocar recursos en la red distribuida.

### Cost of Gas
Es la medida que relaciona ambas magnitudes, expresada en unidades de ether por unidad de consumo de gas

Quorum mantiene el concepto de gas y los límites por transacción y por bloque, pero establece de forma forzada un cost of gas = 0

De esta forma, las transacciones no cuestan ether, pero se mantiene la protección del sistema.

Hasta la versión 2.0.0 era necesario tener un balance positivo de ether en una dirección (“address”) para poder enviar transacciones desde ella - por lo que era preciso prealocar ether y enviarlo a las direcciones a utilizar. Pero no a partir de la versión 2.0.0

# Quorum: roadmap
* Mejor modelo de permisionamiento, idealmente controlado por smart contracts:
    * Sin posibilidad de re-permisionamiento
    * Tanto a nivel de nodo como a nivel de address
* Mecanismos de anti-spam, e.g. con cost of gas > 0
* Transmisión de transacciones privadas (Constellation) por mecanismo de “gossiping” (i.e. utilizando nodos “relay” para no necesitar abrir puertos entre peers)
* Nuevos modelos de privacidad (e.g. ring signatures, address obfuscation)
* Mecanismos de mensajería segura
* Mecanismos de almacenamiento de ficheros

**Roadmap en proceso de ser consensuado, en el ámbito de la Enterprise Ethereum Alliance** (equipo “core” de Alastria en contacto directo)


***
Siguiente: [Arquitectura de la red blockchain de Alastria](https://github.com/jesus-alastria/alastria-node/wiki/Arquitectura-de-la-red-blockchain-de-Alastria)
