# Organización (a efectos de plataforma)
![](https://docs.google.com/drawings/d/e/2PACX-1vS81QkcRyx8O-md-GvWumPxoLbXlRw3psp_FxzzWFIr_pHDNHPHlCoKLikWXkuE0TsdicwWLfEEspga/pub?w=1391&h=566)

### 1. Entidades miembros de Alastria
Despliegan y mantienen sus nodos (validadores y/o regulares) conforme a la política técnica establecida por Alastria; desarrollan y despliegan sus propias aplicaciones distribuidas a través de sus nodos regulares
### 2. Nodos regulares
Se conectan voluntariamente a los nodos validadores (que actúan como “bootnodes”); Permiten el despliegue de aplicaciones distribuídas y el acceso general a la red de blockchain; cumplen las políticas técnicas establecidas por Alastria
### 3. Nodos validadores
Intervienen como validadores (voters / blockmakers) en los algoritmos de consenso de la red de blockchain; mantienen copias integrales del blockchain y toda su historia; actúan como “bootnodes” permitiendo la conexión a los otros nodos, según la lista de nodos permisionados establecida por Alastria; cumplen las politicas técnicas establecidas por Alastria
### 4. Equipo técnico "core" de Alastria
Crea las herramientas básicas de despliegue y monitorización de la red; monitoriza activamente la red y estado de todos sus nodos; gestiona el permisionamiento de los nodos en función de la política técnica establecida; da soporte a la comunidad sobre las cuestiones técnicas de la plataforma
### 5. Comité Técnico de Alastria
Establece la política técnica y la estrategia técnica general de la plataforma; supervisa al equipo técnico “core”, y decide sobre sus propuestas para establecer la arquitectura de red; autoriza a los miembros de la red a desplegar y mantener nodos validadores; decide las actuaciones técnicas a realizar en función de las situaciones que se presenten
### 6. Comité de Resiliencia
Valida las propuestas arquitecturales y supervisa la operativa desde un punto de vista de resiliencia
### 7. Junta directiva de Alastria
Delega en el comité técnico las decisiones referentes a los aspectos técnicos de la red; refrenda las decisiones de carácter estratégico y/o de especial importancia, a su criterio

# Nodos regulares: Normas de participación (a.k.a. adhesión a la política técnica)
**Cada miembro de Alastria que quiera desplegar un nodo regular (no validador) se compromete a:**
* Designar una persona de contacto técnico (“administrador del nodo”), responsable de la administración del nodo de Alastria
* Responder a los requerimientos de actuación técnica que se soliciten desde el equipo técnico “core” de Alastria, en un plazo de 72 horas hábiles como máximo
* Utilizar las versiones de los clientes blockchain especificadas en el repositorio oficial de Alastria, y desplegar y permisionar las herramientas de monitorización que el equipo técnico de Alastria determine
* No permisionar ni permitir conectarse a otros nodos blockchain no autorizados en la lista oficial mantenida por Alastria
* Limitar la carga de la red dentro de los límites establecidos en cada momento dentro de la política técnica, inicialmente 25.000 transacciones al día. Y en caso de necesitar superar este límite, solicitar y obtener una autorización por parte del comité técnico de Alastria a través del canal establecido en dicha política
* Cumplir todas las políticas de Alastria. En concreto la política legal que establece que ningún miembro desplegará ni permitirá el despliegue a través su(s) nodo(s) de aplicaciones, productos o negocios que no cumplan con la regulación y legislación aplicable, o que puedan suponer, a juicio de la junta directiva de Alastria, un riesgo reputacional relevante
* Comunicar inmediatamente al equipo técnico de Alastria las posibles vulnerabilidades que se pudieran encontrar en la plataforma, y no explotarlas en beneficio propio

**En caso de incumplimiento de alguna de estas normas, el equipo técnico de Alastria junto con los nodos validadores procederán al despermisionamiento y consiguiente desconexión del nodo regular, momento en el cual el miembro dueño del nodo podrá solicitar su repermisionamiento al Comité Técnico de Alastria previa presentación de un plan de resolución del problema detectado**

# Nodos validadores: Normas de participación (a.k.a. adhesión a la política técnica)
**Cada miembro de Alastria autorizado por el comité técnico para desplegar un nodo validador se compromete a:**
* Designar una persona de contacto técnico (“administrador del nodo validador”), responsable de la administración del nodo
* Responder a los requerimientos de actuación técnica que se soliciten desde el equipo técnico “core” de Alastria, en un plazo de 24 horas como máximo. En particular, proceder a actualizar la lista de nodos permisionados cuando así se solicite, dentro de este plazo
* Utilizar las versiones de los clientes blockchain especificadas en el repositorio oficial de Alastria, y desplegar y permisionar las herramientas de monitorización que el equipo técnico de Alastria determine
* Permitir la conexión de cuantos nodos se especifiquen en la lista oficial autorizada por Alastria, permisionando los enodes, direcciones IP y puertos necesarios (i.e. actuar como “bootnodes” para todos los clientes blockchain autorizados por Alastria)
* Dotar a los servidores (virtuales o físicos) de suficiente capacidad de proceso, memoria y espacio en disco para su correcto funcionamiento como nodos validadores y “bootnodes” en función de la magnitud de la red de Alastria en cada momento, y conforme a las especificaciones concretas que se vayan detallando  dentro de la política técnica. En concreto, se requiere que los nodos validadores tengan suficiente espacio y capacidad de proceso para mantener todo el histórico del blockchain de Alastria desde su comienzo (i.e. sin hacer “tree prunning”)
* Mantener los servidores en régimen de alta disponibilidad, 24/7, según las condiciones estándar detalladas en la política técnica
* No utilizar ni permitir utilizar los nodos validadores para la instanciación de smart contracts o el envío de transacciones
* Comunicar inmediatamente al equipo técnico de Alastria las posibles vulnerabilidades que se pudieran encontrar en la plataforma, y no explotarlas en beneficio propio

**En caso de incumplimiento de alguna de estas normas, el equipo técnico de Alastria junto con los otros nodos validadores procederán al despermisionamiento y consiguiente desconexión del nodo validador.**

**El compromiso de lanzamiento y operación del nodo validador es voluntario e indefinido, y podrá revocarse voluntariamente mediante comunicación fehaciente al Comité Técnico de Alastria con un preaviso de un mes.**

# Asociado general Alastria: Normas de participación (a.k.a. adhesión a la política técnica)
**Alastria, a través de su equipo técnico “core” gobernado por su Comité Técnico:**
* Promoverá el desarrollo, evolución y mantenimiento de la arquitectura de la red de blockchain de Alastria, así como los scripts y herramientas de soporte para el despliegue de nodos por parte de sus socios, y de las herramientas de monitorización necesarias
* Aceptará la participación de los miembros de Alastria en la red, autorizando y actualizando las listas oficiales con los identificadores de los nodos de los miembros que así lo soliciten, según el procedimiento establecido
* Organizará la monitorización continua de la red, y velará por el cumplimiento de la política técnica que se establezca en cada momento, detectando en la medida de lo posible los incumplimientos que se produzcan, y realizando las acciones correctivas necesarias para salvaguardar el buen funcionamiento de la red
* Proveer un soporte técnico razonable a los socios de Alastria, en horario laboral, y mediante las herramientas de colaboración establecidas
* Recibirá las alertas, comunicaciones de problemas y posibles vulnerabilidades, y sugerencias técnicas que los socios de Alastria puedan enviar al equipo técnico por los canales establecidos, y realizará el mayor esfuerzo posible para atenderlas en la medida de lo razonablemente posible, velando siempre por la integridad y utilidad de la red, y por el beneficio para sus socios

***
Siguiente: [Alguna información útil](https://github.com/jesus-alastria/alastria-node/wiki/Alguna-informaci%C3%B3n-%C3%BAtil)
