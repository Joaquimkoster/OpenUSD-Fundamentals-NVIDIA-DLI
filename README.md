# OpenUSD Fundamentals — NVIDIA DLI

Project developed during the **Fundamentals of Working With OpenUSD** course from the **NVIDIA Deep Learning Institute (DLI)**.

The goal of this project was to learn the fundamentals of **OpenUSD (Universal Scene Description)** and understand how complex 3D scenes can be structured, composed, and reused in applications such as **NVIDIA Omniverse, simulation, and industrial Digital Twins**.

This file contains only the welding Locker.

---

## 📸 Preview

### Welding Locker

<img width="750" alt="Welding Locker" src="https://github.com/user-attachments/assets/f6044193-833a-4756-82df-bcb73df8c231" />

### Factory Environment

<img width="750" alt="Factory Environment" src="https://github.com/user-attachments/assets/55f37bb7-6a25-43d8-b2bf-f08806604a97" />

---

## 📚 About the Project

During the course, I worked on building and organizing OpenUSD components, starting with a **Welding Locker** and later using composition concepts to integrate it into larger industrial structures.

The project demonstrates how an asset can be divided into different files responsible for **geometry, appearance, and composition**.

```text
Welding_Locker/
├── content.usd
├── geometry.usdc
└── looks.usd
```

### `geometry.usdc`

Contains the **3D geometry** of the Welding Locker and its Prim structure.

Example:

```text
World
└── Geometry
    └── Locker
        ├── exterior
        ├── fittings
        ├── door
        └── trims
```

### `looks.usd`

Contains information related to the **appearance and materials** of the component.

Separating geometry from appearance makes it possible to modify materials without directly changing the original geometry.

### `content.usd`

Used for **component composition**, bringing together the different elements required to represent the complete asset.

---

## 🧠 Concepts Learned

During the project, I worked with fundamental OpenUSD concepts, including:

- USD, USDA, and USDC
- Stage and Prims
- Prim Hierarchy
- Default Prim
- Layers and Sublayers
- Authoring Layers
- Layer Stack
- Non-destructive Composition
- Geometry and Looks
- Materials
- Material Binding
- Transformations
- Coordinate Systems and World Axis
- References
- Payloads
- Variants and Variant Sets
- Assemblies
- Layouts
- Asset Reuse
- Modular Scene Organization
- Industrial Environment Composition
- Design Proposals using Layers
- USD Composition Debugging

---

## 🏗️ OpenUSD Scene Structure

One of the main concepts I learned is that a complex 3D scene does not need to exist as a single large file.

Instead, it can be composed of multiple assets and layers:

```text
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
```

Features such as **References, Payloads, Variants, and Layers** make it possible to build larger scenes while keeping assets organized and reusable.

---

## 🧩 Non-Destructive Composition

Another important concept was working with different Layers without permanently modifying the original files.

```text
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
```

This allows different modifications to coexist and be combined by OpenUSD.

Instead of modifying the original asset directly, additional Layers can contain changes and alternative configurations.

---

## 🔄 Variants

Variant Sets allow multiple configurations of the same asset to be created without duplicating its entire structure.

Example:

```text
Welding_Locker
└── Looks
    ├── Painted
    └── Steel
```

The same principle can be applied to machines, vehicles, equipment, and other industrial components.

For example, a single asset could contain different configurations for:

- Materials
- Colors
- Components
- Equipment configurations
- Design alternatives

---

## 🔗 References

**References** allow assets to be reused in other scenes without duplicating their data.

```text
Factory
   ↓
Lockers Assembly
   ↓
Welding Locker
```

This makes it possible to maintain a reusable asset and reference it multiple times throughout a larger environment.

Changes made to the original asset can then be reflected wherever that asset is referenced.

---

## 📦 Payloads

**Payloads** provide a way to control which parts of a scene are loaded.

For example:

```text
Factory
├── Building       [LOADED]
├── Welding Area   [LOADED]
├── Warehouse      [UNLOADED]
└── Production     [LOADED]
```

This concept is especially useful when working with large industrial environments where loading every asset simultaneously may not be necessary.

---

## 🧱 Layers and Sublayers

Layers are one of the fundamental mechanisms used to organize OpenUSD scenes.

A scene can be composed from multiple Layers:

```text
Root Layer
├── Building.usda
├── Equipment.usda
├── Layouts.usda
└── Proposal_A.usda
```

Using **Sublayers**, different USD files can contribute information to the final Stage.

This allows different parts of a project to remain separated while still being combined into one scene.

---

## ✏️ Authoring Layers

When multiple Layers are present, an **Authoring Layer** determines where new modifications are written.

This makes it possible to keep the original assets unchanged while creating modifications in separate Layers.

Conceptually:

```text
Original Asset
      ↓
Base Layer
      +
Layout Layer
      +
Proposal Layer
      ↓
Final Stage
```

---

## 🎨 Geometry and Materials

OpenUSD allows geometry and appearance information to remain separated.

```text
Geometry
├── exterior
├── fittings
├── door
└── trims

        +

Looks
├── Materials
└── Material Bindings
```

This allows materials to be changed without modifying the underlying 3D geometry.

---

## 🎨 Material Binding

Material Binding associates materials with specific Prims.

Conceptually:

```text
Locker
├── exterior ──→ Painted Metal
├── fittings ──→ Steel
├── door ──────→ Painted Metal
└── trims ─────→ Plastic
```

This provides a structured way to manage the visual appearance of complex assets.

---

## 📐 Transformations and Coordinate Systems

During the project, I also worked with object transformations and scene orientation.

Important transformation properties include:

```text
Transform
├── Translate
├── Rotate
└── Scale
```

I also worked with the **World Axis**, including configuring the scene to use the **Z axis as the vertical axis**.

Coordinate-system configuration is important when combining assets created using different 3D workflows.

---

## 🏗️ Assemblies

Individual components can be combined into larger assemblies.

For example:

```text
Lockers
├── Welding_Locker
├── Welding_Locker
├── Welding_Locker
└── Welding_Locker
```

This creates a hierarchical workflow:

```text
PARTS
  ↓
COMPONENTS
  ↓
ASSEMBLIES
  ↓
AREAS
  ↓
FACTORY
```

This type of organization is particularly useful for industrial Digital Twin environments.

---

## ♻️ Asset Reuse

One of the key advantages of OpenUSD is the ability to reuse the same asset throughout a scene.

```text
              Welding_Locker
                    │
          ┌─────────┼─────────┐
          ↓         ↓         ↓
       Locker 1  Locker 2  Locker 3
```

Instead of creating independent copies of the same model, assets can be referenced and reused throughout the environment.

---

## 🏭 Industrial Scene Composition

The course progressed from working with an individual asset to composing a larger industrial environment.

Conceptually:

```text
Factory
│
├── Building
│
└── Equipment
    ├── Lockers
    ├── Walkway
    ├── Hood Rack
    └── Welding Line
```

This demonstrated how individual assets and assemblies can become part of a structured factory environment.

---

## 📐 Layouts and Design Proposals

Layouts can define where assets are positioned inside the industrial environment.

OpenUSD Layers can also be used to create alternative design proposals.

```text
Factory
│
├── Current Layout
├── Proposal A
├── Proposal B
└── Proposal C
```

This makes it possible to experiment with changes without permanently modifying the original factory configuration.

---

## 🔧 USD Composition Debugging

During the project, I also gained experience identifying and solving problems related to USD composition.

A typical debugging process can involve:

```text
Asset not visible
       ↓
Check Stage
       ↓
Check Prim hierarchy
       ↓
Check Layers
       ↓
Check Sublayers
       ↓
Check file paths
       ↓
Check References
       ↓
Check transformations
```

This helped me better understand how the different parts of an OpenUSD scene depend on each other.

---

## 🏭 OpenUSD and Digital Twins

This project introduced me to an approach that goes beyond traditional 3D modeling.

Instead of thinking only in terms of:

```text
3D Model
```

OpenUSD makes it possible to think in terms of:

```text
Structured 3D Data
        ↓
Reusable Assets
        ↓
Assemblies
        ↓
Industrial Environment
        ↓
Digital Twin
```

This structure provides a foundation for more advanced projects involving **Digital Twins, simulation, industrial visualization, and NVIDIA Omniverse**.

---

## 🛠️ Technologies

- OpenUSD
- NVIDIA Omniverse
- NVIDIA Kit
- USD Composer
- NVIDIA Deep Learning Institute
- Linux

---

## 📂 Repository Structure

```text
openusd-fundamentals/
│
├── Welding_Locker/
│   ├── content.usd
│   ├── geometry.usdc
│   └── looks.usd
│
└── README.md
```

---

## 🎯 Key Skills Acquired

By completing this project, I gained practical experience in:

- Structuring assets using OpenUSD
- Working with scenes composed of multiple USD files
- Understanding Stage and Prim hierarchies
- Separating geometry and appearance
- Creating and using Layers and Sublayers
- Working with Authoring Layers
- Understanding non-destructive scene composition
- Working with References and Payloads
- Creating asset configurations using Variants
- Applying and organizing materials
- Working with transformations and coordinate systems
- Organizing components into Assemblies
- Reusing assets across different parts of a scene
- Creating structured industrial environments
- Working with alternative layouts and design proposals
- Debugging USD composition and asset dependencies
- Understanding the foundations of an OpenUSD workflow for Digital Twins

---

## 📜 Course

**Fundamentals of Working With OpenUSD**  
**NVIDIA Deep Learning Institute (DLI)**

Project developed as part of my studies in **OpenUSD, NVIDIA Omniverse, and Digital Twins**.
