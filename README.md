# VDI 3682 Ontology-Design-Pattern

## Introduction

The development of software functionalities, or applications in general, that monitor and analyze manufacturing related data in order to improve, support or automate processes, is becoming increasingly important in industry. These applications require several information from different data sources in their context. An application that is planning a maintenance workers daily schedule for instance, requires several information about machine statuses, production plans and inventory, which resides in different systems likes Programmable Logical Controllers (PLC) or Structured Query Language (SQL) databases. Furthermore, manufacturing companies usually run machines and software systems from different vendors or of different ages. The schemata used in such systems do therefore not follow a certain standard, i.e. they are very heterogeneous in their semantics. When building such applications, accessing, searching and understanding the data sources is becoming a very time intensive, manual and error prone procedure that is repeated for every newly build application and for every newly introduced data source. To allow for an eased access, searching and understanding of these heterogeneous data sources, an ontology can be used to integrate all heterogeneous data sources in one schemata. 

This repository contains an ontology of DIN EN 61360 which is a standard to describe properties. We maintain a whole list of standard-based ontologies, check out these links:
 - [DIN EN 61360](https://github.com/hsu-aut/IndustrialStandard-ODP-DINEN61360)
 - [VDI 2206](https://github.com/hsu-aut/IndustrialStandard-ODP-VDI2206)
 - [VDI 2860](https://github.com/hsu-aut/IndustrialStandard-ODP-VDI2860)
 - [DIN 8580](https://github.com/hsu-aut/IndustrialStandard-ODP-DIN8580)
 - [ISA 88](https://github.com/hsu-aut/IndustrialStandard-ODP-ISA88)
 - [WADL](https://github.com/hsu-aut/IndustrialStandard-ODP-WADL)
 - [DIN EN 62264-2](https://github.com/hsu-aut/IndustrialStandard-ODP-DINEN62264-2)
 - [OPC UA](https://github.com/hsu-aut/IndustrialStandard-ODP-OPC-UA)
 - [ISO 22400-2](https://github.com/hsu-aut/IndustrialStandard-ODP-ISO22400-2)


## VDI 3682 - Formalized Process Description

The formalized process description ontology is based on the VDI 3682 guidline according to [1]. The formalized process description enables a standardized description of all kinds of processes. It is applicable for technical, non-technical, continuous, batch and discrete processes. A process describes the desired behavior of a system, by means of a solution neutral description of inputs and outputs. Inputs and outputs (product, energy or information) are transformed by a process (desired behavior), while the process is performed by a technical resource. The technical resource is able to implement certain processes and is an abstract description of a system containing hardware (structure) and software (behavior) aspects.

Figure 1 shows the information model of this ODP as an UML class diagram. Based on the VDI 3682 guideline, inputs and outputs (product, energy or information) are transformed by a process, while the process is performed by a process operator, which is realized by a technical resource. The technical resource is able to implement certain functions or processes and is an abstract description of a system containing hardware (structure) and software (behavior) aspects. A process consists of a process operator, state and system border. The system border defines the observation horizon.

![](./pictures/VDI3682_LWO.png?raw=true "VDI3682 LWO")<br></br>
Figure 1: Formalized Process Description according to VDI3682

“Dependency” is not explicitly contained within the VDI 3682. It is used to describe dependencies of In- and Outputs. Due to open world assumption (OWA) the case that more than one In- or Outputs occur does always mean an alternative Input. For the case, that In- and Outputs are depending on each other, dependencies can be defined.

A detailed description can be found in the rdfs:comment of the ODP or the standard [1].

Exemplary Competency Questions that could be answered with this ODP:<br></br>

<table>
	<thead>
		<tr>
			<th>ID</th>
			<th>Competency Question</th>
			<th>Answer</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>1</td>
			<td>What processes do exist and what inputs and outputs do they have?</td>
			<td>A list of process operators and their respective inputs and outputs</td>
		</tr>
		<tr>
			<td>2</td>
			<td>Which energy / product / information is needed (produced) by process operators X?</td>
			<td>Energy / products / information that is input (output) of process operators X</td>
		</tr>
		<tr>
			<td>3</td>
			<td>What is the predecessor (successor) of process operators X</td>
			<td>Predecessor (successor) of process operator X</td>
		</tr>
		<tr>
			<td>4</td>
			<td>What are decomposed process steps of process operator X?</td>
			<td>Sub process operators that process operator X is composed of</td>
		</tr>
	</tbody>
</table>

[1] Guideline VDI/VDE 3682-1. Formalized Process Descriptions, 05.2015.


## Usage
If you want to use this ontology design pattern, the easiest way is to directly import it into your ontology via `owl:imports` statements. Make sure to reference a fixed release version so that you can't get surprised by future changes. To do so, click on the branch selection right below the number of commits and select a tag from the dropdown, e.g. v2.0.1. Then navigate to the .owl-file and open the raw file. For this example it would be https://raw.githubusercontent.com/hsu-aut/IndustrialStandard-ODP-VDI3682/v2.0.1/VDI3682.owl. You can use this URL in an `owl:imports` statement of your ontology. If you're having trouble using this URL in a tool like Protégé, try opening your ontology with a text editor and simply inserting your imports manually.
An example of an imports section looks like this:

```xml
<owl:Ontology rdf:about="http://www.hsu-ifa.de/ontologies/capability-model#">
    <owl:versionIRI rdf:resource="http://www.hsu-ifa.de/ontologies/capability-model/1.0.0#"/>
    <owl:imports rdf:resource="https://raw.githubusercontent.com/hsu-aut/IndustrialStandard-ODP-VDI3682/v2.0.1/VDI3682.owl"/>
</owl:Ontology>
```
Of course you can also clone or download this repository and import an ODP from a local copy. The advantage of the first approach is that tools like Protégé or TopBraid Composer will directly use the ontologies from the internet and you can simply increase the version number in case you want to use a newer version of our ODPs.

## Tool Support
In case you want to make creating individuals from these TBoxes a lot easier, check out our 'Lightweight Industrial Ontology Design Support Tool' (LiOnS). It is designed to create RDF models using the Ontology Design Patterns of this repository. This enables users to:
- Semi-automatically design RDF models (only variable parts of the graph have to be defined)
- Consistent modelling, without being an ontology expert
- Downloading Turtle serialized models or SPARQL INSERTs

For more information, see https://github.com/hsu-aut/lion.

## Further reading:
- C. Hildebrandt, A. Köcher, C. Kustner, C.-M. Lopez-Enriquez, A.W. Muller, B. Caesar, C.S. Gundlach, A. Fay: _Ontology Building for Cyber-Physical Systems: Application in the Manufacturing Domain_. IEEE Transactions on Automation Science and Engineering, 2020, S. 1–17.
-  C. Hildebrandt, S. Törsleff, T. Bandyszak, B. Caesar, A. Ludewig, A. Fay: _Ontology Engineering for Collaborative Embedded Systems – Requirements and Initial Approach_. In: Schäfer, Karagiannis (Hrsg.): Fachtagung Modellierung, 2018.
- C. Hildebrandt, S. Törsleff, B. Caesar, A. Fay: _Ontology Building for Cyber-Physical Systems: A domain expert centric approach_. In: 2018 14th IEEE Conference on Automation Science and Engineering (CASE 2018), 2018.
- C. Hildebrandt, A. Scholz, A. Fay, T. Schröder, T. Hadlich, C. Diedrich, M. Dubovy, C. Eck, R. Wiegand: _Semantic Modeling for Collaboration and Cooperation of Systems in the production domain_. In: 22nd IEEE Emerging Technology and Factory Automation (ETFA), 2017.