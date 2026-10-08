# Plano Técnico — Zona Azul Digital (API REST)

Decisões técnicas e suas justificativas: stack, estrutura, persistência e relógio.
Implementa o que está em spec.md, respeitando constitution.md.

O contrato (rotas, campos, status de resposta) está especificado em spec.md.


## Stack

1 - Deve ser utilizada a linguagem Python 3.11 (python:3.11-slim), utilizando FastAPI, junto de Uvicorn e Pydantic v2. Sempre use a sintaxe do Pydantic v2, NUNCA da v1.

2 - Os dados devem ser salvos em memória (dicts). Sem consistência de memória.

3 - Use Pytest + httpx para os testes. 

## Dependências (requirements.txt)
Para o arquivo requirements.txt, salve explicitamente estas dependências: 
- fastapi
- uvicorn
- pydantic>=2,<3
- pytest
- httpx

## Estrutura dos Arquivos
```text
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
```