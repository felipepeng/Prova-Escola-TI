Arquivo que contempla as Regras Gerais que devem ser seguidas no Projeto.

# Regras

R0 - Em caso de divergência de informações siga esta hierarquia para decidir qual seguir: spec.md>constitution.md>plan.md>test.md>task.md

R1 - O back-office não existe - somente a API. Não deve ser implementado nada relacionado ao back-office, somente a api específicada (spec.md)

R2 - Deve ser criado uma variável que irá padronizar o endereço da rota. A variável será chamada 'PORTA_SERVICO', ela será a porta que o serviço gerado deve escutar. Sempre que for necessário usar o endereço da rota deve ser utilizada esta variável.

R3

## Qualidade

R4 - Deve ser gerado um arquivo Dockerfile na raiz do projeto (com EXPOSE na rota 8000 e CMD), requirements.txt (Arquivo de dependencias expecificado em plan.md, não utilizar mais nenhum tipo de arquivo para armazenar as dependências).


