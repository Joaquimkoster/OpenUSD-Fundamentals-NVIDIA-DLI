![Uploading factory-environment.jpeg…]()
![Uploading welding-locker.jpeg…]()
# OpenUSD Fundamentals — NVIDIA DLI

Projeto desenvolvido durante o curso **Fundamentals of Working With OpenUSD**, da NVIDIA Deep Learning Institute (DLI).

O objetivo do projeto foi aprender os fundamentos do **OpenUSD (Universal Scene Description)** e entender como cenas 3D complexas podem ser estruturadas, compostas e reutilizadas em aplicações como **NVIDIA Omniverse, simulação e Digital Twins industriais**.

---
## 📸 Preview

### Welding Locker

![Welding Locker](https://github.com/user-attachments/assets/...)

### Factory Environment

![Factory Environment](https://github.com/user-attachments/assets/...)

---

## 📚 Sobre o projeto

Durante o curso, trabalhei na construção e organização de componentes OpenUSD, começando por um **Welding Locker** e posteriormente utilizando conceitos de composição para integrá-lo a estruturas maiores.

O projeto demonstra como um asset pode ser dividido em diferentes arquivos responsáveis por geometria, aparência e composição.

```text
Welding_Locker/
├── content.usd
├── geometry.usdc
└── looks.usd
```

### `geometry.usdc`

Contém a **geometria 3D** do Welding Locker e sua estrutura de Prims.

Exemplo:

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

Responsável pelas informações relacionadas à **aparência e materiais** do componente.

A separação entre geometria e aparência permite modificar materiais sem alterar diretamente a geometria original.

### `content.usd`

Arquivo utilizado para a **composição do componente**, reunindo as diferentes partes necessárias para representar o asset completo.

---

## 🧠 Conceitos aprendidos

Durante o projeto, trabalhei com conceitos fundamentais do OpenUSD, incluindo:

- USD, USDA e USDC
- Stage e Prims
- Hierarquia de Prims
- Default Prim
- Layers e Sublayers
- Authoring Layers
- Layer Stack
- Composição não destrutiva
- Geometry e Looks
- Materials
- Material Binding
- Transformações
- Sistemas de coordenadas e World Axis
- References
- Payloads
- Variants e Variant Sets
- Assemblies
- Layouts
- Reutilização de assets
- Organização modular de cenas
- Composição de ambientes industriais
- Propostas de alteração através de Layers
- Debugging de composição USD

---

## 🏗️ Estrutura de uma cena OpenUSD

Um dos principais conceitos aprendidos foi que uma cena 3D complexa não precisa existir como um único arquivo.

Ela pode ser composta de diversos assets e layers:

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

Recursos como **References, Payloads, Variants e Layers** permitem construir cenas maiores mantendo os assets organizados e reutilizáveis.

---

## 🧩 Composição não destrutiva

Outro conceito importante foi trabalhar com diferentes Layers sem modificar permanentemente os arquivos originais.

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

Dessa forma, diferentes alterações podem coexistir e ser combinadas pelo OpenUSD.

---

## 🔄 Variants

Variant Sets permitem criar diferentes configurações para um mesmo asset sem duplicar toda sua estrutura.

Exemplo:

```text
Welding_Locker
└── Looks
    ├── Painted
    └── Steel
```

O mesmo princípio pode ser utilizado para configurações de máquinas, veículos, equipamentos e outros componentes industriais.

---

## 🔗 References e Payloads

**References** permitem reutilizar assets em outras cenas sem duplicar seus dados.

```text
Factory
   ↓
Lockers Assembly
   ↓
Welding Locker
```

**Payloads** permitem controlar o carregamento de partes de cenas maiores, algo importante para trabalhar com ambientes industriais complexos.

---

## 🏭 OpenUSD e Digital Twins

O projeto me apresentou uma abordagem diferente da modelagem 3D tradicional.

Em vez de pensar somente em:

```text
3D Model
```

o OpenUSD permite pensar em:

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

Essa estrutura fornece uma base para projetos mais avançados envolvendo **Digital Twins, simulação, visualização industrial e NVIDIA Omniverse**.

---

## 🛠️ Tecnologias

- OpenUSD
- NVIDIA Omniverse
- NVIDIA Kit
- USD Composer
- NVIDIA Deep Learning Institute
- Linux

---

## 📂 Estrutura do repositório

```text
openusd-fundamentals/
│
├── Welding_Locker/
│   ├── content.usd
│   ├── geometry.usdc
│   └── looks.usd
│
├── media/
│   ├── welding-locker.png
│   ├── factory-environment.png
│   └── demo.mp4
│
└── README.md
```

---

## 🎯 Principais conhecimentos adquiridos

Ao concluir o projeto, adquiri uma base prática para:

- Estruturar assets utilizando OpenUSD;
- Trabalhar com cenas compostas por múltiplos arquivos;
- Organizar geometria e aparência separadamente;
- Criar e utilizar Layers e Sublayers;
- Trabalhar com References e Payloads;
- Criar configurações utilizando Variants;
- Organizar componentes em Assemblies;
- Reutilizar assets em diferentes partes de uma cena;
- Estruturar ambientes industriais;
- Compreender a base de um workflow OpenUSD voltado para Digital Twins.

---

## 📜 Curso

**Fundamentals of Working With OpenUSD**  
NVIDIA Deep Learning Institute (DLI)

Projeto desenvolvido como parte dos meus estudos em **OpenUSD, NVIDIA Omniverse e Digital Twins**.
