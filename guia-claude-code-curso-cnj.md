# Guia — Editar e expandir o curso no Claude Code

Este guia mostra como abrir, editar e ampliar o arquivo **`curso-eixo-produtividade-premio-cnj.html`** usando o **Claude Code**, com prompts prontos para copiar e colar. Você não precisa saber programar — basta descrever o que quer.

---

## 1. O que você já tem

Na sua pasta há dois arquivos:

- **`curso-eixo-produtividade-premio-cnj.html`** — o curso interativo completo (abre em qualquer navegador, funciona offline).
- **`guia-claude-code-curso-cnj.md`** — este guia.

O curso é um **único arquivo HTML autocontido**: todo o conteúdo, o visual e a interatividade (navegação, barra de progresso e quiz) estão dentro dele. Isso facilita compartilhar — basta enviar o `.html`.

---

## 2. Instalar o Claude Code (uma vez)

O Claude Code é uma ferramenta de linha de comando. Para instalar:

1. Instale o **Node.js** (versão 18 ou superior) — em `nodejs.org`.
2. No terminal, rode:

   ```bash
   npm install -g @anthropic-ai/claude-code
   ```

   > Não use `sudo`. Se aparecer erro de permissão, siga as orientações de instalação da documentação oficial.

3. Faça login na primeira vez:

   ```bash
   claude
   ```

   Será aberto o navegador para autenticar com sua conta Claude.

Documentação oficial de instalação: <https://docs.claude.com/en/docs/claude-code/setup>

---

## 3. Abrir o projeto

No terminal, entre na pasta do curso e inicie o Claude Code apontando para ela:

```bash
cd "/caminho/para/Premio CNJ de Qualidade - Justica Eleitoral"
claude
```

A partir daí, é só conversar. O Claude Code enxerga os arquivos da pasta e edita o HTML diretamente.

### Como ver o resultado
Dê **duplo clique** no arquivo `.html` para abrir no navegador. A cada edição, basta **atualizar a página** (F5). Para uma prévia que recarrega sozinha, peça ao Claude Code: *“suba um servidor local para eu visualizar o curso”*.

---

## 4. Como o curso é organizado (para pedidos precisos)

Saber a estrutura ajuda a pedir mudanças certeiras:

- Cada módulo é uma seção `<section class="modulo">`. O **menu lateral é gerado automaticamente** a partir dessas seções — para criar um módulo novo, basta acrescentar outra seção; o menu e a numeração se ajustam sozinhos.
- O título de cada módulo fica no atributo `data-titulo`, e o grupo do menu, em `data-grupo`.
- O **quiz** é montado por uma lista chamada `perguntas`, no `<script>` ao final do arquivo. Cada item tem a pergunta (`p`), as opções (`o`), o índice da correta (`c`) e o comentário (`fb`).

Você pode citar esses nomes nos pedidos, mas não precisa: descrever em português funciona.

---

## 5. Prompts prontos (copie, cole e ajuste)

### a) Corrigir ou refinar um conteúdo
```
No arquivo curso-eixo-produtividade-premio-cnj.html, no módulo "5. IAD",
revise a explicação para deixá-la mais simples, mantendo os números e
a fórmula exatamente como estão. Não altere outros módulos.
```

### b) Adicionar um novo módulo
```
Adicione um novo módulo ao curso, logo após o módulo "Visão geral do eixo",
intitulado "Como os dados chegam ao CNJ", explicando de forma didática o
fluxo DataJud → Justiça em Números → Prêmio. Use o mesmo estilo visual,
componentes (cards, callouts) e estrutura <section class="modulo"> dos
demais módulos. O menu lateral deve atualizar automaticamente.
```

### c) Criar cursos para os outros eixos
```
Use este curso como modelo e crie um novo arquivo
"curso-eixo-governanca-premio-cnj.html" cobrindo o eixo Governança
(Anexo I da Portaria CNJ nº 471/2025), mantendo o mesmo layout, navegação
e quiz. Baseie todo o conteúdo no PDF da Portaria que está nesta pasta e
destaque o que se aplica à Justiça Eleitoral.
```
> Troque "Governança" por "Transparência" ou "Dados e Tecnologia" para os demais.

### d) Gerar slides para a aula presencial
```
A partir do conteúdo de curso-eixo-produtividade-premio-cnj.html, crie uma
apresentação em PowerPoint (.pptx) com um slide por indicador, incluindo
título, definição, fórmula, tabela de pontuação da Justiça Eleitoral e um
exemplo. Visual sóbrio e institucional.
```

### e) Gerar uma apostila (.docx) ou PDF
```
Gere uma apostila em Word (.docx) com todo o conteúdo do curso, organizada
em capítulos por módulo, com sumário e numeração de páginas. Depois, gere
também uma versão em PDF.
```

### f) Ampliar o quiz
```
No quiz do curso, acrescente 5 novas questões de nível intermediário sobre
o IAD e as Metas Nacionais aplicáveis à Justiça Eleitoral, seguindo o mesmo
formato da lista "perguntas" (pergunta, opções, índice da correta e
comentário explicativo).
```

### g) Atualizar para os parâmetros de 2027
```
Os Anexos da premiação de 2027 do Prêmio CNJ de Qualidade foram publicados
(arquivo nesta pasta). Compare com os parâmetros de 2026 usados no curso e
atualize apenas os valores que mudaram, deixando uma nota em cada módulo
indicando o ano de referência.
```

### h) Aplicar a identidade visual do TRE-GO
```
Ajuste as cores e o cabeçalho do curso para a identidade visual do TRE-GO,
mantendo bom contraste e acessibilidade. Se eu fornecer o logotipo (arquivo
na pasta), inclua-o no topo do menu lateral.
```

---

## 6. Boas práticas

- **Confira sempre contra a fonte.** Peça ao Claude Code para validar números e parâmetros contra o PDF da Portaria antes de fechar uma versão.
- **Peça mudanças pequenas e específicas.** “Altere o módulo X” funciona melhor que “refaça o curso”.
- **Guarde versões.** Antes de uma grande mudança, faça uma cópia do `.html` (ex.: `...-v2.html`).
- **Teste depois de editar.** Abra no navegador e clique pelos módulos e pelo quiz.

---

## 7. Dica de prompt eficaz

Bons pedidos costumam ter: **contexto** (qual arquivo, qual módulo), **o que fazer** (ação clara), **o que preservar** (números, estilo) e **o formato** (HTML, .pptx, .docx). Exemplo completo:

```
Contexto: arquivo curso-eixo-produtividade-premio-cnj.html, módulo "2. Metas Nacionais".
Tarefa: acrescentar um quadro com as datas-base de cada meta da Justiça Eleitoral.
Preserve: a pontuação e o restante do módulo.
Fonte: use o PDF da Portaria 471/2025 nesta pasta.
```

---

*Material de apoio à capacitação interna do TRE-GO. Os parâmetros do curso referem-se à premiação de 2026 (Portaria CNJ nº 471/2025); confira os Anexos de 2027 quando publicados.*
