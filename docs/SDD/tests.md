O Contrato(Rotas, campos, status de resposta) estão especificados em spec.md

## Testes do UC1 — Abrir bilhete

T1 - POST /bilhetes — body {"placa": "ABC1D2365"} - deve falhar e retornar erro 400 (pois não segue a regra de 7 caracteres alfanuméricos, maiúsculos)

T2 - POST /bilhetes — body {"placa": "ABC1F54"} - deve ser aceito e retornar status 201 + {"id": 1, "placa": "ABC1D23", "entrada": "<ISO-8601 com fuso -03:00>", "status": "aberto"}

## Testes do UC2 — Encerrar bilhete

T3 - POST /bilhetes/{id}/encerramento - body {"id": 1, "placa": "ABC1D23", "entrada": "...", "saida": "...",
    "minutos": 95, "valor_centavos": 1250} 

