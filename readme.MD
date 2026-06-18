# Projeto-Eletiva: Action Platform Game

A 2D platformer game developed as part of a Game Development Platforms course, featuring state-machine-based player movement, dynamic camera systems, and multiple themed environments.

## Overview

**Projeto-Eletiva** is a functional prototype of a 2D action platformer built with Godot Engine 4.4.1. The game implements fundamental platformer mechanics through a state machine architecture, allowing the player character to transition seamlessly between idle, walking, and jumping states. The project demonstrates practical game development concepts including physics simulation, scene management, camera control, and level progression.

The game is optimized for pixel art aesthetics with a viewport resolution of 288x208 pixels and features over 30 character animations across multiple action states.

## Context

This repository represents the game engine and core gameplay systems developed as part of an elective course focused on game development platforms. The project serves as a practical exploration of platformer mechanics and the Godot Engine's capabilities for 2D game development. Within the broader solution, this repository contains all gameplay logic, scene architecture, and visual assets required to run the platform game across multiple themed levels.

## Technologies

- **Engine**: Godot Engine 4.4.1
- **Scripting Language**: GDScript
- **Graphics**: Pixel art (32×32 sprites with 288×208 viewport)
- **Version Control**: Git
- **Platform Target**: Cross-platform (configured for mobile and desktop)

## Architecture

The game follows a modular, component-based architecture organized into distinct systems:

### Player State Machine
The player character is controlled by a finite state machine (FSM) with three primary states:
- **Idle**: Character at rest, awaiting input
- **Walk**: Character moving horizontally in response to input
- **Jump**: Character in mid-air due to jump action or gravity

State transitions are managed by the `player.gd` script, which handles input detection and physics calculations.

### Camera System
A dedicated camera entity (`camera.gd`) follows the player character dynamically by querying the global "player" group. This ensures the viewport always centers on player position during gameplay.

### Level Progression
The `level_end.gd` script manages scene transitions via Area2D collision detection. When the player enters a level exit zone, the system automatically loads the next scene based on configured parameters.

### Asset Organization
- **Entities**: Reusable scene components (player, camera, level end triggers)
- **Scripts**: Core game logic in GDScript
- **Sprites**: Character animations and tileset definitions
- **Scenes**: Composed level environments
- **Tiles**: Terrain and decoration resources

## Features

- **State-Based Player Movement**: Fluid transitions between idle, walking, and jumping states
- **Physics Simulation**: Gravity-based falling and momentum-aware movement
- **Dynamic Camera**: Real-time player tracking with smooth following
- **Multi-Level Support**: Three themed environments with seamless scene transitions
- **Extensive Animation Library**: 30+ character animations covering movement, combat, and injury states
- **Thematic Level Design**: Seasonal tilesets (Grassland, Autumn Forest, Tropics, Winter World) with environment-specific visual identity
- **Input System**: Keyboard controls (A/D for movement, Space/W for jumping; arrow keys supported)
- **Pixel Art Optimization**: Retro aesthetic with optimized asset sizes and viewport resolution

## Repository Structure

```
projeto-eletiva/
├── entities/                    # Reusable scene components
│   ├── player.tscn             # Player character scene
│   ├── camera.tscn             # Camera follow entity
│   └── level_end.tscn          # Level exit trigger
├── scripts/                     # GDScript game logic
│   ├── player.gd               # Player state machine and movement
│   ├── camera.gd               # Dynamic camera controller
│   └── level_end.gd            # Scene transition logic
├── scene/                       # Composed level scenes
│   ├── forest.tscn             # Forest level
│   ├── game.tscn               # Main/menu level
│   └── tropic.tscn             # Tropical level
├── sprites/                     # Visual assets
│   ├── 1 - Toggle/             # Character animations (30+ states)
│   └── Seasonal Tilesets/      # Environment tilesets and decorations
├── tiles/                       # Tile resource definitions
│   ├── terrain.tres            # Terrain tile resource
│   └── decoration.tres         # Decoration tile resource
├── project.godot               # Godot project configuration
└── icon.svg                     # Project icon
```

### Key Files

- [project.godot](project.godot): Engine configuration, input mappings, and project metadata
- [player.gd](scripts/player.gd): Core player logic implementing state machine and physics
- [camera.gd](scripts/camera.gd): Camera tracking system using group-based target detection
- [level_end.gd](scripts/level_end.gd): Scene transition handler

## Installation

### Prerequisites

- **Godot Engine 4.4.1** (exact version required)
  - Download from: [Godot 4.4.1 Stable Release](https://godotengine.org/download)

### Setup Instructions

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/eletiva-games.git
   cd eletiva-games
   ```

2. **Open in Godot**
   - Launch Godot Engine 4.4.1
   - Click **Import** on the startup screen
   - Navigate to the cloned project directory
   - Select `project.godot`
   - Click **Import & Edit**

3. **Project Initialization**
   - Godot will automatically import all scenes, scripts, and assets
   - Wait for the editor to fully load the project

## Usage

### Running the Game

1. In the Godot editor, ensure the main scene is set (typically `game.tscn`)
2. Press **F5** or click the **Play** button to start the game
3. The game will launch in a new window with the configured viewport (288×208 pixels)

### Game Controls

| Action | Input |
|--------|-------|
| Move Left | A or Left Arrow |
| Move Right | D or Right Arrow |
| Jump | Space or W |

### Level Selection

The project contains three playable levels accessible through scene transitions:
- **forest.tscn**: Initial level with grassland environment
- **game.tscn**: Main level with primary gameplay setup
- **tropic.tscn**: Advanced level with tropical environment

Load scenes through the editor or modify `level_end.gd` to configure progression flow.

## My Contributions

Based on repository evidence, contributions include:

- **Core Player State Machine**: Implementation of the three-state FSM (`player.gd`) with smooth state transitions
- **Physics Integration**: Integration of Godot's physics system for gravity, movement, and collision detection
- **Camera System**: Development of the group-based dynamic camera that follows player position (`camera.gd`)
- **Level Progression**: Implementation of scene transition logic triggered by level exit zones (`level_end.gd`)
- **Input Mapping**: Configuration of input events for movement (left/right) and jump actions
- **Project Architecture**: Organization of assets, scripts, and scenes into a modular structure
- **Asset Integration**: Setup and configuration of 30+ character animations and multi-season tilesets

## Future Improvements

- **Enhanced Mechanics**: Add double-jump, wall-slide, and dash mechanics for expanded movement options
- **Enemy Systems**: Implement enemy AI with patrol and chase behaviors
- **Combat Mechanics**: Introduce player attack animations and projectile systems
- **Health System**: Add health/damage mechanics with visual feedback and the existing "Half_Health" animation states
- **Particle Effects**: Integrate particle systems for jump landing, damage, and environmental interactions
- **Audio System**: Add background music and sound effects for actions and level transitions
- **UI/HUD**: Implement health display, level progression indicators, and pause menu
- **Level Editor Tools**: Create visual level design tools to streamline environment creation
- **Performance Optimization**: Profile and optimize asset loading for mobile platforms
- **Additional Environments**: Expand with winter world level and additional seasonal variations

## Team

This project was developed by a team of Computer Science students as part of a Game Development Platforms elective course. The collaborative effort demonstrates practical application of game engine fundamentals and software architecture principles in a production-oriented project.
```

**Para executar uma cena:**
1. Abra qualquer arquivo `.tscn` no editor
2. Pressione **F6** (Play Scene)

⚠️ **Nota importante:** Não use F5 (Play Project), pois o fluxo principal ainda não está completamente configurado.

---

## 🎮 Controles

| Ação | Tecla | Alternativa |
|------|-------|------------|
| Mover Esquerda | **A** | ← (Seta Esquerda) |
| Mover Direita | **D** | → (Seta Direita) |
| Pular | **ESPAÇO** | **W** |

---

## 🏗️ Estrutura do Projeto

```
projeto-eletiva/
├── project.godot           # Configuração do projeto
├── readme.MD               # Este arquivo
├── icon.svg                # Ícone do projeto
│
├── scene/                  # Cenas principais
│   ├── forest.tscn        # Cenário floresta
│   ├── game.tscn          # Cenário principal
│   └── tropic.tscn        # Cenário trópicos
│
├── entities/              # Componentes reutilizáveis
│   ├── player.tscn        # Entidade jogador
│   ├── camera.tscn        # Câmera dinâmica
│   └── level_end.tscn     # Trigger de conclusão de fase
│
├── scripts/               # Lógica em GDScript
│   ├── player.gd          # Controller do jogador (movimento, estados, animações)
│   ├── camera.gd          # Seguir o jogador
│   └── level_end.gd       # Carregar próxima fase
│
├── sprites/               # Assets de animação
│   ├── 1 - Toggle/        # Animações do jogador (~30+ estados)
│   │   ├── Idle, Run, Jump, Crouch
│   │   ├── Punch, Hurt, Death
│   │   ├── Variants com saúde reduzida
│   │   └── Ataque enquanto corre/pula
│   └── Seasonal Tilesets/ # Tilesets temáticos
│       ├── 1 - Grassland/ # Grama
│       ├── 2 - Autumn Forest/
│       ├── 3 - Tropics/
│       ├── 4 - Winter World/
│       └── 5 - Misc. universal tiles/
│
└── tiles/                 # Dados dos tilesets compilados
    ├── decoration.tres
    └── terrain.tres
```

---

## 🎨 Sistema de Animações

O projeto implementa um sistema robusto de animações com 30+ estados diferentes:

**Estados Básicos:**
- Idle (parado)
- Run (correndo)
- Jump (pulando)
- Landed (pousou)
- Crouch (agachado)

**Estados de Ação:**
- Punch (golpe)
- Hurt (ferido)
- Death (morte)

**Variações:**
- Com arma (Shooting)
- Com saúde reduzida (Half_Health)
- Envenenamento (Poison_Bubbles)

**Mecânica de Direção:**
- Flip horizontal automático baseado em input

---

## 🕹️ Mecânicas Implementadas

### Movimento
- Velocidade: **80 pixels/segundo**
- Aceleração/desaceleração suave
- Detecção de colisão com terreno

### Pulo
- Velocidade inicial: **-300 pixels/segundo**
- Física de gravidade aplicada
- Pulo só ativável quando em solo

### Câmera
- Segue a posição do jogador em tempo real
- Usa sistema de grupos para encontrar o alvo

### Progressão
- Zona de término de fase (Area2D)
- Carregamento dinâmico de próximas cenas
- Exportável para configuração em editor

---

## 🎯 Observações Técnicas

### Status Atual
- ✅ Mecânicas de movimento funcionais
- ✅ Sistema de estados e animações
- ✅ Múltiplos cenários
- ✅ Transição entre fases
- ⚠️ Fases **não interligadas** - cada uma é independente
- ⚠️ Fluxo de menu não implementado
- ⚠️ Sem build executável

### Limitações Conhecidas
- Cada cena funciona isoladamente
- F5 (Play Project) não recomendado
- Sem sistema de save/load
- Sem inimigos ou desafios dinâmicos

---

## 📁 Assets Utilizados

**Spritesheet do Personagem:** 
- Resolução: 32x32 pixels por frame
- Formato: PNG com transparência
- Total: 30+ animações diferentes

**Tilesets Temáticos:**
- Resolução: 16x16 pixels por tile
- 5 temas de ambientes
- Incluem entidades e decoração

**Créditos:**
- Seasonal Tilesets: Community License (LICENSE.txt incluído em `/sprites/Seasonal Tilesets/`)

---

## 💡 Como Expandir o Projeto

**Sugestões de Melhorias:**
1. Implementar inimigos com IA
2. Criar sistema de pontuação e vidas
3. Adicionar menu de navegação entre fases
4. Sistema de power-ups
5. Efeitos sonoros e música
6. Otimização para mobile (resoluções diferentes)
7. Build executável

---

## 📝 Notas para Avaliação

Este é um **protótipo funcional** que demonstra:
- Compreensão de máquinas de estados
- Uso de physicsbody2d e colisor
- Sistema de animações e spritesheet
- Estrutura modular com entities reutilizáveis
- Uso de grupos para comunicação entre nós
- Tratamento de input e delta time

O projeto serve como **prototipagem rápida** e base para expansão posterior.

---

## 🔧 Informações Técnicas

| Propriedade | Valor |
|------------|-------|
| Resolução | 288x208 px |
| Modo Janela | Fullscreen escalado |
| Modo Stretch | canvas_items |
| Linguagem | GDScript |
| Versão Godot | 4.4 |
| Plataforma Alvo | Mobile + Desktop |

---

**Disciplina:** Plataformas para Desenvolvimento de Games  
**Última atualização:** 2026
