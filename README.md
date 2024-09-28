[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/g15WYZGA)
[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=16226623&assignment_repo_type=AssignmentRepo)
# Automação de Testes de API com Postmam e Newman

Este projeto foi criado para auxiliar na execução de testes automatizados utilizando Postman e Newman. Ele permite organizar coleções de testes por tipo e ambiente, além de gerar relatórios detalhados em HTML para cada execução.

## Requisitos

Antes de começar, certifique-se de ter os seguintes itens instalados:

- [Node.js](https://nodejs.org/) (versão LTS recomendada)
- [Newman](https://www.npmjs.com/package/newman) (para execução dos testes do Postman)

## Instalação

### 1. Clone o repositório

```bash
git clone https://github.com/klebersouza/api-test-project-postman-newman.git
cd api-test-project-postman-newman
```

### 2. Instale as dependências

O projeto utiliza o Newman como dependência global. Para instalá-lo, execute:

```bash
npm install -g newman
npm install -g newman-reporter-html
```

## Estrutura do Projeto

- collections/: Contém as coleções de testes organizadas por tipo (contract-tests, functional-tests, etc.).
- environments/: Contém os arquivos de ambiente (development.postman_environment.json, production.postman_environment.json).
- reports/: Diretório onde os relatórios em HTML serão gerados.

## Executando os Testes

Executar testes de contrato no ambiente de desenvolvimento

```bash
npm run test:contract:dev
```

Executar testes de contrato no ambiente de produção

```bash
npm run test:contract:prod
```

Executar todos os testes no ambiente de desenvolvimento

```bash
npm run test:all:dev
```

Executar todos os testes no ambiente de produção

```bash
npm run test:all:prod
```

## Personalizando os Testes

Iterações e Delay
Você pode ajustar o número de iterações e o delay entre as requisições diretamente nos scripts package.json. Por exemplo:

```bash
newman run collections/performance-load-tests/my-collection.json -n 100 --delay-request 200 -e environments/development.postman_environment.json
```

### Uso de Arquivos de Dados

Para passar dados diferentes em cada iteração (por exemplo, simular múltiplos usuários), você pode utilizar arquivos CSV ou JSON:

```bash
newman run collections/performance-load-tests/my-collection.json -d data.csv -e environments/development.postman_environment.json
```

## Relatórios

Os relatórios são gerados em HTML e salvos na pasta reports/, organizados por data e tipo de teste. Para visualizar um relatório, basta abrir o arquivo HTML no navegador.

## Contribuições

Sinta-se à vontade para contribuir com este projeto. Se encontrar algum problema ou tiver sugestões, abra uma issue ou faça um pull request.

## Licença

Este projeto está licenciado sob a MIT License.
