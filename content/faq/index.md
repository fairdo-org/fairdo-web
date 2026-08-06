---
title: "FAQ"
discribtion: "Frequently Asked Questions"
---
{{< faq >}}

  {{< faq-item question="What is an FDO?" >}}

An FDO is a standardised, persistent bundle of information about a digital object, ensuring the FAIR reusability of its bit sequence, which may represent data, metadata, software, and so on.

It is machine-actionable and is identified by a unique, resolvable PID. The PID resolves to a structured FDO record containing registered attributes.

The record requires only a few mandatory fields, currently the FDO profile and type, while allowing community-specific attributes.

Basic FDOs are passive, but they can be upgraded to become active, autonomous agents that are capable of communicating.

  {{< /faq-item >}}


  {{< faq-item question="What is an FDO not?" >}}

An FDO is not a protocol, although a standardised protocol may emerge later to enable uniform interaction with FDOs across diverse repositories. This could work similarly to how TCP/IP enables interaction with routed data.

It is not a new metadata schema. Rather, it enables referencing existing domain-specific metadata and allows communities to add their own registered attributes, for example for versioning or efficiency.

It is not a new data collection or dataset schema either. Instead, it complements existing schemas such as MPEG, CMDI, and RO-Crate rather than replacing them.

  {{< /faq-item >}}


  {{< faq-item question="What are Core FDOs?" >}}

The introduction of **“FDO Operations”** and **“Active FDOs”** necessitated defining a **“Core FDO”** to clarify that operations are optional.

While FDO Specifications describe passive entities, in practice, researchers often attach operations—similar to methods in object-oriented programming—to encapsulate behaviour.

##### A Core FDO is a passive, specification-defined unit:

- It is identified by a PID.
- Its attributes are defined by an FDO Profile.
- All attribute types must be registered in a recognised Data Type Registry.
- The FDO Record contains attribute-value pairs, including references to data, metadata, or software stored in repositories, as well as values such as checksums.
- The record links to a Data Deposit Box (DDB) and a Metadata Repository.

##### The diagram illustrates the following relationships:

- Data Type Registry, including the checksum definition
- FDO Profile, including the checksum
- FDO Record, including the type, data reference, metadata reference, and checksum
- Links to the DDB and Metadata Repository

Core FDOs are initially passive information units, but they can optionally be extended with operations to become active, autonomous agents.

  {{< /faq-item >}}


  {{< faq-item question="Kann ich meine Daten löschen?" >}}

Ja, du kannst jederzeit dein Konto und deine Daten löschen.

  {{< /faq-item >}}

{{< /faq >}}