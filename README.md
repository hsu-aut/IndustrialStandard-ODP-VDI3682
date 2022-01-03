# VDI 3682 Ontology-Design-Pattern

The formalized process description ontology is based on the VDI 3682 guidline according to [1]. The formalized process description enables a standardized description of all kinds of processes. It is applicable for technical, non-technical, continuous, batch and discrete processes. A process describes the desired behavior of a system, by means of a solution neutral description of inputs and outputs. Inputs and outputs (product, energy or information) are transformed by a process (desired behavior), while the process is performed by a technical resource. The technical resource is able to implement certain processes and is an abstract description of a system containing hardware (structure) and software (behavior) aspects.

Figure 1 shows the in OWL implemented information model as an UML class diagram. Based on the VDI 3682 guideline, inputs and outputs (product, energy or information) are transformed by a process, while the process is performed by a process operator, which is realized by a technical resource. The technical resource is able to implement certain functions or processes and is an abstract description of a system containing hardware (structure) and software (behavior) aspects. A process consists of a process operator, state and system border. The system border defines the observation horizon.

![](./pictures/VDI3682_LWO.png?raw=true "VDI3682 LWO")<br></br>
Figure 1: Formalized Process Description according to VDI3682

“Dependency” is not explicitly contained within the VDI 3682. It is used to describe dependencies of In- and Outputs. Due to open world assumption (OWA) the case that more than one In- or Outputs occur does always mean an alternative Input. For the case, that In- and Outputs are depending on each other, dependencies can be defined.

A detailed description can be found in the rdfs:comment of the ODP or the standard [1].

Exemplary Competency Questions that could be answered with this ODP:<br></br>
Table 1: Example Competency Questions
![](./pictures/exCQ.png?raw=true "exampleCQ")

[1] Guideline VDI/VDE 3682-1. Formalized Process Descriptions, 05.2015.
