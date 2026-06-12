<div align="center">

# 🛩️🤖 autopilot-cmo

**Dê uma meta. Um diretor de marketing autônomo planeja, age, mede e se adapta — dia a dia, dentro do chat do Claude Code.**

Você diz "quero 350 leads em 7 dias". O CMO decide o plano de cada dia (sempre em rascunho), o mundo responde com ruído — nunca como o projetado — e ele replaneja com base no que funcionou. No fim: bateu ou não bateu, e por quê.

![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-Skill-7C3AED?style=for-the-badge)
![Sem API key](https://img.shields.io/badge/API%20key-n%C3%A3o%20precisa-38d39f?style=for-the-badge)
![Português](https://img.shields.io/badge/idioma-PT--BR-ff7a45?style=for-the-badge)
![License MIT](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge)

</div>

---

## ⚡ O que é

`autopilot-cmo` é uma **skill do Claude Code** que demonstra um agente guiado por **objetivo, não por comando**: o loop *planejar → agir → medir → replanejar*. Não é "me escreve um post" — é um CMO que olha o placar todo dia e muda a estratégia quando a realidade desmente a projeção.

> O agente não executa ordens. Ele persegue a meta.

## 🚀 Instalação (30 segundos)

```bash
# 1. Clone
git clone https://github.com/ojogadorcaro/autopilot-cmo.git

# 2. Copie a skill pro Claude Code (global)
cp -r autopilot-cmo/skill ~/.claude/skills/autopilot-cmo
# Windows (PowerShell):
# Copy-Item -Recurse autopilot-cmo\skill "$env:USERPROFILE\.claude\skills\autopilot-cmo"
```

Pronto. Abra o Claude Code e dê uma meta:

> *"quero 350 leads em 7 dias, hoje capto uns 20/dia"*

**Não precisa de chave de API** — roda 100% no chat.

## 🧩 Como funciona

```
sua meta (alvo numérico + prazo + linha de base)
        │
        ▼   ┌──────────────────────────── repete N dias ─┐
🧠 CMO DECIDE → analisa o histórico (projetado vs. real), │
        │      corta o que não rendeu, dobra o que rendeu │
        │      → 2–4 ações do dia (SEMPRE em rascunho)    │
        │      → projeção de leads + relatório matinal    │
        ▼                                                 │
🌍 O MUNDO RESPONDE → resultado real = projetado × ruído  │
        │             (60%–140% — a realidade nunca bate) │
        ▼                                                 │
📈 PLACAR → acumulado/meta, ritmo necessário ─────────────┘
        ▼
🏁 FECHAMENTO → bateu ou não (sem maquiar) + curva
               projetado vs. real + o que o CMO aprendeu
```

## 🔒 Governança (o ponto sério do projeto)

Toda ação sai com **`status: "rascunho"`**. O agente **nunca publica, nunca gasta verba, nunca ativa nada sozinho** — plugado numa plataforma real (ex.: Meta Ads), tudo continuaria saindo como rascunho/PAUSED com aprovação humana obrigatória. Autonomia de decisão ≠ autonomia de execução.

## 📊 Exemplo real (de `data/output/`)

Meta: **350 cadastros em 7 dias** num grupo VIP de finanças pessoais (baseline 20/dia):

| Dia | Projetado | Real | |
|---|---|---|---|
| 1 | 55 | **73** | acima — dobra o formato |
| 2 | 85 | **118** | pico — surfa a onda |
| 3 | 80 | **65** | esfriou — troca o ângulo |
| 4–6 | 28–30 | 21–23 | vacas magras — segura o ritmo |
| 7 | 35 | **47** | sprint final |

**Final: 369 / 350 — meta batida** ✅ (e dá pra ver o CMO mudando de estratégia no dia 3, quando a realidade virou). Simulação completa: [data/output/cmo-leads.json](data/output/cmo-leads.json)

## 🔑 Requisitos

| Quer o quê? | Precisa de |
|---|---|
| O loop completo de N dias + relatórios | **Nada** (só o Claude Code) |

## 📂 Estrutura

```
skill/SKILL.md      # a skill — o produto inteiro, chat-native
data/requests/      # meta de exemplo
data/output/        # simulação real de 7 dias (369/350)
```

## Licença

MIT — use, adapte, leve a ideia pro seu projeto.

---

<div align="center">

_Parte da coleção **Vibe Coding & Marketing**. Quer uma ferramenta dessas na sua operação? Me chama._

</div>
