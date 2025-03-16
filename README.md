# Guia de Configuração do Azure Cognitive Search

Este repositório contém um passo a passo detalhado sobre como configurar o **Azure Cognitive Search**, incluindo a criação de um índice e a indexação de dados. O Azure Cognitive Search é uma poderosa ferramenta de busca que permite integrar a funcionalidade de pesquisa avançada em aplicativos e sistemas, proporcionando uma experiência de usuário melhorada.

## Índice

1. [Introdução](#introdução)
2. [Pré-requisitos](#pré-requisitos)
3. [Passo 1: Criar o Serviço de Azure Cognitive Search](#passo-1-criar-o-serviço-de-azure-cognitive-search)
4. [Passo 2: Criar um Índice no Azure Cognitive Search](#passo-2-criar-um-índice-no-azure-cognitive-search)
5. [Passo 3: Indexar Dados no Azure Cognitive Search](#passo-3-indexar-dados-no-azure-cognitive-search)
6. [Possíveis Ferramentas que se Beneficiam](#possíveis-ferramentas-que-se-beneficiam)
7. [Insights e Aprendizados](#insights-e-aprendizados)
8. [Conclusão](#conclusão)

## Introdução

O **Azure Cognitive Search** é uma plataforma de pesquisa como serviço (SaaS) oferecida pela Microsoft Azure. Ele facilita a implementação de recursos de busca em aplicativos e websites com recursos avançados, como pesquisa de texto completo, sugestão de autocompletar, filtragem e ordenação.

## Pré-requisitos

- Conta do Azure com permissão para criar recursos.
- Navegador web e acesso ao portal do Azure ([portal.azure.com](https://portal.azure.com)).
- Dados (em formato JSON, CSV, etc.) para indexar e consultar.

## Passo 1: Criar o Serviço de Azure Cognitive Search

1. Acesse o [portal do Azure](https://portal.azure.com).
2. No painel de navegação à esquerda, procure por **Azure Cognitive Search** na barra de pesquisa.
3. Selecione **Azure Cognitive Search** e clique em **Criar** para iniciar a criação do serviço.
4. Preencha os campos necessários, como:
   - **Nome do serviço**: Escolha um nome único.
   - **Grupo de recursos**: Selecione ou crie um grupo de recursos.
   - **Região**: Selecione a região mais próxima de seus usuários.
   - **Plano de preço**: Escolha o plano que melhor atende às suas necessidades.
5. Após a criação do serviço, você poderá acessar o painel do **Azure Cognitive Search**.

## Passo 2: Criar um Índice no Azure Cognitive Search

Agora que o serviço está configurado, o próximo passo é criar um **índice**.

1. No painel do serviço de **Azure Cognitive Search**, clique em **Índices**.
2. Clique em **Adicionar índice** e preencha as informações, como:
   - **Nome do índice**: Escolha um nome (ex.: `produtos`).
   - **Campos**: Defina os campos para seu índice, como `id`, `nome`, `descricao`, `preco`.
   - Para o campo `id`, defina como **Chave (Key)**, o que significa que ele será único e identificador.
   - Adicione as propriedades de cada campo, como **pesquisável**, **ordenável**, **filtrável**, etc.

Exemplo de estrutura de índice:

```json
{
  "name": "produtos",
  "fields": [
    { "name": "id", "type": "Edm.String", "key": true },
    { "name": "nome", "type": "Edm.String", "searchable": true },
    { "name": "descricao", "type": "Edm.String", "searchable": true },
    { "name": "preco", "type": "Edm.Double", "sortable": true, "filterable": true }
  ]
}
