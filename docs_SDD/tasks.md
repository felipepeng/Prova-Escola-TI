# Tarefas — Zona Azul Digital (API REST)

Ordem de execução do projeto. Siga as tasks em sequência.
Cada task só termina quando os testes indicados de tests.md passam.

Regra para toda task: escreva os testes indicados de tests.md, rode e confirme que falham,
implemente o mínimo para passarem e rode `python -m pytest` inteiro antes de avançar.

## Tasks

1 - Estrutura: crie os arquivos, o requirements.txt e o Dockerfile conforme plan.md.
    Pronto quando: `python -m pytest` executa sem erro de importação.

2 - Cálculo de valor: função pura minutos → valor_centavos (tolerância → frações → teto), sem float.
    Pronto quando: T__ a T__ passam.

3 - POST /bilhetes (UC1, UC8): validação de placa e entrada, conflito de placa aberta, erros no formato {"erro": ...}.
    Pronto quando: T__ a T__ passam.

4 - POST /bilhetes/{id}/encerramento (UC2, UC7): usa a função da task 2; trata 404 e 409.
    Pronto quando: T__ a T__ passam.

5 - POST /bilhetes/{id}/cancelamento (UC5): só bilhetes abertos; sem saida nem valor.
    Pronto quando: T__ a T__ passam.

6 - GET /bilhetes/ativos (UC3): só abertos, mais recentes primeiro; vazio → 200 [].
    Pronto quando: T__ a T__ passam.

7 - GET /bilhetes?placa= (UC6): todos os status, mais recentes primeiro; placa sem histórico → [].
    Pronto quando: T__ a T__ passam.

8 - GET /relatorios/diario (UC4): média com 0,5 para cima por aritmética inteira; data inválida → 422.
    Pronto quando: T__ a T__ passam.

9 - Docker: build da imagem e container na PORTA_SERVICO; POST /bilhetes retorna 201.
    Se o Docker não estiver disponível, valide com uvicorn na mesma porta.