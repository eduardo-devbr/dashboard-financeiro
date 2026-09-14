# 💰 Dashboard Financeiro Pessoal

SPA (Single Page Application) para controle financeiro pessoal, construída com React. Permite registrar receitas e despesas, categorizá-las e visualizar a saúde financeira através de gráficos — tudo rodando no navegador, sem backend.

🔗 **Demo:** [link do deploy aqui]

---

## 📸 Screenshots

> _Adicionar prints da aplicação aqui após o polish visual (Dia 5)._

---

## ✨ Funcionalidades

- ✅ Cadastro, edição e exclusão de transações (receita/despesa)
- ✅ Categorização de transações, com categorias customizáveis
- ✅ Filtros por categoria e período (afetam lista e gráficos)
- ✅ Cards de resumo: saldo total, receitas e despesas
- ✅ Gráfico de gastos por categoria (pizza/donut)
- ✅ Gráfico de evolução mensal (linha/barra)
- ✅ Persistência local via `localStorage`
- ✅ Validação de formulário e confirmação antes de exclusões
- ✅ Totalmente responsivo (mobile-first)

---

## 🛠️ Tecnologias

- **[React](https://react.dev/)** (via [Vite](https://vitejs.dev/))
- **Context API + useReducer** — gerenciamento de estado global
- **[Recharts](https://recharts.org/)** — visualização de dados
- **CSS Modules** — estilização com escopo por componente
- **[uuid](https://www.npmjs.com/package/uuid)** — geração de IDs únicos

---

## 📂 Estrutura do Projeto

```
src/
  context/
    FinanceContext.jsx      # estado global + reducer
  hooks/
    useTransactions.js      # lógica de CRUD + cálculos derivados
    useLocalStorage.js      # hook genérico de persistência
  components/
    TransactionForm/
    TransactionList/
    Summary/                # cards de saldo/receita/despesa
    Charts/
      CategoryPieChart/
      MonthlyBarChart/
    CategoryManager/
    ConfirmDialog/
    EmptyState/
  pages/
    Dashboard.jsx
  utils/
    formatters.js            # formatação de moeda/data (pt-BR)
    calculations.js          # funções puras de agregação
    validators.js             # regras de validação de formulário
```

---

## 🚀 Como rodar localmente

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/dashboard-financeiro.git

# Entre na pasta
cd dashboard-financeiro

# Instale as dependências
npm install

# Rode em modo de desenvolvimento
npm run dev
```

O projeto estará disponível em `http://localhost:5173`.

---

## 🧠 Decisões técnicas

- **Sem backend por escolha de escopo**: o foco do projeto é demonstrar domínio de React moderno (state management, componentização, hooks customizados), não construir uma API. Os dados vivem no `localStorage` do navegador.
- **Separação de Context/reducer**: para evitar re-renders desnecessários em uma árvore de componentes com gráficos (que são caros de re-renderizar), o estado foi dividido em [Contexts separados / reducer único com memoização — *ajustar conforme decisão tomada no Dia 1*].
- **Categoria padrão "Outros"**: ao excluir uma categoria que ainda possui transações vinculadas, elas são automaticamente reatribuídas a essa categoria, evitando dados órfãos.
- **Lógica separada de UI**: cálculos e regras de negócio ficam em hooks customizados (`useTransactions`) e funções puras (`utils/calculations.js`), mantendo os componentes focados em apresentação.

---

## 📌 Próximos passos

Funcionalidades fora do escopo do MVP, candidatas a evolução futura:

- Autenticação e suporte a múltiplos usuários
- Backend/API real (substituindo o `localStorage`)
- Metas de gastos mensais
- Transações recorrentes automáticas
- Exportação de relatórios em PDF/CSV

---

## 📄 Licença

Este projeto está sob a licença MIT. Sinta-se livre para usar como referência ou ponto de partida para o seu próprio projeto.
