O Contrato(Rotas, campos, status de resposta) estão especificados em spec.md


## Stack

1 - Deve ser utilizada a linguagem python 3.11 (python:3.11-slim), utilizando FastAPI, junto de uvicorn e Pydantic v2. Sempre use a sintaxe do Pydantic v2, NUNCA da v1.

2 - Os dados devem ser salvo em memória (dicts). Sem consistência de memória.

3 - Use Pytest + httpx para os testes. 

## Dependências (requirements.txt)
para o arquivo requirements.txt salve explicitamente estas dependências: 
- fastapi
- uvicorn
- pydantic>=2,<3
- pytest
- httpx

## Estrutura dos Arquivos
.
├── Dockerfile
├── requirements.txt
├── app/
│   ├── __init__.py
│   ├── main.py       # app FastAPI, rotas UC1–UC8, storage em dicts e mapeamento de erros
│   ├── schemas.py    # modelos Pydantic v2 de request/response
│   └── pricing.py    # constantes da variante + cálculo puro (minutos → centavos)
└── tests/
    ├── test_pricing.py   # bordas: fração exata, +1 min, teto, tolerância
    └── test_api.py       # contrato HTTP, status, bodies de erro, UC8, relatório



--- apagar
Stack inicial:
Python 3.11, Pydantic v2, uvicorn, Pytest, hhtpx, dicts.
Dockerfile (Com EXPOSE na rota 8000 e CMD)