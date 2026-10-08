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

## Testes do UC5 — Cancelar bilhete

T6 - POST /bilhetes/{id}/cancelamento - bilhete com status "aberto" - deve retornar 200 com "status": "cancelado", sem os campos saida e valor_centavos

## Testes do UC6 — Histórico por placa

T7 - GET /bilhetes?placa=ABC1D23 - placa com 1 bilhete encerrado e, depois, 1 bilhete aberto - deve retornar 200 com array de 2 bilhetes, o aberto (mais recente) primeiro

## Testes do UC7 — Tolerância gratuita

T8 - POST /bilhetes/{id}/encerramento - bilhete com duração de TOLERANCIA_MINUTOS + 1 minuto - deve retornar 200 com valor_centavos cobrado sobre todos os minutos (⌈(TOLERANCIA_MINUTOS + 1) ÷ FRACAO_MINUTOS⌉ frações), sem descontar a tolerância

## Testes do UC8 — Uma vaga por placa

T9 - POST /bilhetes - body {"placa": "ABC1D23"} com a placa já tendo um bilhete aberto - deve retornar 409 {"erro": "bilhete_em_aberto"}



