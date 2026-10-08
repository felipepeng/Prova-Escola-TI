Arquivo que contempla as Regras Gerais que devem ser seguidas no Projeto.

# Regras

R0 - Em caso de divergência de informações siga esta hierarquia para decidir qual seguir: spec.md>constitution.md>plan.md>test.md>task.md

R1 - O back-office não existe - somente a API. Não deve ser implementado nada relacionado ao back-office, somente a api específicada (spec.md)

R2 - Deve ser criado uma variável que irá padronizar o endereço da rota. A variável será chamada 'PORTA_SERVICO', ela será a porta que o serviço gerado deve escutar. Sempre que for necessário usar o endereço da rota deve ser utilizada esta variável.

R3 - Erros de validação devem gerar status 400 em vez de 422 por padrão.

R4 - Os dados Json devem ser feitos utilizando camelCase

R5 - as datas devem seguir o modelo AAAA-MM-DD

## Qualidade

R6 - Deve ser gerado um arquivo Dockerfile na raiz do projeto (com EXPOSE na rota 8000 e CMD), requirements.txt (Arquivo de dependencias expecificado em plan.md, não utilizar mais nenhum tipo de arquivo para armazenar as dependências), arquivo README (Expecificando como rodar o docker, comandos para os testes e visão geral do projeto)

R7 - Seguir o Padrão PEP8 para todo o código. Mas no JSON use camelCase.


