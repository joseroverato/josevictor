# 🧳 Travel Squad

> Equipe especializada em planejamento completo de viagens — do brief inicial aos cards visuais do itinerário.

---

## 👥 A Equipe

| Agente | Persona | Especialidade |
|--------|---------|---------------|
| 🗂 Coordenador | **Marco Destinos** | Interpreta o brief, coordena a equipe e consolida o plano |
| ✈ Transporte | **Vera Rotas** | Compara modais, analisa custo × tempo e recomenda a melhor rota |
| 🏨 Hospedagem | **Ricardo Conforto** | Pesquisa hotéis, pousadas e airbnbs por localização e orçamento |
| 🍽 Gastronomia | **Sofia Sabores** | Mapeia restaurantes, pratos típicos e custo médio de alimentação |
| 🗺 Turístico | **André Aventuras** | Levanta atrações, passeios, ingressos e horários |
| 🎭 Cultural | **Lara Culturas** | Costumes, etiqueta, segurança e dicas práticas |
| 💰 Financeiro | **Bruno Bolso** | Consolida orçamento, verifica viabilidade e sugere economias |
| 📅 Roteirista | **Camila Cronos** | Monta o cronograma dia a dia com horários realistas |
| 🎨 Designer | **Diego Designs** | Cria os cards visuais com mapas, programação e slide de custos |

---

## 🚀 Como Usar

### 1. Preencha o Brief
Abra `pipeline/data/travel-brief.md` e preencha todos os campos:
- Destinos e roteiro
- Datas e duração
- Orçamento máximo
- Perfil do viajante
- Preferências e proibições

### 2. Inicie o Squad
Com o brief preenchido, diga ao Claude Code:

```
Execute o Travel Squad com o brief em pipeline/data/travel-brief.md
```

### 3. Acompanhe o Pipeline
O squad seguirá este fluxo automaticamente:

```
📋 Brief interpretado (Marco)
        ↓
   ┌────┴────┬──────────┬─────────┬─────────┐
   ✈ Vera  🏨 Ricardo 🍽 Sofia 🗺 André 🎭 Lara
   └────┬────┴──────────┴─────────┴─────────┘
        ↓
💰 Análise financeira (Bruno)
        ↓
✋ CHECKPOINT — Você aprova o plano geral?
        ↓
📅 Roteiro dia a dia (Camila)
        ↓
✋ CHECKPOINT — Você aprova o roteiro?
        ↓
🎨 Cards e infográficos (Diego)
        ↓
✅ Entrega final
```

### 4. Checkpoints
O squad pausa em **2 momentos** para sua aprovação:
- **Checkpoint 1** — após a pesquisa de todos os especialistas (plano geral)
- **Checkpoint 2** — após a montagem do roteiro dia a dia

Em cada checkpoint você pode aprovar ou solicitar ajustes.

---

## 📁 Estrutura de Arquivos

```
travel-squad/
├── SQUAD.md                    # Este arquivo
├── squad.yaml                  # Configuração da equipe
├── state.json                  # Estado de execução
├── _memory/
│   └── memories.md             # Aprendizados entre execuções
├── agents/
│   ├── coordinator.agent.md    # Marco Destinos
│   ├── transport.agent.md      # Vera Rotas
│   ├── accommodation.agent.md  # Ricardo Conforto
│   ├── gastronomy.agent.md     # Sofia Sabores
│   ├── tourist-guide.agent.md  # André Aventuras
│   ├── cultural-guide.agent.md # Lara Culturas
│   ├── financial.agent.md      # Bruno Bolso
│   ├── itinerary.agent.md      # Camila Cronos
│   └── presentation.agent.md   # Diego Designs
├── pipeline/
│   ├── pipeline.yaml           # Definição das etapas
│   └── data/
│       ├── travel-brief.md     # ← PREENCHA AQUI
│       └── output-examples.md  # Exemplos de qualidade
└── output/
    └── {run_id}/               # Criado automaticamente
        ├── brief-parsed.md
        ├── transport-options.md
        ├── accommodation-options.md
        ├── gastronomy-map.md
        ├── tourist-attractions.md
        ├── cultural-guide.md
        ├── financial-analysis.md
        ├── itinerary-draft.md
        └── presentation-cards.md
```

---

## 💡 Dicas

- **Quanto mais detalhes no brief, melhor o resultado** — especialmente nas preferências e proibições
- **Confie nos checkpoints** — revise com calma antes de aprovar cada etapa
- **O financeiro é honesto** — se o orçamento for inviável, Bruno vai dizer
- **Os cards do Diego são para levar na viagem** — salve em PDF ou print
- **A memória acumula** — após cada viagem, o squad fica mais alinhado com suas preferências

---

## 🔧 Inspiração

Projeto inspirado no [OpenSquad](https://github.com/renatoasse/opensquad) — framework de multi-agentes especialistas.
