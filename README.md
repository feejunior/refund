# Refund

Aplicação web para solicitação de reembolso de despesas. Cadastre despesas por categoria, acompanhe a lista de solicitações e veja o total atualizado em tempo real, com valores formatados em Real (BRL).

## Funcionalidades

- Cadastro de despesa com nome, categoria e valor
- Máscara de moeda automática no campo de valor (`R$ 0,00`)
- Categorias com ícone próprio: Alimentação, Hospedagem, Serviços, Transporte e Outros
- Remoção de despesas da lista
- Contador de despesas e soma total recalculados a cada alteração
- Validação de campos obrigatórios e tratamento de erros

## Tecnologias

- HTML5
- CSS3
- JavaScript (vanilla, sem frameworks)
- Google Fonts (Open Sans)

## Como executar

Não há dependências nem build. Basta clonar e abrir o `index.html` no navegador:

```bash
git clone git@github.com:feejunior/refund.git
cd refund
```

Depois abra o `index.html` direto no navegador, ou sirva a pasta com um servidor local:

```bash
npx serve .
```

## Estrutura

```
refund/
├── img/          # logo e ícones das categorias
├── index.html    # estrutura da página
├── styles.css    # estilos
└── scripts.js    # lógica: máscara de moeda, adicionar/remover despesas, totais
```

## Como funciona

1. O campo de valor remove tudo que não é dígito, divide por 100 e formata com `toLocaleString('pt-BR', { style: 'currency', currency: 'BRL' })`.
2. Ao enviar o formulário, um objeto da despesa é criado e renderizado como item da lista, com o ícone da categoria.
3. A cada inclusão ou remoção, `updateTotals()` percorre os itens, converte os valores e atualiza a quantidade e o total.
