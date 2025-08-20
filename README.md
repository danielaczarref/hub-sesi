# Hub Sesi - Repositório Principal

Este repositório contém todos os projetos como submodules.

## Estrutura:
- `frontend/` - [hub-sesi-frontend](https://github.com/danielaczarref/hub-sesi-frontend)
- `backend/nodejs/` - [hub-sesi-node-backend](https://github.com/danielaczarref/hub-sesi-node-backend)
- `backend/java-spring/` - [hub-sesi-java-backend](https://github.com/danielaczarref/hub-sesi-java-backend)
- `backend/python-datascience/` - [hub-sesi-python-backend](https://github.com/danielaczarref/hub-sesi-python-backend)

## Como clonar:
git clone --recurse-submodules git@github.com:danielaczarref/hub-sesi.git


## ✅ **1. Visão Geral do Projeto**

Criar um sistema web seguro (intranet) que se integre com o RH da empresa para **monitorar, analisar e prever padrões de absenteísmo**. O sistema usará **dados internos + formulários anônimos** para gerar relatórios, gráficos e perfis de risco com base em características dos colaboradores.

---

## 🧩 **2. Componentes do Sistema**

### 🧑‍💼 Acesso e Permissões

* **Usuário colaborador**: acesso apenas ao formulário.
* **Gestores e RH**: acesso aos resultados e dashboards.
* **Administrador**: configura permissões, usuários e integrações.

### 📝 Coleta de dados

* Opção 1: colaborador preenche **formulário individual e anônimo**
* Opção 2: empresa importa **base de colaboradores** via planilha/ETL/API

### 🔄 Integração de dados (ETL)

* Unifica dados do formulário com os dados do RH
* Aplica limpeza, transformação e anonimização
* Gera base unificada para análise

---

## 🛠️ **3. Funcionalidades do Sistema**

### 🔐 Acesso e Segurança

* Login por intranet/SSO
* Sessão por tempo limitado
* Controle de permissões

### 📥 Coleta

* Formulário de registro (ou primeira vez)
* Formulário recorrente de feedback (ausência, clima organizacional, sintomas de estresse)

### 📊 Análise e Visualização

* Dashboards com:

  * % de absenteísmo por setor/cargo/gênero
  * Comparativo entre áreas
  * Evolução mensal
* Mapas de calor por equipe/departamento
* Geração de perfis de risco com IA/statística:

  * Ex: “Jovens do setor operacional com baixa escolaridade e salário abaixo da média têm 30% mais faltas”

### 🧠 Previsões

* Algoritmo de previsão (regressão, classificação ou clustering) para:

  * Detectar quem está mais propenso a faltar
  * Prever risco de aumento do absenteísmo

---

## 🔄 **4. ETL no projeto**

**Extract**

* CSV da empresa com: `nome`, `cargo`, `setor`, `idade`, `gênero`, `salário`, `escolaridade`, `dias de falta`, `motivo`, etc
* Formulários do sistema preenchidos

**Transform**

* Normalização (ex: padronizar cargos)
* Agrupamentos
* Anonimização (remover nome ou CPF)
* Preenchimento de campos faltantes

**Load**

* Banco de dados relacional ou warehouse (MySQL, PostgreSQL ou BigQuery)
* Base servirá como fonte para dashboards e análises

---

## 🧰 **5. Tecnologias sugeridas**

| Componente     | Sugestão técnica                                   |
| -------------- | -------------------------------------------------- |
| Frontend       | ReactJS (ou VueJS) + Tailwind                      |
| Backend/API    | Node.js (Express) ou Python (Flask/Django)         |
| Banco de dados | PostgreSQL ou MySQL (ou SQLite para POC)           |
| ETL            | Python (pandas + agendamento com cron) ou Airbyte  |
| Visualização   | Chart.js, Recharts, Power BI Embedded, ou Metabase |
| Autenticação   | LDAP, SSO da empresa, ou login com permissões      |
| Hospedagem     | Servidor interno (intranet) ou Docker privado      |

---

## 🔮 **6. Possíveis Extensões Futuras**

* Questionários de clima organizacional
* Análise de presenteísmo (produtividade baixa)
* Gatilhos automáticos para RH intervir (ex: faltas consecutivas)
* Integração com calendário de férias/licenças
* API para importar dados de plataformas de ponto ou ERP

---

## 🧭 Próximos passos sugeridos:

1. **Validar o escopo com a empresa** (reunião rápida para entender as dores específicas e se aceitam formulário anônimo, etc.)
2. **Criar um protótipo (wireframe)** da interface do sistema
3. **Montar um banco de dados de exemplo**
4. **Fazer um MVP** com:

   * Upload de CSV de colaboradores
   * Um formulário
   * Um dashboard simples


