# Create: No Lose the Control

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
| **Chip de Precisão** | Bancada: Revestimento de Andesito em cima, Mecanismo de Precisão embaixo | Peça base de tudo |
| **Caixa de Precisão** | Bancada: Chip no meio + 4 Revestimentos de Andesito em cruz | Vira o Melhorador |
| **Puxadores de Precisão** | **Montador Mecânico** do Create (grade 4×3): 4 botões / 4 eixos / 4 chips | Clique direito numa Caixa de Precisão → vira Melhorador |
| **Melhorador de Precisão** | Caixa + Puxadores | A máquina animada (3 slots, sem GUI) |
| **Magnetita de Precisão** | Melhorador: Chip + **Magnetita** (Lodestone) | Bússola presa nela mostra direção **e distância** |
| **Mesa de Navegação de Precisão** | Melhorador: Chip + **Navigation Table** | Mesa de navegação que solta **redstone pela distância** (3 modos + GUI) |

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
manda redstone para os blocos em volta (inclusive o de baixo) conforme o **modo**:

| Modo | Sinal |
|---|---|
| **Somatic Redstone** | quanto mais **perto** da magnetita, mais forte |
| **Minimus Redstone** | quanto mais **longe** da magnetita, mais forte |
| **Dot to Dot** | mais forte no **meio do caminho** |

A "régua" usada é a **maior distância que a mesa já esteve** da magnetita, e ela só cresce. Assim o "meio do
caminho" existe de verdade. Explicação completa: [MESA_DE_NAVEGACAO.md](MESA_DE_NAVEGACAO.md).

**Shift + clique direito com a mão vazia** abre a GUI, no estilo das telas do Create:

![GUI da Mesa de Navegação de Precisão](img/gui_mesa.png)

---

## ⬇️ Instalação (para jogar)
1. NeoForge **21.1.247+** para Minecraft 1.21.1.
2. Na pasta `mods`: **Create 6.0.10+**, **Create: Aeronautics** (que já traz o *Create Simulated*), **Sable**
   e o `.jar` deste mod.

## ⬇️ Download
**[📥 Baixar a versão 1.1.1 (.jar)](https://github.com/jholmine50-dotcom/create-no-lose-the-control-releases/raw/main/downloads/create_no_lose_the_control-1.21.1-1.1.1.jar)** e coloque na pasta `mods`.

Requisitos: NeoForge 21.1.247+, Create 6.0.10+, Create: Aeronautics e Sable. Novidades de cada versão: [CHANGELOG.md](CHANGELOG.md).

## 📄 Licença
Todos os direitos reservados ao autor (mammut). O código-fonte não é público.
Create, Create: Aeronautics/Simulated e Sable pertencem aos seus respectivos autores.
