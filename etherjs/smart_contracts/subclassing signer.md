Sure, let's break down the provided information about subclassing the `Signer` class, focusing on the `AbstractSigner` and `VoidSigner` classes:

### AbstractSigner

**Abstract class:**
- `AbstractSigner` is an abstract class that provides most of the functionality required to get a `Signer` working as expected.
- It requires a few signer-specific methods to be overridden.

**Properties:**
- `provider`: Read-only property representing the provider this signer is connected to.

**Methods:**
- `connect(provider: null | Provider) ⇒ Signer`: Returns the signer connected to a new provider. This method may throw errors if the signer is connected over a socket or to a specific instance of a node that cannot be transferred.

**Constructor:**
- `new AbstractSigner(provider?: P)`: Creates a new signer connected to the specified provider.

### VoidSigner

**Class:**
- `VoidSigner` is a class designed to allow an address to be used in any API that accepts a signer, but without actual signing capabilities.

**Properties:**
- `address`: Read-only property representing the signer's address.

**Constructor:**
- `new VoidSigner(address: string, provider?: null | Provider)`: Creates a new `VoidSigner` with the specified address attached to a provider.

These classes and methods provide a foundation for subclassing the `Signer` class to create custom signer implementations. The `AbstractSigner` class serves as a base with essential functionality, while the `VoidSigner` class is a specific implementation that allows using an address in signer-required APIs without actual signing capabilities.
