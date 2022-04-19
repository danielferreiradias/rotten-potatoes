# 1 - Baixa a imagem do python, a aplicação é baseada em python;
# 2 - Define o WORKDIR
# 3 - Copiar o arquivo que gerencia os pacotes da aplicação o "requirements.txt"
# 4 - Baixar e instalar os pacotes com o RUN
# 5 - Copia os arquivos da aplicação para meu WORKIDR
# 6 - Expor a porta da aplicação
# 7 - Comando de inicialização com o "gunicorn" um servidor web light em python, definindo "workers", "bind" acessível de qualquer IP, o arquivo de configuração

FROM python:3.8-slim-buster
WORKDIR /app
COPY requirements.txt .
RUN python -m pip install -r requirements.txt
COPY . /app
EXPOSE 5000
CMD [ "gunicorn", "--workers=3", "--bind", "0.0.0.0:5000", "-c", "config.py", "app:app" ]