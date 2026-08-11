# OpenUSD Fundamentals — NVIDIA DLI

Project developed during the **Fundamentals of Working With OpenUSD** course from the NVIDIA Deep Learning Institute (DLI).

The goal of this project was to learn the fundamentals of **OpenUSD (Universal Scene Description)** and understand how complex 3D scenes can be structured, composed, and reused in applications such as **NVIDIA Omniverse, simulation, and industrial Digital Twins**.

---

## 📸 Preview

### Welding Locker

<img width="800" alt="Welding Locker" src="https://github.com/user-attachments/assets/f6044193-833a-4756-82df-bcb73df8c231" />

### Factory Environment

<img width="800" alt="Factory Environment" src="https://github.com/user-attachments/assets/55f37bb7-6a25-43d8-b2bf-f08806604a97" />

---

## 📚 About the Project

During the course, I worked on building and organizing OpenUSD components, starting with a **Welding Locker** and later using composition concepts to integrate it into larger structures.

The project demonstrates how an asset can be divided into different files responsible for geometry, appearance, and composition.

```text
Welding_Locker/
├── content.usd
├── geometry.usdc
└── looks.usd
geometry.usdc

Contains the 3D geometry of the Welding Locker and its Prim structure.

Example:

World
└── Geometry
    └── Locker
        ├── exterior
        ├── fittings
        ├── door
        └── trims
looks.usd

Contains information related to the appearance and materials of the component.

Separating geometry from appearance makes it possible to modify materials without directly changing the original geometry.

content.usd

Used for component composition, bringing together the different elements required to represent the complete asset.

🧠 Concepts Learned

During the project, I worked with fundamental OpenUSD concepts, including:

USD, USDA, and USDC
Stage and Prims
Prim Hierarchy
Default Prim
Layers and Sublayers
Authoring Layers
Layer Stack
Non-destructive Composition
Geometry and Looks
Materials
Material Binding
Transformations
Coordinate Systems and World Axis
References
Payloads
Variants and Variant Sets
Assemblies
Layouts
Asset Reuse
Modular Scene Organization
Industrial Environment Composition
Design Proposals using Layers
USD Composition Debugging
🏗️ OpenUSD Scene Structure

One of the main concepts I learned is that a complex 3D scene does not need to exist as a single large file.

Instead, it can be composed of multiple assets and layers:

                         FACTORY
                            │
             ┌──────────────┼──────────────┐
             │              │              │
         BUILDING       EQUIPMENT        LAYOUT
                            │
                       ASSEMBLIES
                            │
                       COMPONENTS
                            │
                     WELDING LOCKER
                            │
                  ┌─────────┴─────────┐
                  │                   │
              GEOMETRY              LOOKS
                                      │
                                  MATERIALS

Features such as References, Payloads, Variants, and Layers make it possible to build larger scenes while keeping assets organized and reusable.

🧩 Non-Destructive Composition

Another important concept was working with different Layers without permanently modifying the original files.

Base Asset
    ↓
Geometry
    ↓
Looks
    ↓
Layout
    ↓
Proposal
    ↓
Final Stage

This allows different modifications to coexist and be combined by OpenUSD.

🔄 Variants

Variant Sets allow multiple configurations of the same asset to be created without duplicating its entire structure.

Example:

Welding_Locker
└── Looks
    ├── Painted
    └── Steel

The same principle can be applied to machines, vehicles, equipment, and other industrial components.

🔗 References and Payloads

References allow assets to be reused in other scenes without duplicating their data.

Factory
   ↓
Lockers Assembly
   ↓
Welding Locker

Payloads allow control over which parts of larger scenes are loaded, which is especially useful when working with complex industrial environments.

🏭 OpenUSD and Digital Twins

This project introduced me to an approach that goes beyond traditional 3D modeling.

Instead of thinking only in terms of:

3D Model

OpenUSD makes it possible to think in terms of:

Structured 3D Data
        ↓
Reusable Assets
        ↓
Assemblies
        ↓
Industrial Environment
        ↓
Digital Twin

This structure provides a foundation for more advanced projects involving Digital Twins, simulation, industrial visualization, and NVIDIA Omniverse.

🛠️ Technologies
OpenUSD
NVIDIA Omniverse
NVIDIA Kit
USD Composer
NVIDIA Deep Learning Institute
Linux
📂 Repository Structure
openusd-fundamentals/
│
├── Welding_Locker/
│   ├── content.usd
│   ├── geometry.usdc
│   └── looks.usd
│
└── README.md
🎯 Key Skills Acquired

By completing this project, I gained practical experience in:

Structuring assets using OpenUSD
Working with scenes composed of multiple files
Separating geometry and appearance
Creating and using Layers and Sublayers
Working with References and Payloads
Creating configurations using Variants
Organizing components into Assemblies
Reusing assets across different parts of a scene
Structuring industrial environments
Understanding the foundations of an OpenUSD workflow for Digital Twins
📜 Course

Fundamentals of Working With OpenUSD
NVIDIA Deep Learning Institute (DLI)

Project developed as part of my studies in OpenUSD, NVIDIA Omniverse, and Digital Twins.
