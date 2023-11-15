# Projeto Final: Análise Concorrente e Eficiente de Grandes Volumes de Dados em

# Sistemas Operacionais

**Prof. Me. Michel Junio Ferreira Rosa**

**Sistemas Operacionais**

## **Objetivo do Projeto**

Desenvolver um script capaz de ler e processar um arquivo CSV com de linhas, utilizando técnicas de multiprogramação,
sincronização de processos e particionamento de dados para realizar cálculos diversos sobre os dados de forma performática.
Os dados sáo históricos extensos de transações eletrônicas (e-commerce, serviços de streaming, apps de transporte, etc.) de diversas empresas ao redor do mundo.

## **Estrutura do Projeto**

## 1. **Implementação**

- **Divisão e Conquista:** Implementar um mecanismo que divida o arquivo em partes menores para processamento paralelo.

- **Sincronização de Processos:** Utilizar semáforos ou outros mecanismos de sincronização para gerenciar o acesso concorrente aos recursos compartilhados.

- **Estrutura de Cada Registro:** \
**a**.  ```transaction_id``` : Identificador único da transação (UUID). \
**b**.  ```user_id``` : Identificador único do usuário. \
**c**.  ```company_id``` : Identificador da empresa onde a transação foi realizada. \
**d**.  ```transaction_date``` : Data e hora da transação (timestamp). \
**e**.  ```product_id``` : Identificador do produto/serviço. \
**f**.  ```product_description``` : Descrição breve do produto/serviço. \
**g**.  ```quantity``` : Quantidade do produto/serviço adquirido. \
**h**.  ```price_per_unit``` : Preço unitário do produto/serviço na moeda original. \
**i**.  ```total_price``` : Preço total da transação (quantity * price_per_unit),  *necessário calcular*. \
**j**.  ```currency``` : Moeda em que a transação foi realizada (USD, EUR, BRL, etc.). \
**k**.  ```payment_method``` : Método de pagamento (cartão de crédito, PayPal, transferência bancária, etc.). \
**l**.  ```country``` : País onde a transação foi realizada. \
**m**.  ```city``` : Cidade onde a transação foi realizada.

- **Cálculos a Serem Realizados:** \
**a**. Total de transações por país. \
**b**. Média de preço por produto. \
**c**. Total de vendas por empresa. \
**d**. Quantidade de transações por método de pagamento. \
**e**. Distribuição de vendas por mês/ano. \
**f**. Transações mais comuns por cidade. \
**g**. Média de gastos por usuário. \
**h**. Total de vendas em cada moeda.

- **DataSet**: \
Acesse o arquivo de entrada no link: [DATASET](https://uniceuma-my.sharepoint.com/personal/michel_rosa_unieuro_edu_br/_layouts/15/onedrive.aspx?id=%2Fpersonal%2Fmichel%5Frosa%5Funieuro%5Fedu%5Fbr%2FDocuments%2Fdataset&ga=1)

## 2. **Relatório**

- **Saída de Cada Função**: Documentar a saída gerada por cada cálculo.
- **Contribuição dos Membros**: Detalhar a contribuição específica de cada membro do grupo no projeto.
- **Manual de Utilização**: Incluir instruções detalhadas sobre como executar o script, incluindo instalação de bibliotecas e comandos necessários.
- **Análise de Desempenho**: Avaliar o desempenho do sistema em termos de eficiência na utilização de memória e tempo de
processamento.

## 3. **Requisitos Técnicos Mínimos do Projeto**

# - **i. *Multiprogramação e Concorrência**

- Implementar a leitura e processamento do arquivo CSV usando múltiplas threads ou processos.
- Cada thread/processo deve ser responsável por ler e processar uma parte do arquivo, demonstrando claramente a divisão do
trabalho.

# **ii. Comunicação Entre Processos**

- Utilizar mecanismos de sincronização como semáforos ou mutexes para gerenciar o acesso concorrente a recursos
compartilhados.
- Estabelecer um protocolo de comunicação entre as threads/processos para a agregação dos resultados de cada partição do
arquivo.

# **iii. Estratégias de Particionamento de Dados**

- Dividir o arquivo CSV em partes menores que podem ser processadas independentemente.
- Cada thread/processo deve trabalhar em uma parte diferente do arquivo para maximizar a eficiência e minimizar a competição
por recursos.

# **iv. Uso Eficiente de Memória**

- Implementar estratégias para minimizar o uso de memória, como processamento em lotes ou estruturas de dados otimizadas.

# **v. Tempo Médio de Uso de CPU**

- Medir e registrar o tempo médio de uso de CPU para o processamento de cada parte do arquivo.
- Incluir essas métricas na saída final para avaliar a eficiência do uso de recursos.
- **Sugestão de Implementação**: Utilizar funções de cronometragem no código para medir o tempo de CPU. Por exemplo, em Python, pode-se usar time.process_time() para capturar o tempo de CPU.

# **vi. Saída Padrão**

Exibir os resultados de todos os cálculos na saída padrão (console) em um formato claro e legível. A saída deve incluir:

- Total de transações por país.
- Média de preço por produto.
- Total de vendas por empresa.
- Quantidade de transações por método de pagamento.
- Distribuição de vendas por mês/ano.
- Transações mais comuns por cidade.
- Média de gastos por usuário.
- Total de vendas em cada moeda.

# **vii. Documentação e Comentários no Código**

- Incluir comentários detalhados e documentação no código explicando a lógica e as escolhas de design.
- Incluir um arquivo README com instruções sobre como compilar e executar o programa.
- **Relatório de Desempenho**: Incluir no relatório o detalhamento sobre o desempenho, destacando o uso de CPU para cada parte do arquivo.
- Documentar como o tempo de CPU é medido e interpretado.
Incluir a configuração da máquina utilizada para o processamento [CPU; RAM; DISCO].
- Incluir o print da aba CPU e Memory do CPU-Z.

# **viii.  Ambiente de Desenvolvimento**

- Especificar a linguagem de programação e as ferramentas necessárias para compilar e executar o projeto.
- Listar todas as bibliotecas e dependências necessárias.
- Para garantir que o projeto final na disciplina de sistemas operacionais cumpra todas as especificações necessárias, é
importante detalhar ainda mais os requisitos técnicos, incluindo um formato padrão de saída para os cálculos e uma métrica de desempenho, como o tempo médio de uso de CPU. Vamos detalhar isso:

## 4. **Formatação da Saída**

- Incluir o resultado da saída padrão no Relatório. 
- A saída padrão deve ser formatada da seguinte maneira para cada cálculo:

```
Tempo Total de Processamento do Arquivo: 3.5 horas

Tempo Médio de Uso de CPU para Cada Parte do Arquivo:
Parte 1: 2.5 segundos
Parte 2: 3.1 segundos
...

Total de Transações por País:
País 1: [Número de transações]
País 2: [Número de transações]
...
Média de Preço por Produto:
Produto 1: [Média de preço]
Produto 2: [Média de preço]
...
[Continuar para cada cálculo]
```

# **Avaliação**

- **Funcionalidade**: Verificar se o aplicativo realiza todos os cálculos corretamente.
- **Eficiência**: Avaliar a eficiência do uso de recursos do sistema.
- **Qualidade do Código**: Analisar a clareza, organização e documentação do código.
- **Qualidade do Relatório**: Avaliar a completude e clareza do relatório.

# **Entrega Final**

- Entrega 03/12/2023 até 23:59.
- Código-fonte do projeto.
- Relatório detalhado conforme especificado.
- Um arquivo README com instruções de instalação e execução.
- A entrega deve ser realizada apenas por um membro do grupo em arquivo .zip.
