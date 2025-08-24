# Desafio 1 - Flask e FastHTTP

### Instruções de como rodar cada projeto

### Dependências Necessárias:

- **Flask**: Framework web para Python
- **FastAPI**: Framework web moderno para Python
- **Uvicorn**: Servidor ASGI para executar FastAPI

### Instalação:

#### Método Recomendado (com ambiente virtual):

```bash
# Criar e ativar ambiente virtual
python -m venv venv

# Ativar ambiente no Windows:
venv\Scripts\activate

# Ativar ambiente no Linux/macOS/Raspberry Pi:
source venv/bin/activate

# Instalar dependências
pip install flask fastapi uvicorn

# Ou instalar as dependências que estão no arquivo requirements.txt
cd projeto_flask_app
pip install -r requirements.txt

cd projeto_fasthttp_app
pip install -r requirements.txt

# Executar no Windows
python .\projeto_flask_app\app.py
python .\projeto_fasthttp_app\app.py

# Executar no Linux/macOS/Raspberry Pi
python3 ./projeto_flask_app/app.py
python3 ./projeto_fasthttp_app/app.py
```

## Como eu verifico que os dois servidores estão funcionando?

* **Flask** : acessando no navegador `http://127.0.0.1:5000/` ou usando o `curl http://127.0.0.1:5000/`, deve aparecer:

```
Hello, World!
```

* **FastAPI** : acessando no navegador `http://127.0.0.1:8080/` ou usando o `curl http://127.0.0.1:8080/`, deve aparecer:

```
"Hello, World!"

```

## É possível rodar os dois projetos ao mesmo tempo?

Sim!

* O **Flask** foi configurado na porta **5000**.
* O **FastAPI** foi configurado na porta **8080** .

Assim, pode deixar ambos rodando em paralelo sem conflito de portas.

## Diferenças entre os dois projetos.

| Flask                                  | FastAPI                                         | Diferenças                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| -------------------------------------- | ----------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `-`                                  | `import uvicorn`                              | **Flask** já vem com servidor de desenvolvimento integrado, **FastAPI** não. Por isso a necessidade de instalar um server ASGI.                                                                                                                                                                                                                                                                                               |
| `from flask import Flask`            | `from fastapi import FastAPI`                 | Cada app importa sua própria biblioteca principal.                                                                                                                                                                                                                                                                                                                                                                                          |
| `app = Flask(__name__)`              | `app = FastAPI()`                             | Inicialização da aplicação (**Flask** precisa do nome do módulo, **FastAPI** não).                                                                                                                                                                                                                                                                                                                                         |
| `@app.get("/")`                      | `@app.get("/")`                               | Cria endpoint para requisições GET na rota raiz.                                                                                                                                                                                                                                                                                                                                                                                           |
| `def hello_world():`                 | `async def hello_world():`                    | Define a função.**FastAPI** permite funções síncronas ou assíncronas.                                                                                                                                                                                                                                                                                                                                                            |
| `return "Hello, World!"`             | `return "Hello, World!"`                      | Retorno da função.**FastAPI** automaticamente serializa para JSON quando apropriado.                                                                                                                                                                                                                                                                                                                                                 |
| `if __name__ == "__main__":`         | `if __name__ == "__main__":`                  | Evita execução quando o arquivo é importado como módulo.                                                                                                                                                                                                                                                                                                                                                                                 |
| `app.run(host="0.0.0.0", port=5000)` | `uvicorn.run(app, host="0.0.0.0", port=8000)` | **Flask**<br />Inicia o servidor de desenvolvimento Flask<br /> `host="0.0.0.0"`: Aceita conexões de qualquer endereço IP<br />`port=5000`**:** Define que o servidor rodará na porta 5000<br />**FastAPI** <br />`app=app`**:** Passa a instância FastAPI para o uvicorn<br />`host="0.0.0.0"`**:** Aceita conexões de qualquer IP<br />`port=8080`**:** Servidor rodará na porta 8080 |

**FastAPI** gera documentação automática em `/docs`, enquanto **Flask** não.

**FastAPI** é agnóstico ao servidor ASGI, por conta disso há a necessidade de instalar o servidor ASGI. Utilizei o **uvicorn** que é o mais comum.

Apesar da sintaxe similar, os frameworks têm arquiteturas bem diferentes por baixo dos panos.
