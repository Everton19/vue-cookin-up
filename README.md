# Cookin' Up

Projeto de estudo desenvolvido com Vue 3 + Vite para praticar construção de interfaces, componentização e fluxo de dados em uma aplicação de receitas baseada em ingredientes selecionados.

## Sobre o projeto

Este projeto foi utilizado como estudo de Vue, com foco em conceitos essenciais do ecossistema frontend moderno.

O fluxo da aplicação é simples:

1. O usuário seleciona os ingredientes disponíveis.
2. A aplicação monta uma lista com os itens escolhidos.
3. As receitas são filtradas e exibidas de acordo com os ingredientes necessários.

Os dados de categorias e receitas são carregados via `fetch` a partir de arquivos JSON externos.

## Objetivos de aprendizado

- Praticar componentização com Vue
- Trabalhar com `props`, `emits` e estado local
- Organizar uma aplicação em componentes reutilizáveis
- Consumir dados externos com `fetch`
- Utilizar TypeScript na tipagem de dados e componentes
- Estruturar um projeto frontend com Vite

## Funcionalidades

- Seleção de ingredientes por categoria
- Atualização visual da lista de ingredientes escolhidos
- Busca de receitas compatíveis com os ingredientes selecionados
- Tela de resultados com estado vazio quando nenhuma receita é encontrada
- Layout responsivo para desktop e mobile

## Tecnologias utilizadas

- Vue 3
- TypeScript
- Vite
- ESLint
- Prettier

## Estrutura do projeto

```text
src/
  components/     # componentes visuais e de fluxo da aplicação
  http/           # acesso aos dados de categorias e receitas
  interfaces/     # tipagens TypeScript
  operations/     # funções utilitárias
  assets/         # imagens, ícones e estilos

public/
  images/         # imagens públicas usadas nas receitas e categorias
```

## Como executar localmente

### Pré-requisitos

- Node.js 18+ recomendado
- npm

### Instalação

```bash
npm install
```

### Ambiente de desenvolvimento

```bash
npm run dev
```

### Build de produção

```bash
npm run build
```

### Preview da build

```bash
npm run preview
```

### Lint

```bash
npm run lint
```

### Formatação

```bash
npm run format
```

## Scripts disponíveis

- `npm run dev`: inicia o servidor de desenvolvimento
- `npm run build`: executa type-check e gera a build de produção
- `npm run preview`: abre a build localmente para conferência
- `npm run lint`: valida e corrige problemas de lint
- `npm run format`: formata os arquivos dentro de `src/`

## Regras de negócio implementadas

- Uma receita só é exibida quando todos os ingredientes necessários estão presentes na lista selecionada.
- Ingredientes básicos como sal, pimenta e água são considerados disponíveis, conforme o texto da interface.

## Melhorias futuras

- Adicionar busca por nome da receita
- Permitir remoção em lote dos ingredientes selecionados
- Exibir loading e tratamento de erro nas chamadas HTTP
- Publicar uma demonstração online

## Licença

Este projeto foi desenvolvido para fins de estudo e portfólio. Pode ser usado como referência para aprendizado e personalização.
