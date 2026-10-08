Contrato(Rotas, campos, status de resposta) estão especificados em spec.md


## Stack

1 - Deve ser utilizada a linguagem python 3.11 (python:3.11-slim), junto de uvicorn e Pydantic v2. Sempre use a sintaxe do Pydantic v2, NUNCA da v1.

2 - Os dados devem ser salvo em memória (dicts). Sem consistência de memória.

3 - Use Pytest + httpx para os testes. 

Stack inicial:
Python 3.11, Pydantic v2, uvicorn, Pytest, hhtpx, dicts.
Dockerfile (Com EXPOSE na rota 8000 e CMD)


## Dependências (requirements.txt)



## Estrutura dos Arquivos


## Decisões Tecnicas 