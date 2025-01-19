<h1>
    <a href="https://www.dio.me/">
     <img align="center" width="40px" src="https://hermes.digitalinnovation.one/assets/diome/logo-minimized.png"></a>
    <span>Microsoft AI for Tech – Criando Prompts Inteligentes</span>
</h1>

# :computer: Desafio de projeto: Documentando Projetos Automáticos Utilizando IA

Orientações para o projeto:

- Escolha um projeto seu ou use o repositório apresentado na aula.
- Utilize uma ferramenta de IA para documentar o projeto (exemplos: ChatGPT, Microsoft Copilot, GitHub Copilot, ferramentas de geração de diagramas, entre outras).
- Estruture a documentação com seções e imagens.

# :bulb: Solução do desafio

Utilizei o Gemini Advance 1.5 Pro with Deep Research para desenvolver a documentação do repositório [DetonaRalph](https://github.com/tsdes-santiago/DIO_RiHappyFrontEnd/blob/main/DetonaRalph/README.md). Utilizei o prompt:

```
Crie uma documentação para substituir o README.md do repositório https://github.com/tsdes-santiago/DIO_RiHappyFrontEnd/tree/main/DetonaRalph 
baseado no formato do readme.me de https://github.com/felipeAguiarCode/MegaApiDotnetCore/blob/master/README.MD
```
O plano de pesquisa desenvolvido pela ferramenta de IA:

```

(1) Acesse o repositório https://github.com/tsdes-santiago/DIO_RiHappyFrontEnd/tree/main/DetonaRalph e analise o código e a estrutura do projeto.
(2) Acesse o arquivo README.MD em https://github.com/felipeAguiarCode/MegaApiDotnetCore/blob/master/README.MD e identifique o formato e as seções utilizadas.
(3) Crie um novo arquivo README.md para o repositório DetonaRalph.
(4) Utilize o formato do README.MD do repositório MegaApiDotnetCore como base para a estrutura do novo README.md.
(5) Inclua as seguintes seções no novo README.md, adaptando o conteúdo ao projeto DetonaRalph:
- Título do projeto
- Descrição do projeto
- Funcionalidades
- Tecnologias utilizadas
- Como executar o projeto
- Como contribuir para o projeto
- Licença
(6) Utilize uma linguagem clara e objetiva na escrita do README.md.
(7) Revise o README.md para garantir que todas as informações estão corretas e completas.
(8) Substitua o README.md antigo pelo novo no repositório DetonaRalph.
```

A nova documentação foi gerada com alguma alucinações. Segue o resultado após os ajustes necessários:

# Detona Ralph
<img src="https://raw.githubusercontent.com/tsdes-santiago/DIO_RiHappyFrontEnd/refs/heads/main/DetonaRalph/detonaRalph.png">

## Descrição do Projeto

Este projeto consiste em um jogo web simples inspirado no filme Detona Ralph, desenvolvido como parte do programa de formação da Digital Innovation One. O jogo utiliza HTML, CSS e JavaScript para criar uma experiência interativa onde o jogador deve clicar no personagem Ralph em um cenário 2D análogo a jogos do estilo Whack-a-mole.

## Arquitetura do Jogo

```console
DetonaRalph/
├── detonaRalph.png
├── index.html
├── README.md
└── src
    ├── audios
    │   ├── hit.m4a
    │   └── miss.m4a
    ├── images
    │   ├── favicon.jpg
    │   ├── player.png
    │   ├── ralph.png
    │   └── wall.png
    ├── scripts
    │   └── engine.js
    └── styles
        ├── main.css
        └── reset.css
```

O código do jogo é estruturado em três arquivos principais:

- **index.html**: Contém a estrutura HTML do jogo, incluindo elementos para o cenário, o personagem, os doces e o placar.
- **main.css**: Define o estilo visual do jogo, como as cores, as fontes e o posicionamento dos elementos.
- **engine.js**: Contém a lógica do jogo, incluindo as funções para gerar a posição do personagem, detectar cliques certos e errados e atualizar o placar.

## Tecnologias Utilizadas

-   HTML: Estrutura do jogo.
-   CSS: Estilização visual do jogo.
-   JavaScript: Lógica e interatividade do jogo.

## Como Executar o Projeto

1.  Faça o download ou clone o repositório.
2.  Abra o arquivo `index.html` em seu navegador web.

## Como Contribuir para o Projeto

Sinta-se à vontade para contribuir com o projeto! Você pode:

-   Reportar bugs e problemas.
-   Sugerir novas funcionalidades.
-   Melhorar o código existente.
-   Criar _pull requests_ com suas alterações.
