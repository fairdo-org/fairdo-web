---
title: "What is an FDO?"
description: "Learn more about our organisation and mission."
---
#### What is an FDO?
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

