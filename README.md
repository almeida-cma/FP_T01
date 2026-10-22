# 🧠 Lógica de Programação — Guia Interativo com Portugol Webstudio

> **Material didático autônomo** para o TEMA 01 de cursos técnicos de Desenvolvimento de Sistemas: história das linguagens, níveis, paradigmas e prática de sintaxe com o **Portugol Webstudio**.

[![HTML5](https://img.shields.io/badge/HTML5-Monolítico-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/pt-BR/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-Mobile--First-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/pt-BR/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript)
[![Portugol](https://img.shields.io/badge/Portugol-Webstudio-ff8c42?style=for-the-badge)](https://portugol.dev)
[![Licença](https://img.shields.io/badge/Licen%C3%A7a-MIT-10b981?style=for-the-badge)](LICENSE)

---

## 📌 Sumário

- [Sobre o Material](#-sobre-o-material)
- [Demonstração](#-demonstração)
- [Estrutura da Aplicação](#-estrutura-da-aplicação)
- [Funcionalidades por Aba](#-funcionalidades-por-aba)
  - [1. Teoria Completa](#1-teoria-completa)
  - [2. Prática com Portugol](#2-prática-com-portugol)
  - [3. Exercícios](#3-exercícios)
- [Arquitetura Técnica](#-arquitetura-técnica)
- [Design System](#-design-system)
- [Guia de Uso em Sala](#-guia-de-uso-em-sala)
- [Limitações Conhecidas](#-limitações-conhecidas)
- [Roadmap](#-roadmap)
- [Licença & Créditos](#-licença--créditos)

---

## 🎯 Sobre o Material

Este documento HTML é um **material didático distribuído como arquivo único** (`index.html`) para alunos iniciantes em lógica de programação e Portugol. Ele foi projetado para funcionar **100% offline após o carregamento inicial** — todas as simulações e exercícios são processados em memória no navegador do próprio aluno, sem servidor backend.

**Objetivo pedagógico:** dar ao aluno um laboratório de leitura + prática onde ele pode:
- Consultar teoria consolidada sobre linguagens de programação.
- Copiar exemplos de código Portugol já formatados.
- Simular a saída de cada exemplo no navegador antes de rodar em `portugol.dev`.
- Testar respostas de exercícios de fixação.

**Público-alvo:** alunos do 1º módulo de cursos técnicos de Desenvolvimento de Sistemas.

**Ferramenta externa obrigatória:** [Portugol Webstudio](https://portugol.dev) — todos os blocos de código são copiáveis para lá e executáveis nativamente. Segundo o próprio changelog da plataforma, o Portugol Webstudio agora oferece **depuração passo a passo** com a nova aba **Variáveis**, painel de pontos de parada e atalhos de execução (*Depurar* — **Alt + P**; *Parar* — **Shift + F5**), além de mensagens de erro com linha e coluna destacadas — recurso ideal para complementar os exemplos deste material ([portugol.dev](https://portugol.dev)).

---

## 🚀 Demonstração

Abra o arquivo `index.html` em qualquer navegador moderno (Chrome, Firefox, Edge, Safari). Não requer build, servidor local nem dependências instaladas.

> 🌐 **Acesso online:** caso publicado no GitHub Pages, a URL ficará como `https://<usuario>.github.io/<repositorio>/`.

---

## 📁 Estrutura da Aplicação

O projeto é **um único arquivo** — escolha deliberada para permitir distribuição por e-mail, pendrive, Moodle ou qualquer outro canal, sem risco de quebra de caminhos relativos:

```text
logica-portugol/
│
└── index.html          # Material completo (HTML + CSS + JS embutidos)
```

### Diagrama de blocos internos do `index.html`

```text
<!DOCTYPE html>
├── <head>
│   ├── <meta> viewport (responsividade mobile)
│   ├── CDN: Font Awesome 6.0.0-beta3 (ícones)
│   ├── CDN: Google Fonts — Inter (14..32) + Fira Code (400,500)
│   └── <style> Design System do material
│
└── <body>
    ├── .container
    │   ├── .hero        → título, badge, link para portugol.dev
    │   ├── .tabs        → 3 botões de navegação (JS: switchTab)
    │   ├── #teoria      → aba de conteúdo teórico
    │   ├── #pratica     → aba com 4 exemplos + estrutura base
    │   ├── #exercicios  → aba com resolvidos + desafios + fixação
    │   └── .footer-note → créditos TEMA 01
    │
    └── <script>
        ├── switchTab(tabId)
        ├── copiarTexto(elementId)
        ├── simular(tipo) / simularEntrada() / simularCondicional() / simularLaco()
        ├── mostrarDicas()
        └── mostrarRespostas()
```

---

## ⚙️ Funcionalidades por Aba

### 1. Teoria Completa

Seção de leitura corrida, sem interação — 4 cards:

| Card | Conteúdo |
| --- | --- |
| **História e Evolução** | Linha do tempo em `.timeline` cobrindo 1940s → 2000+, com dois vídeos externos do YouTube (Coding Wave e Diolinux). |
| **Níveis de Programação** | Baixo vs. alto nível; diferença entre compilador e interpretador. |
| **Paradigmas** | Estruturada, Modular, Orientada a Objetos, Orientada a Eventos. |
| **Principais Linguagens** | Tabela comparativa: antigas (ALGOL, COBOL, FORTRAN), modernas (C#, C++, Java, Python, Ruby, Swift), web (JS, PHP, TS, HTML/CSS). |

Referências de vídeo: [O que é programação de computadores? (Coding Wave)](https://youtu.be/qyfFw6oWuTk) e [O que é "o tal do Algoritmo"? (Diolinux)](https://youtu.be/z1XTcKKRbKM).

### 2. Prática com Portugol

Seção central do material. Todos os blocos seguem **indentação de 4 espaços** e o esqueleto oficial do Portugol Webstudio:

```portugol
programa {
    funcao inicio() {
        // seu código aqui
        escreva("Olá, mundo!")
    }
}
```

**Exemplos implementados:**

| # | Título | Conceito | Simulação |
| --- | --- | --- | --- |
| 1 | Saudação | `escreva` | Estática |
| 2 | Entrada de Dados | `leia` + `cadeia` | `prompt()` do navegador |
| 3 | Estrutura Condicional | `se` / `senao` | `prompt()` com `parseFloat` |
| 4 | Laço de Repetição | `para` | Loop JS reproduzindo a saída |

**Painel lateral de variáveis:** a seção "Operadores e Estruturas" consolida operadores aritméticos (`+ - * / %`), comparação (`== != > < >= <=`) e lógicos (`e`, `ou`, `nao`), além do esqueleto de `se/senao`, `enquanto`, `para` e `escolha`.

### 3. Exercícios

**Resolvidos** (4): Ditado Popular, Par ou Ímpar, Média com Aprovação, Tabuada.

**Desafios** (6, sem resolução pronta — só dicas via botão):
1. Soma de dois números
2. Maior de três números
3. Fatorial
4. Contagem regressiva de 10 → 0
5. Calculadora com `escolha`
6. Primos até N

**Fixação** (8 perguntas do TEMA 01), com respostas ocultas que só aparecem após clicar em **Ver respostas**.

---

## 🏗 Arquitetura Técnica

### Padrão de código

- **HTML monolítico com CSS e JS integrados** — sem frameworks, sem bundlers, sem Node.js.
- **Vanilla JS puro (ES5/ES6)**: apenas 7 funções globais, todas declaradas no `<script>` final.
- **Estado controlado por classe** (`.tab-content.active`) — sem roteamento por hash, sem dependência de URL.

### Funções JavaScript

| Função | Responsabilidade |
| --- | --- |
| `switchTab(tabId)` | Alterna entre as 3 abas via `classList` e `event.target`. |
| `copiarTexto(elementId)` | Copia o `innerText` de qualquer `.code-block` para a área de transferência, com fallback `execCommand` para navegadores sem `navigator.clipboard`. |
| `simular(tipo)` | Simulação estática do Exemplo 1. |
| `simularEntrada()` | Usa `prompt()` para coletar nome e monta a saída interpolada. |
| `simularCondicional()` | Usa `prompt()` + `parseFloat` + comparação `>= 7` para determinar aprovado/reprovado. |
| `simularLaco()` | Loop `for` JS que reproduz a saída do `para` de 1 a 5. |
| `mostrarDicas()` / `mostrarRespostas()` | Exibe um `.output-console` oculto com conteúdo gerado dinamicamente. |

### Biblioteca de ícones e fontes

- **Font Awesome 6.0.0-beta3** via `cdnjs.cloudflare.com` — CSS parcialmente consumido, cobrindo os ícones `fa-code`, `fa-rocket`, `fa-book`, `fa-laptop-code`, `fa-puzzle-piece`, `fa-history`, `fa-microchip`, `fa-diagram-project`, `fa-table-list`, `fa-brain`, `fa-portugal`, `fa-copy`, `fa-graduation-cap`, `fa-youtube`.
- **Google Fonts**: `Inter` (variável `opsz,wght` 14..32, pesos 300/400/600/700) para o corpo e `Fira Code` (400/500) para blocos de código.

> ⚠️ **Dependência de CDN.** As duas folhas de estilo externas exigem internet no primeiro acesso. Em ambiente **offline puro** (ex.: prova em laboratório sem rede), os ícones e as fontes corretas não carregam — o material continua funcional, apenas com tipografia `system-ui` e quadrados vazios nos ícones.

### Paleta e design tokens

```css
--primary:      #ff8c42   /* laranja de destaque (botoes, accent, mark) */
--primary-dark: #e67e22   /* hover do primario */
--bg:           #f8fafc   /* slate-50 fundo */
--text:         #0f172a   /* slate-900 texto */
--surface:      #ffffff   /* cartoes */
--code-bg:      #1e293b   /* slate-800 blocos de codigo */
--code-fg:      #e2e8f0   /* slate-200 texto do codigo */
--console-fg:   #a5f3c3   /* verde terminal (saida simulada) */
--border:       #e2e8f0   /* slate-200 divisores */
```

### Breakpoints

Duas faixas apenas, seguindo abordagem **mobile-friendly** (não estritamente *mobile-first*):

```css
@media (max-width: 768px) {
    .hero h1  { font-size: 1.3rem; }
    .tab-btn  { padding: 0.4rem 1rem; font-size: 0.8rem; }
    .code-block { font-size: 0.7rem; white-space: pre-wrap; }
}
```

O grid `.grid-2cols` usa `repeat(auto-fit, minmax(340px, 1fr))` — colapsa automaticamente para 1 coluna em telas estreitas, sem necessidade de media query dedicada.

---

## 🎨 Design System

| Componente | Uso | Comportamento |
| --- | --- | --- |
| `.hero` | Cabeçalho da página | Gradiente `135deg` (#0f172a → #1e293b), radius `1.5rem`. |
| `.tabs` + `.tab-btn` | Navegação entre abas | Botões pill-shaped, `.active` recebe cor primária. |
| `.card` | Agrupamento de conteúdo | Superfície branca, radius `1.2rem`, sombra suave, borda cinza. |
| `.section-title` | Títulos internos | Borda esquerda `5px` na cor primária. |
| `.code-block` | Bloco de código Portugol | Fundo escuro, fonte monoespaçada, borda esquerda laranja. |
| `.output-console` | Simulação de saída | Fundo `#0f172a`, texto verde terminal, `pre-wrap`. |
| `.btn` / `.btn-outline` | Ações | Pill, hover com `scale(0.97)`. |
| `.timeline-item` | Linha do tempo histórica | Coluna esquerda com o ano em pílula laranja. |
| `.table-langs` | Comparativo de linguagens | Tabela com cabeçalho `slate-100`. |
| `.warning-box` | Aviso contextual | Amarelo `#fef3c7`, borda esquerda `#f59e0b`. |

---

## 🎓 Guia de Uso em Sala

**Trilha sugerida (60 minutos):**

1. **15 min | Exposição** — projetar a aba **Teoria Completa**, lendo a linha do tempo e a diferença compilador × interpretador.
2. **20 min | Prática guiada** — abrir a aba **Prática**, clicar em **Copiar** no Exemplo 1, colar em [portugol.dev](https://portugol.dev) e executar. Repetir com o Exemplo 3, usando o botão **Depurar** do Portugol Webstudio (Alt+P) para mostrar a execução passo a passo.
3. **15 min | Exercícios** — sortear um dos 4 resolvidos para a turma digitar na IDE, depois propor os desafios.
4. **10 min | Fixação** — aplicar as 8 questões como avaliação diagnóstica, revelando as respostas apenas no final.

**Avaliação sugerida:** pedir que cada aluno implemente **um dos 6 desafios** em `portugol.dev`, com captura de tela da execução — testa se o aluno consegue sair do exemplo pronto e resolver um problema novo.

---

## ⚠️ Limitações Conhecidas

| Item | Descrição | Impacto |
| --- | --- | --- |
| **Simulação simplificada** | As funções `simular*()` reproduzem a saída **esperada**, não executam o Portugol de fato. Um aluno pode alterar o código no `code-block` e a saída simulada continua a mesma. | Comportamento didático apenas; a execução real ocorre em `portugol.dev`. |
| **Sem persistência** | Nada é salvo no `localStorage` — recarregar a página restaura o estado original. | Aluno precisa refazer as escolhas a cada sessão. |
| **Dependência de CDN** | Font Awesome e Google Fonts exigem internet no primeiro carregamento. | Sem conexão, ícones não aparecem e a fonte cai para `system-ui`. |
| **`navigator.clipboard` requer HTTPS** | Em `file://` ou HTTP simples, o `copiarTexto` cai no fallback `execCommand`, que está obsoleto mas ainda funciona em Chrome/Edge. | Firefox pode bloquear o fallback em versões futuras. |
| **`event.target` em `switchTab`** | A função usa `event.target` implicitamente; funciona no Chrome/Firefox atuais mas quebraria em navegadores que aplicam `use strict` estrito. | Recomendável refatorar para receber o `event` como parâmetro. |
| **Acentuação no Portugol** | Os exemplos usam acentos em strings (`"Olá"`, `"não"`, `"café"`). O Portugol Webstudio aceita, mas em versões mais antigas do Portugol Studio podem ocorrer problemas de encoding. | Manter `meta charset="UTF-8"` no HTML é obrigatório. |

---

## 🗺 Roadmap

Sugestões de evolução para próximas versões:

- [ ] Substituir simulações fixas por um **mini-interpretador de Portugol em JS** (ou integrar via `<iframe>` ao Portugol Webstudio).
- [ ] Persistir respostas e progresso em `localStorage`.
- [ ] Adicionar **modo escuro** com `prefers-color-scheme`.
- [ ] Incluir **botão "Abrir no Portugol Webstudio"** com URL pré-carregada via parâmetro (verificar suporte na plataforma).
- [ ] Passar `event` explicitamente para `switchTab` (conformidade com `use strict`).
- [ ] Adicionar `<noscript>` com mensagem de fallback.
- [ ] Auditoria de acessibilidade: `aria-label` nos botões de ícone, `aria-selected` nas abas, foco visível.
- [ ] Blocos de exemplo com **numeração de linhas** para facilitar referência em aula.

---

## 📄 Licença & Créditos

Material didático do **TEMA 01** — Lógica de Programação, para o curso técnico de Desenvolvimento de Sistemas.

- **Portugol Webstudio:** [portugol.dev](https://portugol.dev) — ambiente oficial para execução dos exemplos.
- **Referências de vídeo:** [Coding Wave — O que é programação de computadores?](https://youtu.be/qyfFw6oWuTk) · [Diolinux — O que é "o tal do Algoritmo"?](https://youtu.be/z1XTcKKRbKM).
- **Ícones:** Font Awesome Free 6.0.0-beta3 (CC BY 4.0, SIL OFL 1.1, MIT).
- **Tipografia:** Inter e Fira Code (Google Fonts, SIL Open Font License).

Distribuído sob **MIT** — adapte livremente para sua instituição.
