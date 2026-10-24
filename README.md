# Portfólio Front-end

Site de portfólio pessoal para desenvolvedores front-end, feito com **React**. Apresenta projetos, tecnologias, experiência profissional e um formulário de contato, em um layout responsivo, acessível e com tema claro e escuro.

![React](https://img.shields.io/badge/React-18.3-61DAFB?logo=react&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![Licença](https://img.shields.io/badge/licença-MIT-green)



## Prévia

**Início**

<img width="1400" height="622" alt="preview-inicio" src="https://github.com/user-attachments/assets/82a0dfb9-58ac-42fe-946e-dcddc391eaa5" />

**Projetos**

<img width="1400" height="719" alt="preview-projetos" src="https://github.com/user-attachments/assets/0082e031-86a8-49fe-bded-35c0fde214eb" />


**Sobre mim e experiência**

<img width="1400" height="729" alt="preview-sobre-experiencia" src="https://github.com/user-attachments/assets/1a64e4a3-29b8-4d80-ae5c-79b86daf471c" />


**Contato**

<img width="1702" height="648" alt="Sem título" src="https://github.com/user-attachments/assets/45ef5333-d3ca-47bf-b53f-0e838099829c" />


---

## Sumário

- [Prévia](#prévia)
- [Funcionalidades](#funcionalidades)
- [Tecnologias](#tecnologias)
- [Estrutura do projeto](#estrutura-do-projeto)
- [Como executar](#como-executar)
- [Como personalizar](#como-personalizar)
- [Formulário de contato](#formulário-de-contato)
- [Publicação](#publicação)
- [Acessibilidade](#acessibilidade)
- [Próximos passos](#próximos-passos)
- [Licença](#licença)
- [Autor](#autor)

---

## Funcionalidades

- **Galeria animada** no topo, com prints do site que trocam a cada 2 segundos, pausam ao passar o mouse e podem ser navegadas pelos indicadores.
- **Seletor de cor de destaque**: o visitante escolhe a cor e o site inteiro se adapta.
- **Tema claro e escuro**, com detecção automática da preferência do sistema e botão para alternar.
- **Seção de projetos** com cards e filtro por categoria (Web app, Site, Biblioteca).
- **Sobre mim** com a lista de tecnologias.
- **Linha do tempo** de experiência profissional.
- **Formulário de contato** que abre o aplicativo de e-mail do visitante com a mensagem pronta.
- **Layout responsivo**, do celular ao desktop.
- **Conteúdo editável em um só lugar**: todos os textos ficam em objetos no início do código.

## Tecnologias

| Tecnologia | Uso |
| --- | --- |
| [React 18](https://react.dev/) | Componentes, estado e efeitos (hooks `useState` e `useEffect`) |
| [Babel Standalone](https://babeljs.io/docs/babel-standalone) | Compilação do JSX diretamente no navegador |
| HTML5 e CSS3 | Estrutura, variáveis CSS (design tokens), Grid e Flexbox |
| Imagens WebP embutidas | Prints da galeria, gravados no próprio arquivo (data URI) |
| Google Fonts | Bricolage Grotesque (títulos) e Instrument Sans (texto) |

React e Babel são carregados por CDN, então **não é necessário instalar nada** para rodar o projeto.

## Estrutura do projeto

```
.
├── index.html     # Site completo: estilos, componentes React e dados
├── README.md      # Este arquivo
└── docs/          # imagens usadas neste README
    ├── preview-inicio.png
    ├── preview-projetos.png
    ├── preview-sobre-experiencia.png
    └── preview-contato.png
```

Componentes principais, todos dentro do `index.html`:

| Componente | Função |
| --- | --- |
| `App` | Controla o tema e a cor de destaque |
| `Header` | Navegação fixa e botão de tema |
| `Hero` | Apresentação, botões de ação e seletor de cor |
| `Slideshow` | Galeria de ilustrações com troca automática |
| `Projetos` | Cards de projetos com filtro |
| `Sobre` | Texto de apresentação e tecnologias |
| `Experiencia` | Linha do tempo profissional |
| `Contato` | Formulário que gera o e-mail |

> O arquivo foi gerado com o nome `portfolio.html`. Renomeie para `index.html` antes de publicar.

## Como executar

Não há dependências para instalar.

**Opção 1: abrir direto**

Dê dois cliques em `index.html` e ele abre no navegador. É necessário ter conexão com a internet, pois React, Babel e as fontes vêm de CDN.

**Opção 2: servidor local**

```bash
# com Python
python -m http.server 8000

# ou com Node
npx serve .
```

Depois acesse `http://localhost:8000`.

## Como personalizar

Procure o bloco `EDITE AQUI` no início do script do `index.html`. Ele contém os dados do site:

```js
const PERFIL = {
  nome: "Seu Nome",
  cargo: "Desenvolvedor front-end",
  resumo: "Texto curto sobre você.",
  email: "voce@email.com",
  github: "https://github.com/seu-usuario",
  linkedin: "https://linkedin.com/in/seu-usuario",
};
```

| Objeto | O que controla |
| --- | --- |
| `PERFIL` | Nome, cargo, resumo, e-mail e redes sociais |
| `PROJETOS` | Título, descrição, tecnologias, categoria e links de demo e código |
| `HABILIDADES` | Lista de tecnologias na seção Sobre |
| `EXPERIENCIA` | Itens da linha do tempo |
| `CORES` | Opções do seletor de cor de destaque |

**Cores e fontes:** as cores do tema ficam nas variáveis CSS em `:root` (`--bg`, `--ink`, `--accent` e outras). Para trocar a paleta, edite apenas esses valores.

**Galeria:** os slides ficam na constante `SLIDES`. Para usar outras imagens, como prints dos seus projetos, troque o `src` de cada slide por o caminho de um arquivo seu:

```jsx
{ t: "Painel Financeiro", svg: <img src="img/painel.png" alt="Tela do painel financeiro" /> }
```

O tempo de troca está no `setInterval` do componente `Slideshow` (valor em milissegundos, hoje `2000`).

## Formulário de contato

O botão **Enviar por e-mail** usa um link `mailto:`: ele abre o aplicativo de e-mail do visitante com destinatário, assunto e mensagem preenchidos. O envio **não é automático**, e o visitante precisa apertar enviar no próprio aplicativo.

Para receber as mensagens direto na sua caixa de entrada, use um serviço de formulários, como [Formspree](https://formspree.io/), [EmailJS](https://www.emailjs.com/) ou [Web3Forms](https://web3forms.com/). Depois de criar a conta, substitua a função `enviar` do componente `Contato` por uma requisição `fetch` para o endereço que o serviço fornecer.

## Publicação

Por ser um site estático, ele pode ser hospedado gratuitamente em:

- **GitHub Pages**: envie o projeto para um repositório, vá em *Settings → Pages* e selecione a branch `main`.
- **Vercel**: importe o repositório em [vercel.com](https://vercel.com/) e publique, sem configuração extra.
- **Netlify**: arraste a pasta do projeto em [app.netlify.com/drop](https://app.netlify.com/drop).

## Acessibilidade

- Navegação completa por teclado, com foco visível.
- Rótulos (`aria-label`) nos botões de ícone, nos indicadores da galeria e nas ilustrações.
- A galeria pausa ao receber foco ou passar o mouse.
- Quem usa "reduzir movimento" no sistema não vê a troca automática de slides.
- Contraste de cores adequado nos temas claro e escuro.

## Próximos passos

Ideias para evoluir o projeto:

- [ ] Migrar para [Vite](https://vite.dev/) com componentes em arquivos separados (recomendado para produção, já que o Babel no navegador deixa o primeiro carregamento mais lento)
- [ ] Trocar as ilustrações por prints reais dos projetos
- [ ] Integrar o formulário com Formspree ou EmailJS
- [ ] Adicionar versão em inglês
- [ ] Incluir seção de blog ou artigos
- [ ] Adicionar testes com Vitest e React Testing Library

## Licença

Distribuído sob a licença MIT. Você pode usar, copiar e modificar livremente este projeto.

## Autor

**Elias Dias**
Desenvolvedor front-end

[GitHub]https://github.com/Eliaspessoa · [LinkedIn](https://www.linkedin.com/in/elias-dias-adsti/) · [Email](eliasdiiaz220@gmail.com)
