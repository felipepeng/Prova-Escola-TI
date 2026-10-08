O Contrato(Rotas, campos, status de resposta) estão especificados em spec.md

## Testes do UC1 — Abrir bilhete

T1 - POST /bilhetes — body {"placa": "ABC1D2365"} - deve falhar e retornar erro 400 (pois não segue a regra de 7 caracteres alfanuméricos, maiúsculos)

T2 - POST /bilhetes — body {"placa": "ABC1F54"} - deve ser aceito e retornar status 201 + {"id": 1, "placa": "ABC1D23", "entrada": "<ISO-8601 com fuso -03:00>", "status": "aberto"}

## Testes do UC2 — Encerrar bilhete

T3 - POST /bilhetes/{id}/encerramento - body com data de saída anterior a data de entrada - deve retornar erro 400 (viola a regra de RN6 em spec.md)


## Testes do UC3 - Listar ativos

T4 - GET /bilhetes/ativos - caso não exista nenhum bilhete ativo - retornar erro 404 not found.

## Testes do UC4 - Relatório diário

T5 - GET /relatorios/diario?data=AAAA-MM-DD - caso seja inserida uma data inválida - deve retornar erro 400



