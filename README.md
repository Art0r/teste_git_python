# Setup inicial da resolução

    SO utilizado: Pop!_OS 22.04 LTS x86_64
    Versão do python utilizada: Python 3.10.12
    IDE utilizada: VS Code

```sh
python3 -m venv venv
. venv/bin/activate
pip install Flask pandas 
pip freeze > requirements.txt
touch README.md
flask --app app run --debug --host 127.0.0.1 --port 5000
```

## Resposta item 1.4.1

A aplicação não estava rodando pois para que um app Flask possa rodar, é necessário que o o pacote **Flask** esteja instalado no ambiente python  global ou local com o **venv**. No caso dessa aplicação também é uma dependência que a biblioteca **pandas** esteja instalada. Uma vez instalados a aplicação pode ser rodada utilizando *flask --app app run --debug --host 127.0.0.1 --port 5000* na linha de comando (no caso de utilizar venv, antes o ambiente deve estar habilitado).<br>
Uma outra forma de rodar a aplicação seria adicionando o seguinte código ao final do arquivo **app.py**
```py
if __name__ == "__main__":
    app.run(debug=true, host="127.0.0.1", port="5000")
```
Então executar o seguinte comando na raíz do diretório (com o venv ativado)
```sh
python app.py
```
Outro modo de rodar a aplicação é definindo as variáveis de ambiente que serão lidas pelo código, ao inves de defini-las "manualmente"
```sh
export FLASK_ENV=development
export FLASK_DEBUG=True
export FLASK_APP=app
```
E então rodar
```sh
flask run
```
## Resposta item 1.4.2

```sh
touch templates/table.html
touch static/styles.css 
```