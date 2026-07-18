# Gerador de GPT para AGENTS.md e CLAUDE.md

Este repositório contém os arquivos-fonte utilizados para construir um GPT personalizado.

O objetivo desse GPT é auxiliar na criação de `AGENTS.md` e `CLAUDE.md` para projetos novos e existentes.

## Estrutura

- `INSTRUCOES.md`
  - Conteúdo copiado para o campo **Instruções** do GPT.

- `TEMPLATE-INSTRUCOES.md`
  - Arquivo anexado ao GPT como **Conhecimento**.
  - Contém tópicos, modelos e referências utilizadas pelo GPT.

- `LEVANTAMENTO-PROJETO.md`
  - Arquivo anexado ao GPT como **Conhecimento**.
  - Checklist exibido ao usuário quando o projeto já existe e o levantamento ainda não foi fornecido.
  - Deve ser copiado e executado em um agente local com acesso ao projeto (Claude Code, Codex etc.); a resposta é colada de volta na conversa com o GPT.

## Fluxo de trabalho do GPT

O GPT segue três etapas sequenciais, sem pular nem antecipar etapas:

1. **Levantamento inicial** — reúne objetivo, stack, ambiente e estrutura do projeto a partir do que o usuário fornecer (descrição direta para projeto novo, ou o checklist de `LEVANTAMENTO-PROJETO.md` respondido por um agente local para projeto existente).
2. **Composição em lote** — usa `TEMPLATE-INSTRUCOES.md` como catálogo e apresenta todos os tópicos aplicáveis de uma vez, cada um com opções (A/B/C…), observação e recomendação, para o usuário decidir em lote.
3. **Validação final e entrega** — apresenta o resumo consolidado, aguarda aprovação explícita do usuário e só então gera `AGENTS.md` e `CLAUDE.md` como arquivos para download.

## Importante

Este repositório **não é o GPT**.

Ele apenas contém os arquivos usados para configurá-lo.

Ao analisar este projeto, considere que:

- o GPT final será executado dentro do ChatGPT;
- `INSTRUCOES.md` corresponde ao campo **Instruções** do GPT;
- `TEMPLATE-INSTRUCOES.md` e `LEVANTAMENTO-PROJETO.md` são arquivos de **Conhecimento** anexados ao GPT;
- o GPT não possui acesso direto ao código dos projetos dos usuários;
- projetos existentes são analisados a partir de um levantamento fornecido pelo usuário (produzido por um agente local), e não pela inspeção do repositório;
- os arquivos finais (`AGENTS.md` e `CLAUDE.md`) só são gerados após validação explícita da composição, e são entregues como arquivos para download.

Toda sugestão deve considerar essas limitações do ambiente do GPT.