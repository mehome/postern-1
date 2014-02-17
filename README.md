# Postern

This repository is a placeholder for future work. A simple proof of concept was created to test this idea, but as it is not suitable for production, the code was removed to a separate repository. There is not currently an agent for Barbican, but this repository remains open in case development turns that direction. If you have any questions, hop on #openstack-barbican on Freenode.

An agent allowing secure access to encryption materials from the [Barbican](https://github.com/cloudkeep/barbican) key management API. This project is supported by [Rackspace](http://www.rackspace.com).

Additional documentation can be found on the [Github Wiki](https://github.com/cloudkeep/postern/wiki). For questions, comments or concerns, hop on the [mailing list](https://groups.google.com/forum/#!forum/cloudkeep) and let us know what you think.

## Getting Started

* Installation
* Contributing
* API Documentation
* Technology
* FAQ

## Why Use Postern?

The Barbican API exposes secret materials to applications using a ReST API. Any application wishing to make use of the features of Barbican can use the API directly. However, there are several reasons why you might want to use the Postern agent rather than integrate directly.

1. **Legacy Applications** - Many legacy applications cannot be modified in a cost-effective manner. Postern uses local abstractions to simplify integration.
2. **Vendor Software** - Catering to the requirements of vendor packages would be too difficult for a central API. Postern can expose a variety of abstractions and protocols that can work with vendor packages like databases.
3. **Simplicity & Consistancy** - By using a file system abstraction, developers can use the same encryption style in all environments (dev, test, prod, etc) leading to more consistent & simple environments.

## Abstractions

Postern provides a variety of abstractions for use by client applications. These abstractions are provided by a plugin type system to allow customers to extend the functionality of the agent.

### Current Abstractions

* **File System** - The first abstraction provided by the agent is a FUSE filesystem. This allows for simple integration while allowing for local policy enforcement and security.

### Planned Abstractions

* **PKCS** - The agent may  provide a PKCS enpoint to be used by vendor solutions that support that standard.
* **Environment Variables** - While using environment variables can be somewhat problematic to implement, postern may support the ability to inject keys into the environment.

