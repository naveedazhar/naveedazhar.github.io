# System and Enterprise Architectures

Two disciplines related to software architecture are system architecture andenterprise architecture. Both of these disciplines have broader concerns thansoftware and affect software architecture through the establishment ofconstraints within which a software system, and its architect, must live.

**System Architecture**

A system’s architecture is a representation of a system in which there is amapping of functionality onto hardware and software components, a mapping of the software architecture onto the hardware architecture, and a concern for the human interaction with these components. That is, system architecture is concerned with the totality of hardware, software, and humans.

A system architecture will influence, for example, the functionality that is assigned to different processors and the types of networks that connect those processors. The software architecture will determine how this functionality is structured and how the software programs residing on the various processors interact.

A description of the software architecture, as it is mapped to hardware and networking components, allows reasoning about qualities such as performance and reliability. A description of the system architecture will allow reasoning about additional qualities such as power consumption, weight, and physical dimensions.

When designing a particular system, there is frequently negotiation between the system architect and the software architect over the distribution of functionality and, consequently, the constraints placed on the software architecture.

_**Enterprise Architecture**_

_Enterprise architecture is a description of the structure and behavior of an organization’s processes, information flow, personnel, and organizational subunits. An enterprise architecture need not include computerized information systems—clearly, organizations had architectures that fit the preceding definition prior to the advent of computers—but these days enterprise architectures for all but the smallest businesses are unthinkable without information system support. Thus, a modern enterprise architecture is concerned with how software systems support the enterprise’s business processes and goals. Typically included in this set of concerns is a process for deciding which systems with which functionality the enterprise should support._

_An enterprise architecture will specify, for example, the data model that various systems use to interact. It will also specify rules for how the enterprise’s systems interact with external systems._

_Software is only one concern of enterprise architecture. How the software is used by humans to perform business processes and the standards that determine the computational environment are two other common concerns addressed by enterprise architecture._

_Sometimes the software infrastructure that supports communication among systems and with the external world is considered a portion of the enterprise architecture; at other times this infrastructure is considered one of the systems within an enterprise. (In either case, the architecture of that infrastructure is a software architecture!) These two views will result in different management structures and spheres of influence for the individuals concerned with the infrastructure._
