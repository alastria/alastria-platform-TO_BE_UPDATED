# Descripción general

![](https://docs.google.com/drawings/d/e/2PACX-1vSdVgHvuVzWEtgSywNZ9YwgWa5rAfv-6TYz0wCYq26TLjFDXZo1d2Ziop8Mb8I6-9aP0u1QGp0fVzN7/pub?w=748&h=557)

* ~15-20 nodos validadores, que además actúan como “bootnodes” para todos los nodos regulares (como configuración inicial)
* Nodos validadores en régimen de alta disponibilidad, 24/7
* Los nodos validadores no deben utilizarse para conectar sistemas corporativos, ni para desplegar aplicaciones distribuidas ni interaccionar con ellas
* No es obligatorio desplegar un nodo validador para los miembros de Alastria - se puede participar igualmente de la red mediante un nodo regular

### … pero se admiten voluntarios ;-)

# Anatomía de un nodo regular

<p align="center">
  <img src="https://docs.google.com/drawings/d/e/2PACX-1vQW5h-DG1WTO2dm19VDm7XdYFlQrdQqozXwK4IN61T3JAQJ2iikaCD4HZ9T-8PYqK8FYsH8C7-_DmXx/pub?w=341&h=459" />
</p>

Cada nodo regular de la red de Alastria deberá desplegar tres procesos fundamentales, en uno o varios servidores:
* **Quorum**, que constituye el cliente ethereum de base
* **Constellation**, que implementa el gestor y repositorio de transacciones privadas
* **Monitor**, que es una utilidad de monitorización creada por el equipo técnico de Alastria

Para ello, se deberán permisionar la conectividad a los siguientes puertos:
* **21000** TCP/UDP, como entrada desde los nodos validadores, para el protocolo estándar de Ethereum de base
* **9000** TCP, como entrada y salida, con otros nodos con los que se implementen aplicaciones distribuidas privadas
* **TBD**, para la utilidad de monitorización (que además necesitará el puerto RPC local de geth)

Los nodos regulares utilizarán un fichero “permissioned-nodes.json” que deberá incluir únicamente a los nodos validadores

# Anatomía de un nodo validador

<p align="center">
  <img src="https://docs.google.com/drawings/d/e/2PACX-1vT4bfJFyDc1OUp7VwUx5eB0UYp6Yk3b_NCDQFMnuo7HBpHSXi-4-qqt7Z9Q3r8x4LysD1oy01O81SSd/pub?w=336&h=462" />
</p>

Cada nodo validador de la red de Alastria deberá desplegar dos procesos fundamentales, en uno o varios servidores:
* **Quorum**, que constituye el cliente ethereum de base
* **Monitor** (de nodo validador), que es una utilidad de monitorización creada por el equipo técnico de Alastria
(los nodos validadores no implementan Constellation, ya que no se usan para desplegar aplicaciones)

Para ello, se deberán permisionar los siguientes puertos:
* **21000** TCP/UDP, como entrada y salida para todos los nodos de la red
* **TBD**, para la utilidad de monitorización (que además necesitará el puerto RPC local de geth)

Los nodos validadores utilizarán un fichero “permissioned-nodes.json” que incluye a todos los nodos de la red (tanto validadores como regulares)

# Configuraciones mínimas de los nodos

La definición de las especificaciones detalladas está en proceso, pero la siguiente descripción da una orientación.

## Nodos regulares: configuración mínima recomendada
* 4 CPU cores
* 32 Gb RAM
* 100 Gb SSD
* Red Hat >= 7.0

## Nodos validadores: primeras ideas de SLA
* Servidores más potentes: 8 CPU cores, 128 Gb RAM, 1 Tb SSD; Red Hat >= 7.0
* Alta disponibilidad, 24/7
* Respuesta a peticiones de actualización en 24 horas (permisionamiento de nodos e IP:puertos, actualización de versiones, etc.)
* Mantenimiento del histórico completo del blockchain público (sin “tree prunning”)
* Compromiso indefinido de mantenimiento del nodo validador, pudiendo darse voluntariamente de baja con un preaviso de un mes

***
Siguiente: [Roadmap técnico de la plataforma de Alastria](https://github.com/jesus-alastria/alastria-node/wiki/Roadmap-t%C3%A9cnico-de-la-plataforma-de-Alastria)
