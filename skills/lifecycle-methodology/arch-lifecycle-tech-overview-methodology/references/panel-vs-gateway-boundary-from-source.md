# Control Plane vs Runtime Access Boundary

Case-shaped evidence note for product teams building on top of an external agent runtime.

## Question answered

If a product is built on top of an external agent runtime, should the product frontend talk directly to the runtime access surface, or should a business control plane sit upstream?

## General answer

Default to:
- **Product Control Plane / BFF** upstream
- **Runtime Access Surface** in the middle
- **Agent Runtime** as execution truth layer underneath

## Why this default usually wins

Because runtime-facing APIs typically expose primitives such as:
- run submission
- chat / responses
- event streaming
- approval / stop / interrupt
- scheduler / job CRUD
- capability discovery

But product-facing systems usually also need business objects that the runtime does not naturally own, such as:
- employees / agent personas
- templates / solution packages
- enterprise spaces / workspaces
- governance policies
- business task semantics
- cost, audit, and reporting projections

## Recommended calling relation

For the main product path:

`Frontend -> Product Control Plane -> Runtime Access Surface -> Agent Runtime`

## What the product control plane should do

- own business objects and bindings
- translate product semantics into runtime-native calls
- project runtime events into product-facing states
- hold governance, audit, cost, and management semantics

## What the runtime access surface should keep owning

- run submission
- event streaming
- approval / stop / interrupt
- runtime-native scheduler and jobs surfaces
- capability exposure

## What not to do

- do not treat a runtime-facing API as the same thing as a product management plane just because both speak HTTP
- do not re-wrap every runtime endpoint 1:1 if no business translation is needed
- do not infer from one lightweight UI shell that every serious product frontend should call the runtime directly

## Selective wrapping rule

Good pattern:
- wrap only where business translation or projection is needed
- leave runtime-native primitives where they belong

Potential exception:
- an expert/debug console may talk more directly to the runtime access surface later without changing the main product architecture
