# trello_api
Asynchronous Trello API Client based on AIOHTTP Client 

Python 3.6+

## Install

```bash
pip install git+https://github.com/polozhevets/atrello
```

## Auth

#### TRELLO_APP_KEY: https://trello.com/app-key/
#### TRELLO_APP_TOKEN:

First you need gen auth url:
```python
from atrello import TrelloApi

trello_app = TrelloApi(TRELLO_APP_KEY)
token_url = trello_app.get_token_url('MyAppBot', expires='never', write_access=True)
```
Than you need copy value of token_url and auth your trello account in webbrowser
After that you will get token

#### Apply token in your app:
```python
trello_app.set_token(TRELLO_APP_TOKEN)
```

#### Sample usage

Get board info:
```python
board = await trello_app.boards.get("5c49c07e48557d4e29414936")
```

Synchronous version for python2/3: https://github.com/polozhevets/trello_api
