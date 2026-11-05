# MP Conciliador

### Tecnologia e finanças conectadas à operação de e-commerce

Sistema web desenvolvido por **João Pedro Krass Ramalho**, no contexto da **Control Up**, para apoiar a conciliação financeira de vendas em marketplaces. Integra informações do **Mercado Pago**, **Mercado Livre** e **Tiny ERP**, reunindo pagamentos, taxas, frete, recebíveis e documentos fiscais.

> Este repositório apresenta o projeto como portfólio. O código-fonte, as credenciais, as configurações internas e os dados reais das empresas não são distribuídos.

## O problema de negócio

O valor de uma venda passa por diferentes sistemas até chegar ao financeiro: o pedido está no marketplace, o pagamento e suas taxas no intermediador financeiro, e a nota fiscal no ERP. Conferir essas informações separadamente dificulta compreender o valor líquido, acompanhar liberações e identificar divergências.

O MP Conciliador reúne essas fontes para facilitar a análise de cada operação e o acompanhamento financeiro por período e empresa.

## Minha contribuição

Desenvolvimento do sistema de conciliação, conectando minha experiência nas áreas contábil, fiscal e financeira à construção de software. O projeto envolve integração de APIs, organização de dados financeiros, implementação de telas e relatórios e tratamento de particularidades de pagamentos, frete e documentos fiscais.

## Como a solução funciona

1. **Importa pagamentos do Mercado Pago:** valores brutos e líquidos, taxas, status e datas de liberação.
2. **Complementa com dados do Mercado Livre:** relaciona pedidos, envios, custos de frete e bônus.
3. **Busca documentos fiscais no Tiny:** procura a nota fiscal pelo pedido do marketplace e utiliza uma busca alternativa pelo pedido no ERP quando necessário.
4. **Consolida as informações:** apresenta os dados em telas de conciliação, demonstrativos e relatórios para análise.

## Funcionalidades

| Recurso | Aplicação no negócio |
| --- | --- |
| Conciliação por período | Consulta e detalhamento de pagamentos, taxas, frete e status. |
| Integração com notas fiscais | Associação entre recebimento, pedido e documento fiscal. |
| Acompanhamento de recebíveis | Visualização de valores por data de liberação. |
| Análise de taxas | Demonstrativo dos valores e taxas das operações no período. |
| Consolidação diária | Agrupamento de valores para acompanhamento financeiro diário. |
| Comparação bruto e líquido | Visão dos valores de pagamentos aprovados no período; não equivale ao saldo bancário completo da conta. |
| Relatórios e PDFs | Exportação de informações e gráficos para análise. |
| Gestão multiempresa | Alternância entre empresas vinculadas ao usuário e suas integrações. |
| Perfis de acesso | Permissões para administradores, usuários e visualizadores. |
| Verificação de login em duas etapas | Código enviado por e-mail após a validação de senha. |
| Notificações internas | Comunicação e acompanhamento de avisos no sistema. |

## Integrações e tecnologias

| Área | Tecnologias e serviços |
| --- | --- |
| Aplicação web | PHP 8, HTML e JavaScript |
| Banco de dados | MySQL, PDO e consultas parametrizadas |
| Gráficos | Chart.js |
| Pagamentos | API do Mercado Pago |
| Pedidos e logística | API do Mercado Livre |
| Documentos fiscais | API do Tiny ERP |
| E-mail | SendGrid e PHPMailer |
| Exportação em PDF | Dompdf |
| Comunicação com APIs | cURL e processamento paralelo com cURL multi |

## Desafios técnicos trabalhados

- **Relacionar fontes distintas:** conectar dados de pagamentos, pedidos, envios e notas fiscais.
- **Tratar custos de frete:** associar movimentações de frete à venda correspondente, evitando apresentá-las como uma nova venda.
- **Atualizar registros existentes:** sincronizar alterações de status e valores sem duplicar os pagamentos já importados.
- **Processar volumes de dados:** utilizar paginação e chamadas paralelas, com limite de execução e possibilidade de novas rodadas.
- **Lidar com diferenças na busca fiscal:** utilizar estratégias alternativas para localizar a nota vinculada ao pedido.
- **Separar datas de venda e liberação:** apoiar análises tanto da operação comercial quanto dos recebíveis.

## Relação com minha trajetória

Este projeto representa meu objetivo de **unir tecnologia e finanças**. A experiência com rotinas fiscais, conciliações e relatórios ajudou a identificar quais informações precisam ser reunidas para tornar a conferência das vendas mais clara e apoiar decisões de negócio.

## Escopo e evolução

A versão documentada contempla Mercado Pago, Mercado Livre e Tiny ERP. As integrações com **Amazon e Shopee são planejadas**, e não são apresentadas como funcionalidades concluídas.

A sincronização depende da disponibilidade e dos limites das APIs externas. Períodos extensos podem exigir mais de uma execução. Filas de processamento, sincronização agendada e migrações de banco versionadas são possibilidades de evolução.

Os demonstrativos são voltados às operações importadas e não substituem uma DRE contábil completa. A redução de trabalho manual e a melhoria da conferência são objetivos do projeto; este portfólio não apresenta métricas de impacto mensuradas.

## Autoria

**João Pedro Krass Ramalho**  
Estudante de Ciências Contábeis na UFJF e de Análise e Desenvolvimento de Sistemas na Estácio.

**Foco:** sistemas, integração de dados e tecnologia aplicada a finanças e negócios.
