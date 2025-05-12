# DIO-AZURE
***
No curso em parceria da DIO com a Microsoft tive a oportunidade de entender como funcionam os recursos em Data Factory partindo da criação de recursos.

**Mas, o que são recursos?**
Recursos são **blocos de construção** que formam a infraesterutura, as aplicações e os serviços que são utilizados dentro da Azure. 
A Azure disponibiliza os seguintes recursos para serem utilizados divididos em nichos:

- **Computação:** Máquinas virtuais (VM's), Azure App Services, Azure Functions, Azures Kubernets Services, Azure Virtual Machine Scale Sets, Azure Service Fabric, Azure Batch, Azure Spring Apps;
- **Armazenamento:** Azure Blob Storage, Azure Dick Storage, Azure File Storage, Azure Data Lake Storage, Azure Queue Storage, Azure Table Storage;
- **Banco de Dados:** Azure SQL Database, Azure Cosmos DB, Azure Database for MySQL, Azure Database for PostgreeSQL, Azure SQL Managed Instance, Azure Reds Cache, Azure Synapses Analytics, Azure MariaDB;
- **Rede:** Virtual Networking, Azure Load Balance, Azure Application Gateway, Azure VPN Gateway, Azure ExpressRoute, Azure Firewall, Azure DNS, Azure Traffic Manager;
- **Inteligência Artificial e Machine Leaning:** Azure Machine Learning, Cognitive Services, Azure Bot Services, Azure Databrick, Azure OpenAI;
- **Análise de Dados:** Azure Synapses Analytics, Azure Data Factory, Azure Stream Analytics, Azure HDInsight, PowerBI Embedded, Azure Data Explorer;
- **Segurança:** Azure Active Directory, Azure Key Vault, Azure Security Center, Azure Sentinel, Azure DDos Protection;
- **Gerenciamento e Governança:** Azure Monitor, Azure Log Analytics, Azure Automation, Azure Policy, Azure Cost Management and Billing, Azure Resource Manager;
- **Conteiners:** Azure Kubertnets Service, Azure Container Instances, Azure Container Registry, Azure Service Fabric;
- **IoT:** Azure IoT Hub, Azure IoT Central, Azure Sphere, Azure Digital Twing;
- **DevOps e Desenvolvimento:** Azure DevOps Services, Azure DevTest Labs, Azure Pipelines;
- **Blockchain:** Azure Blockchain Service;
- **Backup e Recuperação:** Azure backup, Azure Site Recovery;
- **Migração:** Azure Migrate, Azure Database Migration Service;
- **Dev/Test e Infraestrutura como serviço:** Azure Virtual Desktop, Azure App Service Environment;
- **Outras ferramentas:** Azure Logic Apps, Azure Media Services, Azure Congnitive Search.

**Como criar um recurso**

Diversas ferramentas são projetas para dar suporte aos desenvolvedores para difernetes casos de uso. Como por exemplo: Use uma ferramenta de GUI como o portal do Azure ou a extensão Ferramentas do Azure para VS Code, 
Escreva um script usando a CLI do Azure ou o Azure PowerShell, ou ferramentas de IaC (infraestrutura como código).

*O Portal do Azure*

![image1](https://github.com/LuanaNikari/DIO-AZURE/blob/main/img1.png)
Nessa tela inicial no Portal do Azure é possível visualizar em Serviços Azure a opção de "Criar um Recurso".

![image2](https://github.com/LuanaNikari/DIO-AZURE/blob/main/img2.png)
Escolha uma das categorias para a criação do recurso.

![image3](https://github.com/LuanaNikari/DIO-AZURE/blob/main/img3.png)
Note que após a criação do Recurso, ele permanecerá visível desta maneira.

![image4](https://github.com/LuanaNikari/DIO-AZURE/blob/main/img4.png)
Vamos exemplificar criando um Recurso de Análise Data Factory. Segundo a documentação do serviço:
É um serviço ETL na nuvem do Azure para integração e transformação de dados sem servidor em expansão. Ele oferece uma interface do usuário livre de código para criação intuitiva e gerenciamento e monitoramento em painel único. Também é possível migrar pacotes SSIS existentes por lift-and-shift para o Azure e executá-los com total compatibilidade no ADF (Azure Data Factory). O Azure-SSIS Integration Runtime oferece um serviço totalmente gerenciado, de modo que não é necessário se preocupar com o gerenciamento da infraestrutura.

Nesse exemplo, os campos precisam ser preenchidos seguindos algumas normas e todos são de resposta obrigatória, as quais vamos comentar. Todo grupo de recurso deve estar dentro de uma Assinatura. Em Detalhes da instância, no campo Nome, é interessante acessar a página de Nomenclatura da Azure. Ao finalizar todas configurações exigidas, nas demais abas, clique em Criar. 

![image6](https://github.com/LuanaNikari/DIO-AZURE/blob/main/img6.png)
O recurso será enviado para a implantação.

![image7](https://github.com/LuanaNikari/DIO-AZURE/blob/main/img7.png)
Você pode visualizar o recurso em "Ir para o Recurso".


# Explorando os Fundamentos e Recursos do Azure Databricks

![image8](https://github.com/LuanaNikari/DIO-AZURE/blob/main/img8.png)
Nesta primeira atividade de código, pude verificar os conceitos e com a documentação de cada uma puder compreender seu funcionamento.

- **DBFS (Sistema de Arquivo do Databricks):**

O Azure Databricks é uma plataforma poderosa de analytics aberta, criada para ajudar você a desenvolver, implantar e compartilhar soluções de dados, inteligência artificial e analytics em grande escala, de forma simples e eficiente.

Ele funciona como um painel de controle, onde os serviços de back-end são gerenciados pelo Azure dentro da sua conta, e o plano de computação é responsável por processar os dados. Cada workspace do Azure Databricks tem uma conta de armazenamento associada a ele, que está vinculada à sua assinatura no Azure.

Além disso, a IA generativa integrada ao Azure usa o conceito de data lakehouse para entender a semântica única dos seus dados, otimizando automaticamente o desempenho e gerenciando a infraestrutura de acordo com as necessidades do seu negócio.

- **Lakehouse (Integra Data Lake e Data Warehouse):**

Um Lakehouse é um sistema de gerenciamento de dados que combina os benefícios de data lakes e data warehouses. Fornece recursos escalonáveis de armazenametno e processamento para ornagizações modernasque desejam evitar sistemas isolados para processar cargas de trabalho diferentes, como ML (machine learning) e BI (business intelligence). Oferece o padrão de arquitetura de medalhão, ou seja, uma série de camas de dados de denotam a qualidade dos dados. Os termos bronze (bruto), prata (validado), e outro (enriquecido) descrevem a qualidade dos dados em cada uma dessas camadas.


O Databricks Lakehouse usa duas tecnologias adiciinais: Delta Lake (veremos a geguir) e Unity Catalog, que trata-se de uma solução de governaça unificada e refinada para dados e IA.


- **Delta Lake (Camada de armazenamento de dados open-source):**

Delta Lake é uma camada de armazenamento otimizada que dá suporte ACID (atomicidade, consistência, isolamento e durabilidade) e imposição de schema. Tal atomicidade significa que todas as transações têm êxito ou falham completamente. As garantias de consistência estão relacionadas a como um determinado estado dos dados é observado por operações simuntâneas. Já o isolametno se refere a como as operações simultâneas podem entrar em conflito entre si. Durabilidade significa que as alterações confirmadas são permanentes.
Todas as tabelas no Azure Databricks são tabelas Delta por padrão.

- **Workspace (Ambiente colaborativo para dados e código):**
Trata-se de um ambiente lógico usado para organizar, gerenciar e agrupar recursos relacionados a um serviço específico — como o Azure Databricks, o Azure Machine Learning, ou até o Log Analytics.

- **IA (Criação e implantação de IA generativa em escala):**
A IA generativa é uma área da inteligência artificial voltada para a criação de conteúdos, como textos, imagens, códigos e até dados sintéticos. Isso é possível graças a modelos avançados, como os LLMs (modelos de linguagem de grande porte) e os modelos de base, que servem como "cérebro" por trás dessas aplicações.

Existem alguns padrões comuns usados no desenvolvimento de soluções com IA generativa:

1. Engenharia de prompt: criar comandos (prompts) estratégicos para guiar o comportamento dos modelos de linguagem.

2. RAG (Recuperação com Geração Aumentada): técnica que combina um LLM com informações externas para gerar respostas mais precisas e atualizadas.

3. Ajuste fino (fine-tuning): adaptar um modelo pré-treinado a um conjunto de dados específico de uma área ou empresa.

4. Pré-treinamento: treinar um modelo do zero, desde a base.

O Mosaic AI, por sua vez, é um conjunto de ferramentas integrado ao Azure Databricks, criado justamente para facilitar o desenvolvimento e a implantação dessas aplicações de IA generativa em escala. Ele é especialmente útil para quem quer montar soluções como o RAG, conectando modelos de linguagem com os dados da empresa para gerar respostas inteligentes, seguras e personalizadas. 

- **Armazenamento (Armazenamento otimizado com arquitetura lakehouse):**
Dentre as arquiteturas em Lakehouse temos: Arquitetura Medallion - mais tradicional, Delta Architecture, Lamba Architecture, Kappa Architecture, Data Mesh + Lakehouse, ML/AI Centric Lakehouse, Lakehouse com RAG (IA generativa), Modern BI Lakehouse, Feature Store Architecture (para IA/ML), RAG (Retrieval-Augmented Generation) Architecture, Serverless Lakehouse, Lakehouse com Data Fabric, Governed Lakehouse. Cada tipo de arquitetura possui um foco principal. Para o armazenamento otimizado um tipo de arquitetura ideal é Delta. O formato Delta, que combina o Parquet com metadados ACID, é excelente para armazenar grandes volumes de dados de forma compactada, usando compressão por colunas — o que garante eficiência no uso do espaço sem comprometer o desempenho. Um dos grandes diferenciais é o time travel, que permite acessar versões anteriores dos dados sem a necessidade de duplicá-los, economizando armazenamento. Além disso, o recurso de compaction (ou optimize) ajuda a unir arquivos pequenos em arquivos maiores, reduzindo a fragmentação e melhorando a performance das consultas. Com o Z-Ordering, os dados são reorganizados fisicamente no disco para acelerar ainda mais as buscas. E tudo isso com suporte a operações como merge, update e delete, que funcionam de forma rápida e confiável graças ao controle transacional.

- **ETL (Processamento de dados em lote e em tempo real):**
No Azure, o processo de ETL (Extract, Transform, Load) pode ser realizado de forma eficiente tanto em lote quanto em tempo real, dependendo das necessidades do seu projeto. Para cenários de processamento em lote, ferramentas como o Azure Data Factory e o Azure Synapse Pipelines são amplamente utilizadas. Eles permitem extrair grandes volumes de dados de várias fontes, transformar com regras de negócio e carregar em destinos como o Data Lake ou SQL Database, tudo isso de forma escalável e automatizada.

Já para o processamento em tempo real, o Azure oferece soluções como o Azure Stream Analytics e o Azure Event Hubs, que são ideais para lidar com dados que chegam continuamente, como logs de aplicações, dados de sensores IoT ou cliques em um site. Esses serviços conseguem capturar, processar e transformar esses dados em segundos, permitindo decisões rápidas baseadas em informações atualizadas em tempo real.

Com esses recursos, o Azure torna possível construir pipelines de dados modernos que combinam confiabilidade, flexibilidade e escalabilidade, seja para análises históricas com dados em lote ou para reações imediatas com dados em tempo real.

- **Governança (Controle e segurança unificada de dados e IA):**

a governança de dados e IA é um conjunto de práticas e ferramentas que ajudam as organizações a manter controle, segurança e conformidade sobre todos os seus ativos de dados e soluções de inteligência artificial. Isso significa garantir que os dados estejam protegidos, bem organizados, acessíveis apenas por quem deve acessá-los, e usados de forma responsável.

A plataforma oferece recursos como o Microsoft Purview, que permite catalogar, classificar e monitorar os dados espalhados por diferentes serviços — tudo em um só lugar. Com isso, é possível aplicar políticas de acesso, acompanhar o uso dos dados e garantir que estejam em conformidade com normas como LGPD ou GDPR.

Para soluções de IA, o Azure também permite aplicar princípios de IA responsável, com ferramentas que ajudam a auditar modelos, explicar decisões automatizadas e garantir que os sistemas estejam livres de vieses. Toda essa governança acontece de forma unificada, integrando dados estruturados e não estruturados, pipelines de machine learning e modelos de linguagem avançados.

Ou seja, governança no Azure vai muito além de segurança: ela traz confiança, rastreabilidade e transparência para tudo o que envolve dados e inteligência artificial dentro da nuvem.

- **Compartilhamento de dados (Compartilhamento rápido de dados, modelos e notebooks):**

1. Compartilhamento de Dados
O Azure Data Share permite o compartilhamento eficiente de dados, seja entre diferentes departamentos ou com outras organizações. A ferramenta possibilita o compartilhamento controlado de dados sem a necessidade de movimentação física, garantindo a segurança e a conformidade com as políticas da empresa. Dessa forma, as partes envolvidas têm acesso aos dados necessários de maneira prática e segura.

2. Compartilhamento de Modelos
O Azure Machine Learning oferece recursos para o compartilhamento de modelos de inteligência artificial, permitindo que equipes colaborem no treinamento, ajuste e reutilização de modelos. O controle de versões é mantido, garantindo a melhoria contínua e a organização dos processos de desenvolvimento de IA.

3. Compartilhamento de Notebooks
No Azure Databricks, os notebooks são amplamente utilizados por equipes de dados para trabalhar de forma colaborativa em análises e transformações. Esses notebooks podem ser compartilhados facilmente com permissões personalizadas, garantindo que apenas os usuários autorizados possam editar, visualizar ou executar os códigos.

Com o Azure, o compartilhamento de dados, modelos e notebooks é realizado de maneira eficiente e segura, acelerando o trabalho colaborativo e a evolução de soluções de dados e inteligência artificial.

## Referências de Estudo

Nomenclatura do Azure
Link: https://learn.microsoft.com/pt-br/azure/cloud-adoption-framework/ready/azure-best-practices/resource-naming

Documentação do Azure Data Factories
Link: https://learn.microsoft.com/pt-br/azure/data-factory/?WT.mc_id=APC-Datafactories

Visão Geral da Arquitetura do Databricks
Link: https://learn.microsoft.com/pt-br/azure/databricks/getting-started/overview

