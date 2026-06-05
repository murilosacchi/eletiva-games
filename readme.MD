# 🎮 Plataforma de Ação - Projeto Eletiva

**Disciplina:** Plataformas para Desenvolvimento de Games  
**Motor:** Godot Engine 4.4.1  
**Status:** Protótipo Funcional - Fase de Desenvolvimento

---

## 📋 Visão Geral

Jogo de plataforma em 2D com sistema de movimentação baseado em máquina de estados, múltiplos cenários temáticos e um protagonista com diversas animações de ação. O projeto implementa mecânicas fundamentais de jogos de plataforma, incluindo movimento, pulo, física de gravidade e transição entre níveis.

**Características Principais:**
- ✓ Sistema de movimento e pulo com física realista
- ✓ Máquina de estados para gerenciar estados do jogador (idle, walk, jump)
- ✓ Câmera dinâmica que segue o jogador
- ✓ 3 cenários diferentes com tilesets temáticos
- ✓ Sistema de progressão entre fases
- ✓ Mais de 30 animações do protagonista
- ✓ Resolução otimizada para pixel art (288x208)

---

## 📦 Requisitos

- **Motor:** Godot Engine **4.4.1** (versão exata)
  - Download: [Godot 4.4.1 Stable](https://godotengine.org/download)
  - Arquivo Windows: `Godot_v4.4.1-stable_win64.exe`

---

## 🚀 Como Executar

### 1. Importar o Projeto

1. Abra o Godot Engine
2. Clique em **Import** na tela inicial
3. Navegue até a pasta do projeto (`projeto-eletiva`)
4. Selecione o arquivo `project.godot`
5. Clique em **Import & Edit**

### 2. Rodar as Cenas

As cenas estão localizadas em `/scene`:

```
scene/
  ├── forest.tscn      # Fase 1 - Floresta
  ├── game.tscn        # Menu / Fase Principal
  └── tropic.tscn      # Fase 2 - Trópicos
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
