# Tutorial — TechInclusiva: Acessibilidade Web e HTML Semântico

## 1. Apresentação do projeto

O TechInclusiva é uma página web institucional criada para divulgar e receber inscrições para cursos gratuitos de tecnologia. O projeto utiliza HTML5 semântico e recursos de acessibilidade para facilitar a navegação por teclado e o uso com tecnologias assistivas.

## 2. Organização dos arquivos

A estrutura do projeto é:

```text
techinclusiva-acessivel/
├── index.html
├── style.css
├── README.md
└── TUTORIAL.md
```

O `index.html` concentra a estrutura e o conteúdo da página. O `style.css` controla apresentação visual, contraste, foco e responsividade.

## 3. Estrutura do HTML

O documento começa com:

```html
<!DOCTYPE html>
<html lang="pt-BR">
```

`<!DOCTYPE html>` informa que o documento utiliza HTML5. O atributo `lang="pt-BR"` identifica o idioma principal da página, ajudando tecnologias assistivas a aplicar pronúncia adequada.

### Header e nav

```html
<header>
  <h1>TechInclusiva</h1>
  <nav aria-label="Navegação Principal">...</nav>
</header>
```

`header` representa o cabeçalho da página. `nav` identifica a região de navegação. O `aria-label` fornece um nome descritivo para essa região.

### Main

```html
<main id="conteudo-principal">
```

`main` delimita o conteúdo principal da página. O `id` é usado pelo skip link para permitir que usuários de teclado pulem diretamente para esse conteúdo.

### Sections

```html
<section id="sobre" aria-labelledby="titulo-sobre">
  <h2 id="titulo-sobre">Sobre o Projeto</h2>
</section>
```

Cada `section` agrupa um assunto relacionado. O `aria-labelledby` associa a seção ao seu título, facilitando sua identificação por tecnologias assistivas.

### Figure, imagem e legenda

```html
<figure>
  <img src="..." alt="Pessoas em uma sala de aula de tecnologia utilizando computadores em ambiente colaborativo.">
  <figcaption>Alunos participando de um workshop presencial de desenvolvimento web.</figcaption>
</figure>
```

`figure` agrupa a imagem e seu contexto. `figcaption` fornece uma legenda. O `alt` apresenta uma descrição textual da imagem para usuários que não conseguem visualizá-la ou quando a imagem não é carregada.

### Footer

```html
<footer>
  <p>&copy; 2026 TechInclusiva. Todos os direitos reservados.</p>
</footer>
```

`footer` representa o rodapé do documento e concentra informações complementares.

## 4. Desenvolvimento do CSS

O CSS começa com um reset simples:

```css
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
```

Isso ajuda a manter dimensões previsíveis dos elementos.

O cabeçalho utiliza azul escuro e texto branco:

```css
header {
  background-color: #0d3b66;
  color: #ffffff;
}
```

A combinação proporciona alto contraste entre texto e fundo. O CSS também mantém o conteúdo centralizado e adapta a navegação para telas menores.

## 5. Recursos de acessibilidade

### Skip link

```html
<a class="skip-link" href="#conteudo-principal">
  Ir para o conteúdo principal
</a>
```

O link fica oculto visualmente até receber foco. Ele permite que quem navega por teclado pule rapidamente o cabeçalho.

### Foco visível

```css
a:focus,
button:focus,
input:focus,
select:focus,
textarea:focus {
  outline: 3px solid #0056b3;
  outline-offset: 2px;
}
```

O foco é destacado de forma clara durante a navegação com `TAB`.

### Imagem com alt

O atributo `alt` descreve o conteúdo relevante da imagem. Essa informação pode ser anunciada por leitores de tela.

### Links e botões

Os links possuem textos que indicam seu destino, enquanto o botão utiliza `Enviar Inscrição`, deixando clara sua ação.

## 6. Construção do formulário

O formulário utiliza:

```html
<form action="#" method="post">
  <fieldset>
    <legend>Dados Pessoais</legend>
```

`form` agrupa os controles destinados ao envio de dados. `fieldset` agrupa campos relacionados e `legend` identifica esse grupo.

Cada campo possui um `label` associado por meio de `for` e `id`:

```html
<label for="nome">Nome Completo:</label>
<input type="text" id="nome" name="nome">
```

Essa associação permite que tecnologias assistivas identifiquem corretamente o propósito do campo.

Os campos obrigatórios utilizam `required` e `aria-required="true"`. Os atributos `autocomplete="name"` e `autocomplete="email"` também ajudam no preenchimento dos dados.

## 7. Testes de acessibilidade

### Teste 1 — Navegação por teclado

Use `TAB` para avançar pelos links, campos e botão e `SHIFT + TAB` para voltar. Observe o contorno azul de foco.

### Teste 2 — Skip link

Ao carregar a página, pressione `TAB`. O primeiro elemento focável deve ser o link `Ir para o conteúdo principal`. Pressione `ENTER` para saltar ao conteúdo principal.

### Teste 3 — Leitor de tela

O projeto pode ser testado com o NVDA. Verifique se o leitor identifica o título, navegação, seções, imagem, campos e botão.

### Teste 4 — Contraste

Utilize uma ferramenta como o WebAIM Contrast Checker para verificar as combinações de texto e fundo. O projeto utiliza cores escolhidas para proporcionar contraste elevado.

### Teste 5 — Responsividade

Redimensione a janela do navegador ou utilize as ferramentas de desenvolvedor para testar uma largura próxima de 360–600 px. A navegação deve permanecer utilizável e o conteúdo deve se adaptar à tela.

## 8. Capturas de tela

Para atender à atividade, abra `index.html` no navegador e produza pelo menos:

1. **Print 1:** visão geral da página renderizada.
2. **Print 2:** página com o foco visível durante navegação por `TAB`, preferencialmente no formulário.
3. **Print 3:** resultado do teste de contraste ou inspeção de acessibilidade no navegador.

Insira essas imagens no documento final da atividade.

## 9. Conclusão

O desenvolvimento do TechInclusiva demonstra que acessibilidade pode ser incorporada desde a estrutura do HTML. O uso de elementos semânticos melhora a organização do documento, enquanto `alt`, labels, foco visível, skip link, contraste e navegação por teclado reduzem barreiras para diferentes usuários.

Uma das principais dificuldades é pensar nos elementos não apenas pela aparência visual, mas também pela forma como serão interpretados por tecnologias assistivas. O projeto mostra, na prática, a importância de uma estrutura semântica e de formulários corretamente associados.
