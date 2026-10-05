# Site do Clube naCASA

Site de vendas do Clube naCASA — no ar em **https://clubenacasa.com.br**

Este repositório tem **tudo** o que o site precisa para funcionar. Não existe nada escondido, nada para instalar e nenhum programa obrigatório. É um único arquivo HTML mais as imagens.

---

## Como abrir o site no seu computador

Clique duas vezes no arquivo `index.html`. Ele abre no navegador exatamente como aparece na internet.

> **Se as imagens não carregarem**, é porque alguns navegadores bloqueiam arquivos abertos direto da pasta. Nesse caso use um servidor local — veja a seção "Para quem usa terminal" no fim deste arquivo. No dia a dia, abrir direto costuma funcionar.

---

## Como mudar o texto

Abra o `index.html` em qualquer editor de texto. Recomendamos o **[Visual Studio Code](https://code.visualstudio.com/)** (gratuito), mas o Bloco de Notas também serve.

O arquivo é dividido em seções marcadas com comentários bem visíveis:

| Seção | Começa na linha | O que é |
|---|---|---|
| `HERO` | 1025 | Primeira tela: título grande, preço e botão |
| `VÍDEO` | 1082 | O vídeo do YouTube |
| `ANTES E DEPOIS` | 1091 | As fotos com a barrinha de arrastar |
| `DEPOIMENTOS` | 1151 | Os prints de WhatsApp das clientes |
| `PARA QUEM` | 1183 | Mosaico "ideal para quem" |
| `SOBRE` | 1232 | "Mais que um curso. Uma comunidade." |
| `CURSOS` | 1271 | "O que você vai aprender" |
| `BÔNUS` | 1313 | Consultoria Mensal, artes, cupons |
| `FUNDADORAS` | 1348 | Analu e Luiza |
| `PREÇO` | 1380 | Valor, benefícios e botão de assinar |
| `FAQ` | 1414 | Perguntas frequentes |

Para achar uma seção rápido, use **Ctrl+F** e procure pelo nome dela, assim:

```
<!-- ═══ PREÇO ═══ -->
```

### A regra de ouro

Troque **só o que está entre as etiquetas**, nunca as etiquetas em si.

```html
<h3 class="ci-nm">Domine as cores</h3>
                  └──── troque esta parte ────┘
```

As etiquetas são os pedaços entre `<` e `>`. Se você apagar um `<h3>` ou um `</p>` sem querer, a página quebra. Se isso acontecer, é só desfazer com **Ctrl+Z**.

### Palavras em destaque

Texto dentro de `<strong>` aparece em **negrito**. Texto dentro de `<em>`, nos títulos grandes, aparece na **cor laranja da marca**.

```html
<p>Casa estilosa <strong>não é pra quem gasta muito</strong>.</p>
```

### Acentos

O arquivo está em UTF-8. Se você editar no Bloco de Notas, na hora de salvar escolha **Codificação: UTF-8** — senão os acentos viram símbolos estranhos.

---

## Como trocar uma imagem

A forma mais simples: **substitua o arquivo mantendo o mesmo nome.** Se você salvar uma foto nova por cima de `fundo-hero.jpg`, o site passa a usar a nova sem precisar mexer em código.

### Onde cada imagem aparece

| Arquivo | Onde aparece no site |
|---|---|
| `logo-nacasa.png` | Logo no topo e no rodapé |
| `fundo-hero.jpg` | Foto de fundo da primeira tela |
| `fundadoras-analu-luiza.jpg` | Foto da Analu e da Luiza na seção "As especialistas" |
| `color_palette_decor.png` | Card "Domine as cores" |
| `antes-depois/01antes.jpg` … `04depois.jpg` | Comparações antes/depois (os pares são 01, 02 e 04) |
| `ideal/alugou.jpg` | "aluguei um apê" |
| `ideal/estilo.png` | "descobrir meu estilo" |
| `ideal/reforma.jpg` | "reforma total" |
| `ideal/construir.jpg` | "construir a casa da vida" |
| `ideal/decorar.png` | "decorar sozinho um ambiente" |

### Se quiser usar um nome de arquivo diferente

Coloque a imagem na pasta e troque o nome dentro do `index.html`:

```html
<img src="ideal/alugou.jpg" alt="Aluguei um apê">
             └─ troque aqui ─┘
```

O `alt` é a descrição da imagem para quem usa leitor de tela e para o Google. Vale a pena atualizar junto.

### Imagens que vêm da internet

Alguns cards de curso usam fotos do Unsplash, carregadas direto da internet (começam com `https://images.unsplash.com/...`). Para usar uma foto própria no lugar, salve o arquivo na pasta e troque o endereço inteiro pelo nome do arquivo:

```html
<!-- antes -->
<img src="https://images.unsplash.com/photo-1555041469..." alt="">
<!-- depois -->
<img src="minha-foto.jpg" alt="Sala decorada">
```

### Tamanho das imagens

Deixe cada foto **abaixo de 500 KB**. Imagens pesadas deixam o site lento no celular, e site lento perde venda. Dá para comprimir de graça em [squoosh.app](https://squoosh.app/).

---

## O que NÃO convém mexer

- **Linhas 12 a 1003** (entre `<style>` e `</style>`) — é a aparência do site: cores, tamanhos, espaçamentos, layout no celular. Mexer aqui sem saber CSS quebra o visual.
- **A partir da linha 1463** (depois de `<script>`) — são as animações, o carrossel de depoimentos, a barrinha do antes/depois e o menu. Mexer aqui quebra as funcionalidades.

Se quiser mudar alguma cor, todas estão definidas logo no começo do `<style>`, em `:root`. As principais:

```css
--cta: #D97736;    /* laranja dos botões e destaques */
--text: #1A1A1A;   /* cor do texto */
--cream: #FFFEF9;  /* bege claro dos fundos */
```

---

## Links importantes dentro do site

Estes são os endereços que levam dinheiro para dentro. Se mudar a plataforma de pagamento, são eles que precisam ser trocados:

- **Botão de compra** (aparece 2 vezes: na primeira tela e na seção de preço)
  `https://lastlink.com/p/C6FC32D72/checkout-payment/`
- **Vídeo do YouTube**
  `https://www.youtube.com/embed/mCPIPgHcmys`
- **E-mail do rodapé**
  `clubenacasa@gmail.com`

Use Ctrl+F para achar cada um.

---

## Antes de publicar: confira estes 5 pontos

1. Abri o site e **todas as imagens apareceram**
2. **Cliquei nos dois botões de compra** e os dois abriram o checkout certo
3. Abri no **celular** (ou estreitei a janela do navegador) e nada ficou cortado ou fora da tela
4. **Reli os textos que mudei** — sem erro de digitação, sem etiqueta aparecendo no meio da frase
5. O **preço está correto** nos 2 lugares onde ele aparece (primeira tela e seção de preço)

---

## Como publicar as mudanças

**Leia isto antes de editar:** este repositório é uma **cópia independente** do site. Ele **não** está ligado ao ar — editar aqui **não** altera o `clubenacasa.com.br`, que é publicado a partir de outro repositório.

Isso é proposital: você pode mexer à vontade sem risco de derrubar o site que está vendendo.

### Para ver a sua versão no ar

Escolha um destes caminhos. Os três são gratuitos:

**GitHub Pages** (o mais rápido, sem sair do GitHub)
1. Aqui no repositório, vá em **Settings → Pages**
2. Em *Source*, escolha **Deploy from a branch**
3. Selecione a branch `main` e a pasta `/ (root)`, e clique em **Save**
4. Em uns 2 minutos o site estará em `https://SEU-USUARIO.github.io/clube-nacasa-site/`

**Netlify** — entre em [netlify.com](https://netlify.com), clique em *Add new site → Import an existing project*, conecte este repositório e confirme. Não preencha comando de build nem pasta de publicação: o site é HTML puro.

**Vercel** — entre em [vercel.com](https://vercel.com), clique em *Add New → Project*, importe este repositório e confirme. Mesma coisa: sem comando de build.

Nos três casos, depois de conectado, **toda alteração salva aqui publica sozinha** em cerca de 1 minuto.

### Como salvar uma alteração

**Pelo site do GitHub (mais simples):** abra o `index.html` aqui no GitHub, clique no lápis (✏️), edite, role até o fim e clique em **Commit changes**.

**Pelo computador:**

```bash
git add .
git commit -m "descrição do que mudou"
git push
```

### Se quiser levar a mudança para o site oficial

As alterações feitas aqui precisam ser passadas para quem cuida do `clubenacasa.com.br`. O caminho mais simples é avisar a pessoa responsável e indicar o que mudou.

---

## Para quem usa terminal

Para rodar um servidor local (resolve o problema de imagens que não carregam):

```bash
python -m http.server 8000
```

Depois abra `http://localhost:8000` no navegador. Para parar, aperte Ctrl+C.

---

## Resumo técnico

- HTML, CSS e JavaScript puros, em **um único arquivo** (`index.html`, ~1770 linhas)
- **Zero dependências**: sem build, sem npm, sem framework
- Fontes carregadas do Google Fonts (Montserrat, Anton, Cormorant)
- Algumas fotos de curso vêm do Unsplash por URL
- Responsivo: os ajustes para tablet e celular ficam no fim do `<style>`, nos blocos `@media`
