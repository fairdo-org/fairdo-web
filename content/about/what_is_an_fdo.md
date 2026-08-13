---
title: " FAIR Data - What is an FDO?"
description: "Learn more about our organisation and mission."
---
<!-- #### What is an FDO? 
-->
People often ask us to explain what an FDO is in a few short words. 
An FDO is a standardized and persistent bundle of all information about a digital object that is important for all FAIR aspects of reusing the included bit sequence. It should be noted that the bit sequence can encode any digital information, such as data, metadata, configurations, semantic assertions, and software. 

##### An FDO is:
- A bundle that complies with the FAIR principles, i.e., it is machine actionable.
- A bundle that is referred to by a global, unique, resolvable, and persistent identifier (PID). The PID resolves to a predictable, machine-actionable structure (FDO Record) containing attribute-value pairs. The attributes must be defined and registered.
- Based on minimal specifications. The FDO Record must contain just a few mandatory attributes defined by the FDO specifications, but it allows communities to add their own defined, registered attributes that are useful for their work. Currently, only two attributes are mandatory: the reference to the FDO profile and the FDO type.
- A passive entity in its basic form. However, many FDO implementations link operations with FDOs, making them active units similar to those in object-oriented programming. In their extended form, they can be autonomous agents that communicate with each other.

#### What is an FDO not?
We often need to state in brief what an FDO is not.

##### An FDO is not:
- A protocol. However, when the FDO specifications are broadly agreed upon, it will make sense to use a protocol that allows interaction with FDOs in a unique, standardized way, independent of how thousands of repositories organize their data. Think of the analogy of routed packages and TCP/IP.
- A new metadata set. However, it allows communities to refer to their metadata records based on their domain schemas and vocabularies. Communities can also use the FDO Record to add their own metadata attributes. Some communities use the FDO Record for versioning, for example, to increase processing efficiency.
- A new schema for "data collections" or "data sets." There are many such schemas serving different communities, from MPEG to CMDI and RO-Crate specifications.

#### What are Core FDOs?
The introduction of **FDO Operations** and **Active FDOs** necessitated defining a **“Core FDO”** to clarify that operations are optional.

While FDO Specifications describe passive entities, in practice, researchers often attach operations—similar to methods in object-oriented programming—to encapsulate behaviour.

**A Core FDO is a passive, specification-defined unit:**

- It is identified by a PID.
- Its attributes are defined by an FDO Profile.
- All attribute types must be registered in a recognised Data Type Registry.
- The FDO Record contains attribute-value pairs, including references to data, metadata, or software stored in repositories, as well as values such as checksums.
- The record links to a Data Deposit Box (DDB) and a Metadata Repository.

**The diagram illustrates the following relationships:**

- Data Type Registry, including the checksum definition
- FDO Profile, including the checksum
- FDO Record, including the type, data reference, metadata reference, and checksum
- Links to the DDB and Metadata Repository

Core FDOs are initially passive information units, but they can optionally be extended with operations to become active, autonomous agents.

#### What are Data FDOs – are they simple?
Data FDOs are the most common type of FDO, referencing bit sequences such as data, metadata, software, and configurations. All data FDOs are core FDOs.

Creating a basic Data FDO is straightforward:  
1. Define attributes beyond the two mandatory ones (FDO_Type, Ref_FDO_Profile, and Ref_Data), such as Checksum and Size.  
2. Register these attributes in an open, recognized data type registry (e.g., FDO DTR or a domain-specific registry).  
3. Create an FDO profile using a template that includes your chosen attributes, and then register it in the FDO profile registry.  
4. Assign a PID, then create the FDO record with all values and references.

Once set up, the same FDO profile and template can be reused for multiple files. Repositories typically maintain several standard templates to accommodate various data types and needs.

#### Are there other FDO Configuration Types?
Yes, there are several other configurations beyond Data FDOs, which illustrates the flexibility of FDOs. These configurations are illustrative, not normative, and reflect diverse use cases.

1. Collection FDOs: A single FDO references multiple data or metadata FDOs (e.g., a dataset bundle). It doesn't contain bit sequences itself, but rather links to them via PIDs. This is useful for managing complex objects, such as a research project with multiple files.

2. RO-Crate FDOs
An FDO points to an RO-Crate metadata file (e.g., JSON-LD) that describes external resources. The FDO record includes a reference to the RO-Crate, enabling rich, standardized metadata packaging.

3. Query FDOs: An FDO references a database query (e.g., SQL) rather than raw data. The actual data is dynamically retrieved by executing the query. It is not a data FDO because it points to an executable operation.

4. Nanopublication FDOs
FDOs are used to represent semantic assertions or scientific claims (nanopublications). The FDO links to a structured assertion with provenance, evidence, and claim.

These configurations demonstrate that FDOs are not limited to data files; they can also represent collections, queries, metadata packages, and assertions. This enables the creation of flexible, FAIR-compliant digital objects.

#### Can FDOs be associated with operations?
Core FDOs are passive and do not inherently include operations. However, operations can be linked to FDOs or FDO types in flexible ways, as defined in the FDO Operations document.

Operation registries can be created by anyone (e.g., individuals or communities) to map FDO types to specific operations. These registries are external to core FDOs and are not standardized by FDOF.
Operations themselves can be FDOs. For example, an FDO could describe a data processing task.
Linking is done via references in the FDO record or registry entries.

**Key points:**  
- Operations can only run if the user has the proper access rights, which are based on the rights metadata in the FDO.  
Access to registries or operations may be restricted.  
- Registries may specify where operations should be executed.  
- The FDO does not define the format or behavior of operation registries.

When operations are attached, FDOs become active, similar to methods in object-oriented programming (OOP). This creates dynamic, executable digital objects while maintaining FAIR principles.

#### What is special for Active FDOs?
ctive FDOs extend the FDO concept by integrating operations and turning them into autonomous, self-contained entities that can communicate with other aFDOs.

**Key features:**
Built-in operations registry: It defines which operations or workflows execute in response to specific events.
Event-driven behavior: They react autonomously to standardized events received via Service Access Points (SAPs).
Standardized communication: Events follow a fixed format, and actions are triggered based on event type and trust checks.
Workflow (as per diagram):
Trust check: The target aFDO verifies the sender’s credentials.
Event acceptance: Decide whether to process the event.
Execution: Runs defined operations or workflows.
Response: Sends feedback (accept or reject) back to the source.
Each aFDO maintains its own state and event list and exposes its capabilities externally.

**Scenarios:**
Closed: Predefined trust relationships (e.g., partner agreements). Known sources and reduced risk.
Open: Unknown aFDOs may send events, presenting higher security challenges. This requires robust trust and security frameworks inspired by WoT and Dataspace architectures.
aFDOs differ from standard FDOs in that they:
- Tight integration of operations
- Autonomous, event-driven behavior
- Built-in trust and security checks

They enable dynamic, intelligent digital objects that can collaborate like agents in a decentralized system.

#### What about the relation between FDOs and Metadata?
FDO records include metadata, called Kernel Attributes (KAs), that describe the bit sequence. However, they are not intended to replace community-specific metadata schemas.

**Key Principles:** 
- FDOs reference, don't replace: FDOs link to rich, domain-specific metadata (e.g., scientific, rights, technical) using persistent references, rather than embedding them directly.  
- Kernel Attributes (KAs): Only a minimal, mandatory set is defined (e.g., FDO_Type, FDO_Profile_Ref) to ensure machine actionability and predictability.  
- Extensibility: Repositories may add more KAs, but they must be:  
  a. Defined and openly registered  
  b. Explicitly referenced in the FDO profile.  
- FDO profile requirement: Every FDO record must be governed by an FDO profile that lists all expected KAs and points to their definitions.

**Best Practices for Linked Metadata:**  
- External metadata should be FAIR.  
  a. The schema must be explicit (preferably expressed as RDF triples).  
  Concepts and vocabularies should be registered in open, shared registries (e.g., community-driven or widely adopted semantic profiles).  
- Avoid embedding large metadata sets in FDO records. Use separate, community-driven metadata instead.

Bottom line: FDOs provide a lightweight, standardized way to reference rich metadata, not replace it. This keeps FDOs simple, interoperable, and aligned with existing community practices.

#### Are Nanopublications FDOs?
The format has evolved to include not only single statements, but also datasets, workflows, reviews, social annotations, and all types of statements related to the domain, meta, and social levels. Over the last decade, a decentralized ecosystem has emerged, providing services such as publication, authentication, timestamping, persistent identifiers, storage, and search across the growing nanopublication network.
Recent analyses demonstrate that properly designed nanopublications — those that describe a digital object type, its location, and its provenance or context — fulfill the FAIR digital object requirement specifications. This enables their deployment as general-purpose FDO implementations. 

For more information, look here:

[Mass Spectrometry Laboratory:](https://nanodash.knowledgepixels.com/project?id=https://w3id.org/kpxl/custom/project/terms/LEIbits)

[Data Stewardship More Generally:](https://nanodash.knowledgepixels.com/project?id=https://w3id.org/kpxl/custom/project/terms/LEIbits)

#### Are DCAT and FDOs the same?
No, DCAT and FDO are different. 

DCAT is neither an FDO nor an FDO implementation. It is an RDF-based metadata vocabulary that aims to improve interoperability across data catalogs. As a standard controlled vocabulary, DCAT categories can be included in FDO profiles or in the metadata descriptions used by providers to describe the bit sequence included in an FDO. The following table compares FDOs and DCAT.
An FDO is a standardized and persistent bundle of all information about a digital object that is important for all FAIR aspects of reusing the included bit sequence.
A bit sequence can encode digital information, such as data, metadata, configurations, semantic assertions, and software.	DCAT is a metadata standard and a controlled vocabulary. It allows publishers to describe datasets. Such a description may or may not include a pointer to the bit sequence.
DCAT focuses on datasets, but it also supports other research artifacts via dcat:Resource, which extends dcat:Dataset.
An FDO is a bundle that complies with the FAIR principles, i.e., it is machine-actionable.	As an RDF controlled vocabulary, DCAT complies with the FAIR principles and is machine-actionable.
A bundle that is referred to by a global, unique, resolvable, and persistent identifier (PID). Any dcat:Resource can have an identifier. If present, it is not mandatory for it to be a PID.
In its basic form, a dcat:Resource is a passive entity; however, many FDO implementations link operations with FDOs. 

#### Do FDOs increase Interoperability?
Data interoperability involves the meaningful use of data from diverse sources and formats, which is achieved through shared standards, formats, vocabularies, and protocols.
The EU Data Act outlines four key layers:
1) Clear, machine-readable descriptions of data content, quality, licensing, and methodology; 2) publicly available, consistent data structures, vocabularies, and classifications; 3) machine-accessible APIs with defined terms of use and service quality (e.g., real-time, bulk); and 4) tools for automating data sharing (e.g., smart contracts).
FDOs address core interoperability by:
- Bundling schema and vocabulary references to ensure that the syntactic and semantic context is always available
- Providing a unified access model, which is a consistent way to identify, access, and interact with data and metadata regardless of the repository, technology, or data structure

Like the TCP/IP protocol for network communication, FDOs offer a common protocol layer for digital objects, enabling seamless, machine-actionable interoperability across diverse systems and data spaces.

#### Do FDOs increase data security?
FDOs, Security & Data Sovereignty (Shortened)
FAIR DO specifications don’t prescribe security mechanisms, but emphasize including access rights in FDOs — critical for trust in data sharing, especially with AI.
Data sovereignty means having control over who collects, stores, shares, and uses data, which is governed by policies and rights metadata.
FDOs enhance sovereignty by:
- Bundling rights metadata with the FDO via PID
- Persistently linking data, metadata, and access rules, independent of context
- Using a secure PID system to protect FDO records from tampering or unauthorized access

Three security realms:
PID System – Critical: It must ensure integrity, confidentiality, and persistence. It is hosted by a trusted, independent agency.
Registries (FDO profiles and types): Less critical. Need availability and basic security, not high-level protection.
Data repositories are critical. They must secure stored bit sequences (data, metadata, and software) with appropriate access controls.
FDOs do not enforce security but provide a framework to securely bind rights and data — enabling trust, sovereignty, and scalable, FAIR data sharing.

#### Do FDOs offer a fundamentally different approach to data security?
FDOs embed rights and reuse conditions directly into data objects tied to a single, persistent PID managed by a trusted entity. This ensures integrity and traceability.
To strengthen security, FDOs can be designed so that:
- Access requires resolving the PID to rights metadata first.
- Usage is checked against owner-defined policies.
- A secure token is issued for authorized access.

This enables controlled, auditable reuse, even restricting execution to approved software, and prevents unauthorized copying while ensuring data sovereignty.

#### Does FDOF have recommendations to improve data security?
There are several ways to increase data security using FDOs.
One option is to add a checksum to your FDO record. This allows you to check the identity, authenticity, and integrity of the data. It can also be used to detect duplicates.
If necessary, restrict access to the data referenced in the FDO record. Access could then be restricted to certain identities. You could also use encapsulation by operation, meaning the provider forces users to use specific software to access the data.

#### Are GIDS and Dataspaces the same?
The term "Global Integrated Dataspace (GIDS)" refers to a domain of autonomous, persistent FAIR digital objects (FDOs) that contain all the necessary information—data, metadata, and rights—for machine-actionable reuse.  

However, "dataspace" is used differently.  
- EU/IDSA: It often implies a governed, closed environment for trusted, sovereign data sharing (e.g., industrial dataspaces).  
- Broader view (IDSA WG): A shared domain with common rules and technology to enable data sharing, which is not necessarily closed.  

FDOs are foundational building blocks for dataspaces.  
- Core FDOs are passive and do not interpret rights.  
With FDO operations, rights can be enforced, enabling usage control.  

FDOs are technology-agnostic and support both open and closed dataspaces. They provide the FAIR, persistent, self-contained object at the heart of any dataspace.

#### Do FDOs require some governance?" 
Since rules need to be maintained and they narrow the degree of freedom in solution building, agreeing to some governance is costly. Therefore, the impact of governance should be minimal. A global agreement on using FDOs to organize data requires minimal governance agreements.
The FDO standard must be maintained and further developed.
A few registries must be created to build an FDO infrastructure.
To organize this, some form of lean global organization must be maintained. Currently, the FDO Forum performs this work without external funding, and the DONA Foundation ensures the availability of the secure, global PID system.

#### Are FDOs the same as Data Products?
Data refers to any meaningful digital representation, including metadata.
According to the DSSC, data products are standardized, consumable packages of data and services with machine-readable descriptions and policies.
FDOs go further.
They explicitly bundle data, metadata, rights, and software; require a persistent PID for identification; and enforce strict, standardized bundling for FAIR reuse. While data products are flexible, FDOs provide a rigorous, machine-actionable foundation, making them ideal for implementing data products with guaranteed interoperability and traceability.

#### What is the relation between FDO and IoT?
A Thing (T) is a physical or virtual entity with a standardized Thing Description (TD), which enables machine-readable interaction. A Thing can act as a client or server, support lifecycle phases, and use W3C Web of Things (WoT) standards, such as JSON-LD, REST, and protocol bindings.  
**Comparison with FDOs:**  
Things are device-centric, protocol-flexible, and evolve dynamically.  
Active FDOs (aFDOs) are similar in that they are autonomous, operation-enabled, and security-aware.  
Both rely on trusted identities, encryption, and access control.  
WoT's work on security, profiles, and interoperability offers valuable lessons for aFDO design.  

FDOs and Things share goals, but FDOs offer a more standardized, persistent, and FAIR-focused approach to digital objects, including data, metadata, and software.


