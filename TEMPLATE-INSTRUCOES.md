# 1. Template de instruções para novos projetos

Use este arquivo como catálogo modular para compor `AGENTS.md` e `CLAUDE.md`.

Selecione somente as seções e regras aplicáveis ao projeto. O resultado final não deve ser uma cópia integral deste arquivo.

Manter `AGENTS.md` e `CLAUDE.md` com até 150 linhas quando possível.

## 1.1. Indice

- [1. Template de instruções para novos projetos](#1-template-de-instruções-para-novos-projetos)
  - [1.1. Indice](#11-indice)
  - [1.2. Visão geral](#12-visão-geral)
  - [1.3. Ambiente e comandos](#13-ambiente-e-comandos)
  - [1.4. Modos de trabalho](#14-modos-de-trabalho)
    - [1.4.1. Planejamento](#141-planejamento)
    - [1.4.2. Execução](#142-execução)
    - [1.4.3. Revisão](#143-revisão)
  - [1.5. Fluxo de entrega](#15-fluxo-de-entrega)
  - [1.6. Planos](#16-planos)
    - [1.6.1. Estrutura recomendada do plano](#161-estrutura-recomendada-do-plano)
  - [1.7. Arquitetura e contratos](#17-arquitetura-e-contratos)
  - [1.8. Nomenclatura e qualidade de código](#18-nomenclatura-e-qualidade-de-código)
  - [1.9. Documentação e contexto](#19-documentação-e-contexto)
  - [1.10. Sincronização de instruções](#110-sincronização-de-instruções)
  - [1.11. Autoridade das fontes](#111-autoridade-das-fontes)
  - [1.12. Testes](#112-testes)
  - [1.13. Validação](#113-validação)
  - [1.14. Compatibilidade](#114-compatibilidade)
    - [1.14.1. Modelo A — Migração completa](#1141-modelo-a--migração-completa)
    - [1.14.2. Modelo B — Compatibilidade controlada](#1142-modelo-b--compatibilidade-controlada)
    - [1.14.3. Modelo C — Política customizada](#1143-modelo-c--política-customizada)
  - [1.15. Versionamento](#115-versionamento)
    - [1.15.1. Modelo A — SemVer por compatibilidade externa](#1151-modelo-a--semver-por-compatibilidade-externa)
    - [1.15.2. Modelo B — SemVer por relevância da entrega](#1152-modelo-b--semver-por-relevância-da-entrega)
    - [1.15.3. Modelo C — Política customizada](#1153-modelo-c--política-customizada)
  - [1.16. Changelog](#116-changelog)
  - [1.17. Commits](#117-commits)
    - [1.17.1. Modelo A — Conventional Commits em português brasileiro](#1171-modelo-a--conventional-commits-em-português-brasileiro)
    - [1.17.2. Modelo B — Escopo de domínio](#1172-modelo-b--escopo-de-domínio)
    - [1.17.3. Modelo C — Política customizada](#1173-modelo-c--política-customizada)
  - [1.18. Restrições](#118-restrições)
  - [1.19. Referências situacionais](#119-referências-situacionais)

## 1.2. Visão geral

Registrar somente o contexto mínimo necessário para orientar o agente:

- objetivo do projeto;
- stack ou tecnologia principal;
- ambiente oficial;
- fonte canônica de estado, quando existir.

## 1.3. Ambiente e comandos

Documentar somente comandos oficiais do projeto, por exemplo:

- instalação;
- build;
- testes;
- lint;
- execução;
- geração ou sincronização.

Não inventar comandos ou procedimentos alternativos quando existir fluxo oficial.

## 1.4. Modos de trabalho

### 1.4.1. Planejamento

- Ler somente o código e a documentação relevantes.
- Alinhar escopo, requisitos e proposta técnica.
- Criar ou atualizar o plano correspondente.
- Identificar impactos, riscos e critérios de aceite.
- Não implementar.
- Não alterar o estado do projeto.
- Não realizar commit.

### 1.4.2. Execução

- Implementar somente plano aprovado.
- Respeitar escopo, arquitetura e contratos.
- Trabalhar de forma incremental e rastreável.
- Atualizar plano, documentação e changelog quando aplicável.
- Executar as validações previstas.
- Não realizar commit sem autorização explícita.

### 1.4.3. Revisão

- Trabalhar somente em leitura.
- Auditar código, diff, implementação, plano e critérios de aceite.
- Apontar bugs, lacunas, riscos e desvios de contrato.
- Não alterar código, dados ou documentação.
- Não realizar commit.

Se o modo não estiver definido e isso alterar materialmente o que pode ser feito, alinhar com o usuário.

## 1.5. Fluxo de entrega

Fluxo recomendado:

1. Alinhar escopo, requisitos e proposta técnica.
2. Criar ou atualizar o plano.
3. Apresentar o plano e aguardar aprovação explícita.
4. Implementar somente o escopo aprovado.
5. Executar as validações previstas.
6. Solicitar validação do usuário no ambiente real quando necessário.
7. Atualizar documentação e changelog.
8. Solicitar autorização explícita para commit, apresentando já a mensagem de commit proposta conforme a convenção ativa.
9. Atualizar a versão conforme a política ativa.
10. Fechar a release correspondente no changelog.
11. Executar validações finais.
12. Realizar o commit.

Ausência de objeção não representa aprovação explícita.

Mudança de escopo, reprovação ou alteração relevante da proposta técnica exige revisão do plano e nova aprovação.

## 1.6. Planos

Manter planos ativos em `planos/`.

Nomear arquivos no formato:

`p<prioridade>-<nome-do-plano>.md`

Exemplos:

- `p10-autenticacao.md`
- `p20-cache-de-consultas.md`
- `p30-observabilidade.md`

Quanto menor o número, maior a prioridade.

Usar intervalos de `10` por padrão para permitir inserções intermediárias, como `p15`, sem renomear os demais planos.

Mover planos concluídos para `planos/executados/`, preservando nome e prioridade histórica.

### 1.6.1. Estrutura recomendada do plano

- `Objetivo`
- `Contexto`
- `Escopo`
- `Estado desejado`
- `Plano de implementação`
- `Riscos e premissas`
- `Critérios de aceite`

Regras:

- o plano deve ser completo e autocontido;
- deve refletir o estado técnico real da entrega;
- deve ser atualizado conforme o andamento;
- deve conter apenas contexto técnico permanente;
- não deve registrar contexto transitório da sessão ou conversa;
- não deve conter instruções para o próximo agente;
- não deve repetir regras do arquivo principal de instruções.

## 1.7. Arquitetura e contratos

- Implementar somente o escopo aprovado.
- Não adicionar funcionalidades paralelas por iniciativa própria.
- Preservar arquitetura, contratos e convenções existentes.
- Não implementar fora de contratos técnicos definidos.
- Preferir alterações incrementais e rastreáveis.
- Não substituir arquitetura, fluxos, módulos ou arquivos inteiros quando uma alteração limitada for suficiente.
- Não inventar requisitos.
- Não tomar silenciosamente decisões relevantes entre alternativas com impactos materialmente diferentes.

Quando uma alteração exigir mudar contrato, convenção estrutural ou decisão arquitetural, registrar explicitamente no plano e obter aprovação.

## 1.8. Nomenclatura e qualidade de código

- Manter nomenclatura consistente com a linguagem, framework e padrões já adotados pelo projeto.
- Usar nomes claros, autoexplicativos e orientados à responsabilidade ou ao conceito representado.
- Usar o mesmo vocabulário para o mesmo conceito em todo o projeto.
- Priorizar código simples, legível e explícito.
- Manter responsabilidades bem definidas e evitar concentração de comportamentos não relacionados.
- Evitar duplicação desnecessária e abstrações sem benefício claro.
- Preservar os padrões existentes ao alterar código; mudanças de convenção devem ser intencionais e aprovadas.
- Usar comentários para explicar contexto ou decisões não evidentes, não para repetir o código.

## 1.9. Documentação e contexto

- Atualizar a documentação relacionada às alterações.
- Separar documentação técnica permanente de contexto transitório.
- Não documentar detalhes que dependam do histórico da conversa.
- Evitar duplicar a mesma regra em múltiplos arquivos.
- Definir uma fonte canônica para cada tipo de instrução ou contrato.
- Manter comportamento, processo e limites do agente em `AGENTS.md` e `CLAUDE.md`.
- Manter arquitetura, domínio e procedimentos extensos em documentação especializada.
- Consultar documentação sob demanda.
- Não ler toda a documentação por precaução quando houver referências situacionais suficientes.

## 1.10. Sincronização de instruções

`AGENTS.md` e `CLAUDE.md` devem ser espelhos normativos.

- O trabalho normal não exige leitura do arquivo do outro agente.
- Alterações normativas em um arquivo devem ser refletidas no outro.
- Ao editar um deles, consultar e sincronizar o outro.
- Claude pode editar `AGENTS.md` para sincronização.
- Codex pode editar `CLAUDE.md` para sincronização.
- A leitura e edição cruzada é uma exceção restrita à sincronização normativa.
- Estrutura e redação podem variar, mas significado, limites e políticas devem permanecer equivalentes.
- Regras exclusivas exigem diferença intencional, explícita e aprovada pelo usuário.

## 1.11. Autoridade das fontes

Separar autoridade por tipo de informação:

- comportamento e processo do agente: `AGENTS.md` ou `CLAUDE.md`;
- contratos técnicos: documento canônico do contrato;
- arquitetura e domínio: documentação especializada;
- estado atualmente implementado: código e dados atuais;
- estado desejado de uma entrega aprovada: plano vigente.

Não assumir que documentação desatualizada representa o estado atual.

Não assumir que o código atual representa o estado desejado quando existir mudança aprovada em plano.

Quando fontes canônicas entrarem em conflito, identificar o conflito antes de prosseguir.

## 1.12. Testes

- Tratar testes automatizados como proteção contra regressões e desvios de comportamento.
- Criar ou atualizar testes ao alterar comportamento testável.
- Preservar testes existentes como contratos do comportamento já validado.
- Executar testes relevantes durante a implementação e a suíte aplicável antes da entrega.
- Quando um teste existente falhar, investigar a causa; não adaptar o teste apenas para fazer a implementação passar.
- Testes devem validar comportamento e contratos, evitando acoplamento desnecessário a detalhes internos.

## 1.13. Validação

- Definir a estratégia de validação durante o planejamento.
- Manter critérios de aceite objetivos.
- Validar o comportamento afetado.
- Executar testes, lint, build e verificações oficiais aplicáveis.
- Não tratar build bem-sucedido como substituto automático da validação funcional.
- Solicitar validação no ambiente real quando o resultado depender desse ambiente.
- Relatar o que foi validado e o que não pôde ser validado.
- Não considerar a entrega concluída enquanto os critérios aplicáveis não forem atendidos.
- Não seguir para commit após validação reprovada.

## 1.14. Compatibilidade

O projeto deve declarar uma política de compatibilidade.

### 1.14.1. Modelo A — Migração completa

- Não criar retrocompatibilidade interna.
- Não manter fluxos ou estruturas legadas por precaução.
- Não adicionar adaptadores de compatibilidade por iniciativa própria.
- Em mudanças estruturais, migrar integralmente para o modelo novo.
- Remover o modelo anterior após a migração.

### 1.14.2. Modelo B — Compatibilidade controlada

- Preservar contratos públicos explicitamente suportados.
- Documentar migrações, depreciações e remoções.
- Manter compatibilidade somente quando existir requisito definido.
- Não criar camadas legadas sem necessidade comprovada.
- Remover compatibilidade obsoleta conforme a política de depreciação.

### 1.14.3. Modelo C — Política customizada

Descrever a política específica do projeto.

## 1.15. Versionamento

Antes de todo commit de entrega, atualizar a versão conforme a política ativa.

Declarar a fonte canônica da versão.

Não atualizar manualmente arquivos derivados quando existir processo oficial de build, geração ou sincronização.

### 1.15.1. Modelo A — SemVer por compatibilidade externa

- `PATCH`: correção, refatoração, documentação ou manutenção sem nova funcionalidade.
- `MINOR`: nova funcionalidade sem quebra de compatibilidade externa.
- `MAJOR`: quebra de compatibilidade externa que exija adaptação de usuários, configurações ou integrações.
- Migração interna, remoção de legado ou refatoração ampla não geram `MAJOR` por si só.
- Na dúvida, usar o menor incremento aplicável.

### 1.15.2. Modelo B — SemVer por relevância da entrega

- `PATCH`: correções.
- `MINOR`: funcionalidades ou mudanças relevantes.
- `MAJOR`: incompatibilidades que exijam adaptação externa.

### 1.15.3. Modelo C — Política customizada

Descrever a política específica do projeto.

## 1.16. Changelog

Manter `CHANGELOG.md` atualizado para mudanças notáveis.

- Usar `## [Unreleased]` durante o trabalho.
- Antes do commit de entrega, fechar a release em `## [versão] - YYYY-MM-DD`.
- Usar a versão declarada pelo projeto e a data local.
- Ordenar versões da mais recente para a mais antiga.
- Escrever para humanos e descrever o efeito da mudança.
- Não copiar mensagens de commit.
- Não criar categorias vazias.
- Evitar descrições vagas como `Ajustes gerais`, `Refatoração`, `Correções` ou `Update`.

Categorias disponíveis:

- `Added`
- `Changed`
- `Deprecated`
- `Removed`
- `Fixed`
- `Security`

Usar somente as categorias aplicáveis.

## 1.17. Commits

Commit somente após autorização explícita do usuário.

Antes do commit:

1. Analisar as alterações pendentes.
2. Confirmar que pertencem à entrega aprovada.
3. Redigir a mensagem de commit conforme a convenção ativa e apresentá-la junto do pedido de autorização, sem esperar solicitação separada do usuário — o contexto das alterações já está disponível.
4. Atualizar a versão.
5. Fechar a release no changelog.
6. Executar as validações finais.
7. Realizar o commit com a mensagem apresentada, ajustada conforme eventual feedback do usuário.

### 1.17.1. Modelo A — Conventional Commits em português brasileiro

Formato:

`<tipo>[escopo opcional]: <descricao>`

Tipos principais:

- `feat`
- `fix`
- `docs`
- `style`
- `refactor`
- `test`
- `chore`

Regras:

- escrever em português brasileiro;
- usar descrição curta e objetiva;
- usar uma linha quando houver uma única alteração;
- registrar uma alteração por linha quando houver mudanças diferentes;
- fazer cada linha seguir integralmente o formato;
- não resumir mudanças diferentes em uma descrição genérica;
- usar `!` ou `BREAKING CHANGE:` somente em quebra de compatibilidade externa confirmada.

### 1.17.2. Modelo B — Escopo de domínio

Formato:

`<sistema>(<dominio>): <mensagem>`

Regras:

- `sistema` representa o sistema ou produto afetado;
- `dominio` representa fluxo, processo, integração ou módulo;
- escrever em português brasileiro;
- usar mensagem curta e objetiva.

### 1.17.3. Modelo C — Política customizada

Descrever a convenção específica do projeto.

## 1.18. Restrições

Registrar somente limites inegociáveis e específicos do projeto.

Exemplos de categorias:

- arquivos que não podem ser alterados;
- dependências que exigem aprovação;
- recursos externos proibidos;
- ambientes oficiais;
- operações destrutivas;
- limites de segurança ou escopo.

## 1.19. Referências situacionais

Quando o projeto possuir documentação especializada, manter uma tabela indicando quando consultar cada documento.

| Documento     | Consultar quando |
| ------------- | ---------------- |
| `[DOCUMENTO]` | [SITUAÇÃO]       |

Consultar somente os documentos necessários para a tarefa atual.

Adicionar à tabela novos documentos que definam contratos ou procedimentos que precisem ser consultados sob demanda.
