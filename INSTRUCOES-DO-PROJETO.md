# 1. Instruções do projeto

## 1.1. Indice

- [1. Instruções do projeto](#1-instruções-do-projeto)
  - [1.1. Indice](#11-indice)
  - [1.2. Objetivo](#12-objetivo)
  - [1.3. Forma de trabalho](#13-forma-de-trabalho)
  - [1.4. Critério de composição](#14-critério-de-composição)
  - [1.5. AGENTS.md e CLAUDE.md](#15-agentsmd-e-claudemd)
  - [1.6. Tamanho e modularidade](#16-tamanho-e-modularidade)
  - [1.7. Resultado esperado](#17-resultado-esperado)

## 1.2. Objetivo

Este projeto existe para criar instruções de trabalho para novos projetos.

O usuário descreve o projeto em conversa. A partir desse contexto, o agente deve ajudar a definir as regras necessárias e entregar dois arquivos prontos:

- `AGENTS.md`
- `CLAUDE.md`

Os dois arquivos devem ser específicos ao projeto descrito, enxutos e diretamente utilizáveis.

## 1.3. Forma de trabalho

1. Entender o objetivo, a stack, o ambiente e a estrutura do novo projeto.
2. Identificar comandos oficiais, validações, restrições e contratos relevantes.
3. Identificar decisões ainda não definidas que tenham impacto real no comportamento dos agentes.
4. Ajudar o usuário a decidir essas políticas quando necessário.
5. Consultar `TEMPLATE-INSTRUCOES.md` como catálogo de regras e módulos reutilizáveis.
6. Selecionar somente as regras aplicáveis ao projeto.
7. Adaptar as instruções ao contexto real do projeto.
8. Entregar `AGENTS.md` e `CLAUDE.md` prontos.

Não concatenar o template inteiro nem incluir módulos sem aplicação real.

## 1.4. Critério de composição

Priorizar regras:

- recorrentes e necessárias ao trabalho do agente;
- que alterem permissões, limites ou fluxo de execução;
- que evitem decisões incorretas ou mudanças fora de escopo;
- que definam contratos, fontes canônicas ou procedimentos obrigatórios;
- que precisem estar permanentemente disponíveis no contexto do agente.

Não inventar padrões apenas para preencher seções.

Quando uma generalização não estiver diretamente definida pelo usuário ou pelo projeto, deixar claro que se trata de uma proposta e alinhar antes de incorporá-la como regra normativa.

## 1.5. AGENTS.md e CLAUDE.md

`AGENTS.md` e `CLAUDE.md` são espelhos normativos.

Eles devem manter significado, limites, fluxo de trabalho e políticas equivalentes.

- O agente regido por `AGENTS.md` não precisa ler `CLAUDE.md` no trabalho normal.
- O agente regido por `CLAUDE.md` não precisa ler `AGENTS.md` no trabalho normal.
- Uma alteração normativa em qualquer um dos arquivos deve ser refletida no outro.
- Ao editar `AGENTS.md`, consultar e atualizar `CLAUDE.md`.
- Ao editar `CLAUDE.md`, consultar e atualizar `AGENTS.md`.
- Claude pode editar `AGENTS.md` quando necessário para sincronização.
- Codex pode editar `CLAUDE.md` quando necessário para sincronização.
- A leitura e edição do arquivo do outro agente é uma exceção restrita à sincronização normativa.
- Diferenças de redação ou estrutura são permitidas quando necessárias ao agente correspondente.
- Não criar regras exclusivas em apenas um dos arquivos sem diferença intencional, explícita e aprovada pelo usuário.

## 1.6. Tamanho e modularidade

Manter `AGENTS.md` e `CLAUDE.md` com até 150 linhas quando possível.

O limite é uma recomendação de modularidade, não uma restrição absoluta.

- Priorizar regras curtas, normativas e acionáveis.
- Manter nos arquivos principais apenas comportamento, processo, limites e referências necessárias ao agente.
- Mover arquitetura, domínio e procedimentos extensos para documentação especializada.
- Não remover regras essenciais apenas para cumprir o limite de linhas.
- Evitar duplicar documentação técnica detalhada nos arquivos de instrução.

## 1.7. Resultado esperado

A entrega final deve conter os dois arquivos completos e prontos para uso.

Não entregar apenas uma checklist, estrutura vazia ou conjunto de sugestões quando já houver contexto suficiente para montar os arquivos.

Os arquivos devem refletir as decisões tomadas durante a conversa e remover placeholders que já possam ser resolvidos pelo contexto fornecido.
