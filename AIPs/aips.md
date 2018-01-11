# Alastria Improvement Proposals (AIPs)
Para cualquier propuesta de mejora sobre la plataforma de Alastria,
y para tener un seguimiento de en qué se encuentra trabajando el
grupo de trabajo se crean los AIPs (equivalentes a EIPs de Ethereum).

## ¿Qué es un AIP?
Un Alastria Improvement Proposal es un documento de diseño a través
del cual cualquiera puede proponer mejoras sobre la plataforma. El documento
debe incluir una breve descripción sobre la mejora, así como una ligera idea
sobre el contexto y como se quiere implementar la misma. Esto abrirá un
espacio de discusión entre toda la comunidad sobre la importancia y mejor
forma de implementarla. El equipo de trabajo con ayuda del comité técnica
priorizará y aceptará las mejoras a implementar

## Estados de un AIP
Un AIP tendrá los siguientes estados:

* *Draft* - AIP abierta para discusión y consideración.
* *Acccepted* - AIP planeada para implementación e inclusión en la próxima versión.
* *Final* - AIP aceptada y ya implementada.
* *Deferred* - AIP que no se considera para adopción inmediata pero se mantiene para el futuro
* *Dismissed* - AIP desestimada

## ¿Como crear una AIP?
Para crear una AIP, debe seguirse la es estructura de la plantilla incorporada
en este repositorio en el directorio AIPs (aips/template.md). Se presentan
todas las secciones que idealmente deberá tener un AIP, pero inicialmente puede incluir
simplemente una breve descripción y rellenar el resto de las secciones con ayuda de la
comunidad.

Cogiendo la plantilla como base debe abrirse una issue por cada nuevo AIP.
En un primer momento estará en estado *Draft*. Aquí comienza toda la discusión
asociada al AIP. Una vez llegado a consenso y aceptada el AIP *Accepted*,
comienza su implementación. Una vez implementado e incluido a la nueva versión
de la plataforma será *Final*. Si la comisión técnica considera que una
mejora no es prioritaria se mantendrá en *Deferred* y las que no aplican como
*Dismissed*. A partir del estado *Accepted*, el AIP se incluirá en una carpeta
independiente en el directorio AIPs con toda la documentación del mismo y se cerrará
la issue.

## Categorías de AIPs
Inicialmente se definen las siguientes categorías:
* *Core*: Mejoras core a la plataforma (Quorum, blockchain, arquitectura, etc.)
* *Node*: Mejoras sobre todas las tecnologías relacionadas con el nodo (ficheros, script, APIs )
* *Monitor*: Mejoras sobre el sistema de monitorización 
* *DNA (Decentralized Network Administration)*: Mejoras sobre el sistema descentralizado de administración de redes
* *Identity*: Mejoras sobre el sistema de identidad soberana
* *Doc*:  Mejoras sobre la documentación.