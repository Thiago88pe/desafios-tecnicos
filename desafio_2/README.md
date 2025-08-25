# Desafio 2 - Produzindo código Python

### Uma nova página para exibir o conteúdo da planilha "editorias.csv" que está contida neste repositório.

Tenho um projeto Flask em Python rodando na porta 5000 com uma roda "/" que retorna "Hello, World". Crie uma rota `/editorias` que leia o arquivo `editorias.csv` (em UTF-8) que está no mesmo diretório usando o delimitado ";" e exiba o conteúdo em uma tabela HTML formatada com `<table>`. O arquivo CSV tem cabeçalhos: "Editoria", "Tom", "Paleta", "Texto de Exemplo". Gere o código completo, incluindo a importação de bibliotecas necessárias (como `pandas`, `csv`), tratamento de erros se o arquivo não existir, e integração no servidor Flask.

Dificuldades

* Garantir que a IA entenda o **formato real do CSV** (colunas, separador).
* O código pode depender do `pandas` ou `csv` puro.
* O HTML gerado pode precisar de ajustes estéticos.

### Uma página que acessa [https://catfact.ninja/fact](https://catfact.ninja/fact) e exibe a resposta formatada.

Adicione uma rota `/catfact` no meu app Flask que faça uma requisição GET para `https://catfact.ninja/fact`, utilizando a biblioteca `requests` e leia o campo `fact` da resposta JSON e renderiza um template HTML estilizada exibindo o fato. Inclua o tratamento de erro caso a API não responda.

Dificuldades

* Necessário garantir que a resposta seja formatada corretamente no HTML.

### Uma página em HTML5 que lê o horário do computador de quem está navegando no site e exibe o horário. Quando o mouse passa por cima do horário, a hora muda de cor.

Crie uma rota `/hora` no Flask que sirva uma página HTML5 com JavaScript. O JS deve capturar a hora local do navegador do usuário e exibir na tela em tempo real. Quando o mouse passar por cima do horário, a cor do texto deve mudar para vermelho, e quando sair, voltar ao normal. Use JavaScript para atualizar o horário e o efeito hover.

Dificuldades

* A IA pode gerar código com horário do servidor (em vez do cliente) se não for específico.
* É preciso pedir explicitamente por  **HTML + JS** .

### Uma nova página que ligue a câmera do usuário e tire uma foto do usuários quando ele clicar em um botão.

Crie uma rota `/camera` no Flask que exiba uma página HTML5 com JavaScript usando a API `navigator.mediaDevices.getUserMedia`. A página deve mostrar o vídeo da câmera do usuário em tempo real e ter um botão `Tirar Foto`. Ao clicar, deve capturar o frame atual e exibir a imagem capturada abaixo do vídeo.

Dificuldades

* A IA pode gerar código com APIs que só funcionam em HTTPS (câmera exige HTTPS ou `localhost`).
* Se quiser salvar a imagem no servidor, deve pedir isso explicitamente.
* Pode não tratar erros de permissão ou dispositivos não encontrados.
* Pode esquecer de parar a câmera após a captura.
