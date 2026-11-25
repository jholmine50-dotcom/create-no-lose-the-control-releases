<p align="center"><img src="img/logo.png" width="200" alt="Create: Don't Lose The Control"></p>

# Create: Don't Lose The Control

> Addon para **Create** e **Create: Aeronautics** — Minecraft **1.21.1** / **NeoForge**.
> Ideia e design: **mammut** · Código: feito com o Claude.

Nunca mais perca o controle de onde está a sua base (ou o seu dirigível). Este mod adiciona uma pequena
linha de produção "de precisão": você fabrica chips, monta uma máquina animada (o **Melhorador de Precisão**)
e com ela transforma blocos comuns em versões que **sabem a distância** até um ponto de referência.

![Melhorador de Precisão animando com uma Navigation Table dentro](img/melhorador_mesa.png)

---

## 📦 O que tem no mod

| Bloco / item | Como consegue | Para que serve |
|---|---|---|
| **Manual de Precisão** | Bancada (sem forma): **Livro + Liga de Andesito** | Livro no jogo com **UI própria**: índice, receitas, imagens e passo a passo de tudo |
| **Chip de Precisão** | Bancada: Revestimento de Andesito em cima, Mecanismo de Precisão embaixo | Peça base de tudo |
| **Caixa de Precisão** | Bancada: Chip no meio + 4 Revestimentos de Andesito em cruz | Vira o Melhorador |
| **Puxadores de Precisão** | **Montador Mecânico** do Create (grade 4×3): 4 botões / 4 eixos / 4 chips | Clique direito numa Caixa de Precisão → vira Melhorador |
| **Melhorador de Precisão** | Caixa + Puxadores | A máquina animada (3 slots, sem GUI) |
| **Magnetita de Precisão** | Melhorador: Chip + **Magnetita** (Lodestone) | Bússola presa nela mostra direção **e distância** |
| **Mesa de Navegação de Precisão** | Melhorador: Chip + **Navigation Table** | Mesa de navegação que solta **redstone pela distância** (4 modos + GUI) e é **fonte do Display Link** |
| **Precision Link** | Melhorador: Chip + **Redstone Link** | Alvo do Display Link que transmite os dados pros óculos |
| **Goggles Display** | Melhorador: Chip + **Óculos de Engenheiro** | Óculos vestíveis com **HUD em tempo real** (e ainda funcionam como Óculos de Engenheiro) |

### 📖 O Manual de Precisão (novo na 1.4.0)
Clique direito com o **Manual de Precisão** e abre um livro com visual próprio (moldura dourada, cores da logo):
- **Índice** clicável com todos os capítulos (Chip, Caixa, Puxadores, Melhorador, Magnetita, Mesa, Link, Goggles).
- **Receitas desenhadas** (bancada 3×3, Montador Mecânico 4×3 e as receitas do Melhorador).
- Passe o mouse num item pra ver o nome; **clique nele pra pular pro capítulo dele**.
- Virar página: setas, roda do mouse ou ←/→. Casinha (ou Backspace) volta pro índice. Ele lembra onde você parou.
- Em **português e inglês** (segue o idioma do jogo).

![Índice do manual](img/manual_indice.png)
![Receita no manual](img/manual_receita.png)

### O Melhorador de Precisão
- Tem 3 espaços internos, sem baú/GUI: **Chip**, **núcleo** (Magnetita *ou* Navigation Table) e **saída**.
- Clique direito com o item certo → ele "engole" 1 unidade e faz a animação `Idle2`.
- Mão vazia → pega o que está na saída.
- Quando os dois inputs estão cheios, ele **espera** qualquer animação acabar (menos a `Idle`), toca a animação
  `charge` e, no final, limpa os inputs e coloca o resultado na saída.
- Durante o `charge`, o cubo que aparece dentro da caixa é o núcleo: a magnetita do modelo **ou o modelo real
  da Navigation Table**, nas mesmas posições, rotações e escala da animação.
- **Funis, calhas, esteiras do Create, hoppers** e qualquer mod que use `IItemHandler` funcionam
  (entra só pelos inputs, sai só pela saída). Comparador lê o estado da máquina.

### A Magnetita de Precisão
Clique direito com uma **bússola** nela. A bússola aponta para ela (igual a uma Magnetita normal) e ainda mostra
a distância acima da hotbar, com a cor indo de verde (perto) para vermelho (longe).

![HUD da bússola](img/hud_bussola.png)

### A Mesa de Navegação de Precisão
Funciona **exatamente** como a Navigation Table do Create Aeronautics (ponteiro, itens aceitos, sinais laterais).
Mas se você colocar nela uma **bússola presa numa Magnetita de Precisão**, ela vira um sensor de distância e
manda redstone para os blocos em volta (inclusive o de baixo) conforme o **modo** (são 4):

| Modo | Sinal |
|---|---|
| **Somatic Redstone** | quanto mais **perto** da magnetita, mais forte |
| **Minimus Redstone** | quanto mais **longe** da magnetita, mais forte |
| **Dot to Dot** | mais forte no **meio do caminho** |
| **Dot else Dot** | o contrário: mais **fraco** no meio do caminho, forte nas pontas |

A "régua" usada é a **maior distância que a mesa já esteve** da magnetita, e ela só cresce. Assim o "meio do
caminho" existe de verdade. Explicação completa: [MESA_DE_NAVEGACAO.md](MESA_DE_NAVEGACAO.md).

**Shift + clique direito com a mão vazia** abre a GUI, no estilo das telas do Create:

![GUI da Mesa de Navegação de Precisão](img/gui_mesa.png)

---

## ⬇️ Instalação (para jogar)
1. NeoForge **21.1.247+** para Minecraft 1.21.1.
2. Na pasta `mods`: **Create 6.0.10+**, **Create: Aeronautics** (que já traz o *Create Simulated*), **Sable**
   e o `.jar` deste mod.

## 📡 Precision Link + Goggles Display
Como montar o HUD dos óculos: [PRECISION_LINK.md](PRECISION_LINK.md)

![HUD dos óculos](img/hud_goggles.png)

## ⬇️ Download
**[📥 Baixar a versão 1.4.0 (.jar)](https://github.com/jholmine50-dotcom/create-no-lose-the-control-releases/raw/main/downloads/create_dont_lose_the_control-1.21.1-1.4.0.jar)** e coloque na pasta `mods`.

Requisitos: NeoForge 21.1.247+, Create 6.0.10+, Create: Aeronautics e Sable. Novidades de cada versão: [CHANGELOG.md](CHANGELOG.md).

## 📄 Licença
Todos os direitos reservados ao autor (mammut). O código-fonte não é público.
Create, Create: Aeronautics/Simulated e Sable pertencem aos seus respectivos autores.
