# Relatório de correções

**Nome:** Tiago Jarruge Saraiva
**Data:** 27/08/2026

---

## Instruções

Descreva cada alteração que você fez. Uma entrada por alteração.

Não é necessário preencher todas as entradas abaixo, nem se limitar a elas.
Acrescente quantas forem necessárias e apague as que não usar.

Para cada alteração, informe:

- **Onde estava o problema**, indicando o elemento ou o trecho do código
- **Por que era um problema**, dizendo quem é prejudicado e de que forma
- **O que você mudou**
- **Qual critério do WCAG** a correção atende, se você souber identificar

---

## Alteração 1 — Estrutura semântica e idioma

**Onde estava o problema:** A página não declarava o idioma e usava `div` para representar cabeçalho, navegação, conteúdo principal, seção e rodapé.

**Por que era um problema:** Leitores de tela e outras tecnologias assistivas tinham menos informações sobre a estrutura e a finalidade de cada região da página. A falta de idioma também pode prejudicar a pronúncia do conteúdo.

**O que mudei:** Declarei `lang="pt-BR"` e organizei a página com `header`, `nav`, `main`, `section`, `h1`, `h2` e `footer`. Também adicionei um link para pular diretamente ao conteúdo principal.

**Critério do WCAG:** 1.3.1 Informações e relações; 2.4.1 Ignorar blocos; 3.1.1 Idioma da página.

---

## Alteração 2 — Navegação acessível

**Onde estava o problema:** Os links do menu exibiam apenas um ponto (`.`) e usavam `javascript:` para navegar.

**Por que era um problema:** Pessoas que usam leitor de tela não recebiam o propósito dos links, e a navegação dependia de JavaScript. Isso também dificultava a compreensão da página atual.

**O que mudei:** Substituí os destinos por links HTML normais (sem `javascript:`) e usei rótulos visíveis e acessíveis para “Início”, “Ingressos” e “Contato”. Marquei “Ingressos” com `aria-current="page"` e dei um nome à região de navegação.

**Critério do WCAG:** 2.4.4 Finalidade do link; 2.4.8 Localização; 4.1.2 Nome, função, valor.

---

## Alteração 3 — Imagens e hierarquia de títulos

**Onde estava o problema:** A imagem do título não tinha `alt`, e os títulos “Tabela de preços” e “Compra por telefone” não eram identificados como cabeçalhos.

**Por que era um problema:** Usuários de leitor de tela poderiam perder informações importantes e não conseguiriam navegar rapidamente pela hierarquia do conteúdo.

**O que mudei:** Coloquei a imagem do título dentro de um `h1`, transformei “Compra por telefone” em `h2` e forneci textos alternativos para o logotipo, o título e a imagem que contém o telefone da central de vendas.

**Critério do WCAG:** 1.1.1 Conteúdo não textual; 1.3.1 Informações e relações; 2.4.6 Cabeçalhos e rótulos.

---

## Alteração 4 — Tabela de preços

**Onde estava o problema:** A tabela usava `td` em todas as células, não possuía `thead`, `tbody`, `caption` ou relações explícitas entre cabeçalhos e dados. A linha de sessões extras também usava células vazias.

**Por que era um problema:** Leitores de tela tinham dificuldade para associar cada preço ao espetáculo, à categoria e ao grupo de sessões correspondente.

**O que mudei:** Criei `caption`, `thead` e `tbody`, usei `th` com `scope="col"`, `scope="row"` e `scope="rowgroup"`, e acrescentei a expansão das abreviações por meio de `abbr` e `title`.

**Critério do WCAG:** 1.3.1 Informações e relações; 1.3.2 Sequência significativa.

---

## Alteração 5 — Botão de reserva

**Onde estava o problema:** “Reservar ingresso” era uma `div` com `onclick`.

**Por que era um problema:** Uma `div` não possui por padrão função de botão, foco ou acionamento por teclado. Pessoas que navegam sem mouse poderiam não conseguir iniciar a reserva.

**O que mudei:** Substituí a `div` por um elemento nativo `<button type="button">`, mantendo a mensagem de reserva e o estilo visual.

**Critério do WCAG:** 2.1.1 Teclado; 2.1.2 Sem bloqueio do teclado; 4.1.2 Nome, função, valor.

---

## Alteração 6 — Foco visível e contraste

**Onde estava o problema:** O CSS removia o contorno de foco e usava cores de baixo contraste no menu, nos textos de apoio e no rodapé.

**Por que era um problema:** Pessoas que navegam pelo teclado não conseguiam identificar o elemento ativo, e pessoas com baixa visão poderiam ter dificuldade para ler os textos.

**O que mudei:** Removi `outline: none`, adicionei um indicador de foco visível com `:focus-visible` e substituí as cores insuficientes por combinações com contraste maior.

**Critério do WCAG:** 1.4.3 Contraste mínimo; 2.4.7 Foco visível.

---

## Alteração 7 — Integração com o VLibras

**Onde estava o problema:** A página não oferecia o widget do VLibras inicialmente.

**Por que era um problema:** Usuários que precisam de tradução para Libras não tinham acesso ao recurso de apoio previsto para a página.

**O que mudei:** Adicionei a estrutura do widget e os scripts oficiais do VLibras ao final do `body`.

**Critério do WCAG:** 1.1.1 Conteúdo não textual; 4.1.2 Nome, função, valor.

---

## Verificação final

**Percorri a página inteira usando apenas o teclado:**
(X) sim   ( ) não

**Consegui alcançar e acionar todos os elementos interativos:**
(X) sim   ( ) não

**Ouvi a página com leitor de tela do começo ao fim:**
(X) sim   ( ) não

**O que o leitor de tela ainda anuncia de forma confusa, se houver:**

Alguns elementos são anunciados de forma muito longa, com adições desnecessárias.

---

## Observações

A aparência geral foi preservada. Os pontos do menu continuam visíveis, mas os
links passaram a ter nomes acessíveis. O carregamento do VLibras depende de
conexão com a internet quando a página é aberta.
