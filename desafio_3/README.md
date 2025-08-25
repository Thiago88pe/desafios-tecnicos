# Desafio 3 - Planejando um projeto

## 1. Análise de Requisitos e Escopo

* Carregar arquivos MP4 e PNG
* Exibição sequencial em segunda tela
* Controle de tempo de exibição para PNGs

## 2. Stack Tecnológica Recomendada

* Escolha da linguagem, framework, bibliotecas

## 3. Arquitetura do Sistema

* **Camada de Apresentação (UI/UX)**

  * Pode ser simples (Tkinter, PyQt, web local).
  * Interface para arrastar arquivos, mudar ordem, alterar duração de PNGs.
* **Camada de Controle (Playlist Manager)**

  * Estrutura de dados que mantém a playlist.
  * Métodos: `add_file`, `remove_file`, `move_up`, `move_down`, `set_duration(img, t)`.
  * Responsável por notificar o player quando há mudanças.
* **Camada de Execução (Media Player Engine)**

  * Lida com reprodução.
  * Necessário suporte para **vídeo (mp4)** e  **imagem (png)** .

## 4. Interface do Usuário

* Slider para ajuste de duração de PNGs
* Visualização de segunda tela dedicada
* Upload de arquivos (drag & drop)

## 5. Controle de Segunda Tela

* Vamos criar uma **janela fullscreen** que abre na tela secundária
* Precisamos identificar os monitores
* O media player não deve abrir no monitor errado

## 6. Roadmap de Desenvolvimento

**Semana 1:** Setup do projeto e interface básica
**Semana 2:** Sistema de playlist e carregamento de arquivos
**Semana 3:** Reprodutor de vídeo e exibição de imagens
**Semana 4:** Controles de tempo e reordenação
**Semana 5:** Segunda tela e polimento
**Semana 6:** Testing e bug fixing
