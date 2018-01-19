# VueJS com o Django Framework

## Como desenvolver ?

1. Clone o repositório.
2. Crie um virtualenv com Python 3.6
3. Ative o virtualenv
4. Instale as dependências do django
5. Instale as dependências do vuejs
6. Gerar arquivo bundle.js via npm  
7. Execute o Django

```console
git clone git@github.com:Ricardolv/django-vuejs.git django-vuejs
cd django-vuejs
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
npm install
comando: webpack ou npm start
python manage.py runserver
```
