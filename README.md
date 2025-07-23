# 🍃 Black Tea Therapy

> **Protocolo de Saúde Mental para a Comunidade Negra**\
> Utilizando Web3 para democratizar o acesso à saúde mental de qualidade no Brasil

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/) [![Next.js](https://img.shields.io/badge/Next.js-14.0-black)](https://nextjs.org/) [![Web3](https://img.shields.io/badge/Web3-Enabled-blue)](https://web3js.org/) [![Build Status](https://img.shields.io/github/workflow/status/DGuedz/Blackteatherapy/CI)](https://github.com/DGuedz/Blackteatherapy/actions)

## 🌟 **Visão Geral**

Black Tea Therapy é um protocolo inovador de saúde mental que combina:

* **IA Empática** para triagem cultural inteligente
* **Privacidade Web3** com zero-knowledge proofs
* **Rede de Psicólogos** especializados na comunidade negra
* **Token $BLACKSTAR** para economia sustentável

## 🚀 **Quick Start**

```bash
# Clone o repositório
git clone https://github.com/DGuedz/Blackteatherapy.git

# Instale as dependências
npm install

# Configure as variáveis de ambiente
cp .env.example .env.local

# Execute em desenvolvimento
npm run dev
```

## 🏗️ **Arquitetura**

```
black-tea-therapy/
├── 🌐 web-platform/          # Next.js frontend
├── 📱 mobile-app/            # React Native app
├── 🔗 smart-contracts/       # Solidity contracts
├── 🤖 ai-services/           # ML/AI microservices
├── 📊 analytics/             # Data analytics
└── 🔧 infrastructure/        # DevOps configs
```

## 🛠️ **Stack Tecnológico**

### **Frontend**

* ⚛️ **React 19** + **Next.js 14**
* 🎨 **Tailwind CSS** para estilização
* 🔗 **Wagmi** + **Web3.js** para Web3
* 📱 **React Native** para mobile

### **Blockchain**

* 🔗 **Multi-chain bridge** (interoperabilidade)
* 🔷 **Ethereum Base** (L2 principal)
* 🟡 **BNB Smart Chain** (micropagamentos)
* 🟣 **Scroll** (privacy com zkEVM)


### **Backend**

* 🚀 **Node.js** + **TypeScript**
* ⚡ **Fastify** para APIs
* 🔍 **GraphQL** para queries
* 🗄️ **Prisma** + **PostgreSQL**

### **AI/ML**

* 🐍 **Python** + **TensorFlow**
* 🧠 **Hugging Face** transformers
* 🔮 **Federated Learning** para privacidade
* 📊 **Analytics** com privacy diferencial

## 💎 **Tokenomics - $BLACKSTAR**

| Aspecto            | Detalhes                         |
| ------------------ | -------------------------------- |
| **Token Standard** | ERC-20                           |
| **Supply Total**   | 100,000,000 BLACKSTAR            |
| **Chains**         | Ethereum Base, BNB Chain, Scroll |
| **Utilidade**      | Pagamentos, (stable), governança, staking  |

## 🤝 **Como Contribuir**

1. 🍴 **Fork** o projeto
2. 🌿 Crie sua **feature branch** (`git checkout -b feature/AmazingFeature`)
3. 💻 **Commit** suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. 📤 **Push** para a branch (`git push origin feature/AmazingFeature`)
5. 🔄 Abra um **Pull Request**

## 📋 **Roadmap**
* [x] **Q3 2025** - MVP Web Platform
* [x] **Q3 2025** - Smart Contracts v1
* [ ] **Q1 2026** - Mobile App Launch
* [ ] **Q2 2026** - Token $BLACKSTAR TGE
* [ ] **Q2 2025** - AI Oracle v2
* [ ] **Q4 2025** - Multi-chain expansion

## 📜 **Licença**

Distribuído sob a licença MIT. Veja `LICENSE` para mais informações.

## 🌍 **Contato**

* 📧 **Email:** <dguedz07@gmail.com>
* 🐦 **X:** [@dg\_doublegreen](https://x.com/dg_doublegreen)
* 🌐 **GitHub:** [DGuedz](https://github.com/DGuedz)

***

**🍃 Transformando vidas através de tecnologia descentralizada e cuidado humanizado 🍃**

Made with ❤️ by [Black Mindz C.O.](https://github.com/BlackMindzCO)

***

## 🔧 **Configurações de Repositório**

### **1. Branch Protection Rules**

```yaml
Branch: main
Settings:
  - Require pull request reviews before merging
  - Require status checks to pass before merging
  - Require branches to be up to date before merging
  - Include administrators
  - Allow force pushes: false
  - Allow deletions: false
```

### **2. GitHub Actions Workflows**

#### **CI/CD Pipeline (.github/workflows/ci.yml)**

```yaml
name: CI/CD Pipeline

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main ]

jobs:
  test:
    runs-on: ubuntu-latest
    
    strategy:
      matrix:
        node-version: [18.x, 20.x]
        
    steps:
    - uses: actions/checkout@v4
    
    - name: Use Node.js ${{ matrix.node-version }}
      uses: actions/setup-node@v4
      with:
        node-version: ${{ matrix.node-version }}
        cache: 'npm'
        
    - run: npm ci
    - run: npm run build --if-present
    - run: npm test
    - run: npm run lint
    
  security:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v4
    - name: Run Snyk to check for vulnerabilities
      uses: snyk/actions/node@master
      env:
        SNYK_TOKEN: ${{ secrets.SNYK_TOKEN }}
        
  deploy:
    needs: [test, security]
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main'
    
    steps:
    - uses: actions/checkout@v4
    - name: Deploy to Production
      run: |
        echo "Deploying to production..."
        # Add deployment scripts here
```

### **3. Issue Templates**

#### **Bug Report (.github/ISSUE\_TEMPLATE/bug\_report.md)**

```markdown
---
name: Bug report
about: Create a report to help us improve
title: '[BUG] '
labels: 'bug'
assignees: ''
---

**Describe the bug**
A clear and concise description of what the bug is.

**To Reproduce**
Steps to reproduce the behavior:
1. Go to '...'
2. Click on '....'
3. Scroll down to '....'
4. See error

**Expected behavior**
A clear and concise description of what you expected to happen.

**Screenshots**
If applicable, add screenshots to help explain your problem.

**Environment:**
 - OS: [e.g. iOS]
 - Browser [e.g. chrome, safari]
 - Version [e.g. 22]

**Additional context**
Add any other context about the problem here.
```

#### **Feature Request (.github/ISSUE\_TEMPLATE/feature\_request.md)**

```markdown
---
name: Feature request
about: Suggest an idea for this project
title: '[FEATURE] '
labels: 'enhancement'
assignees: ''
---

**Is your feature request related to a problem? Please describe.**
A clear and concise description of what the problem is.

**Describe the solution you'd like**
A clear and concise description of what you want to happen.

**Describe alternatives you've considered**
A clear and concise description of any alternative solutions.

**Additional context**
Add any other context or screenshots about the feature request here.
```

### **4. Pull Request Template**

#### **.github/pull\_request\_template.md**

```markdown
## Description
Brief description of changes made.

## Type of Change
- [ ] Bug fix (non-breaking change which fixes an issue)
- [ ] New feature (non-breaking change which adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] Documentation update

## Testing
- [ ] Unit tests pass
- [ ] Integration tests pass
- [ ] Manual testing completed

## Checklist
- [ ] My code follows the style guidelines of this project
- [ ] I have performed a self-review of my own code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings
- [ ] New and existing unit tests pass locally with my changes

## Screenshots (if applicable)
Add screenshots to help explain your changes.

## Additional Notes
Any additional information that reviewers should know.
```

***

## 🏷️ **Labels Padrão**

### **Categorias**

* 🐛 `bug` - Something isn't working
* ✨ `enhancement` - New feature or request
* 📚 `documentation` - Improvements or additions to documentation
* 🔧 `infrastructure` - DevOps and infrastructure changes
* 🎨 `ui/ux` - User interface and experience improvements
* 🔒 `security` - Security-related issues
* ⚡ `performance` - Performance improvements
* 🧪 `testing` - Testing-related changes

### **Prioridades**

* 🔴 `priority: high` - High priority
* 🟡 `priority: medium` - Medium priority
* 🟢 `priority: low` - Low priority

### **Status**

* 🚧 `in progress` - Work in progress
* ✅ `ready for review` - Ready for code review
* 🔄 `needs changes` - Changes requested
* ✅ `approved` - Approved and ready to merge

***

## 📊 **Métricas e Monitoring**

### **GitHub Insights**

* Code frequency
* Commit activity
* Contributors
* Community standards
* Dependency graph
* Security advisories

### **Badges para README**

```markdown
[![GitHub issues](https://img.shields.io/github/issues/DGuedz/Blackteatherapy)](https://github.com/DGuedz/Blackteatherapy/issues)
[![GitHub forks](https://img.shields.io/github/forks/DGuedz/Blackteatherapy)](https://github.com/DGuedz/Blackteatherapy/network)
[![GitHub stars](https://img.shields.io/github/stars/DGuedz/Blackteatherapy)](https://github.com/DGuedz/Blackteatherapy/stargazers)
[![GitHub license](https://img.shields.io/github/license/DGuedz/Blackteatherapy)](https://github.com/DGuedz/Blackteatherapy/blob/main/LICENSE)
```

***

## 🎯 **Próximos Passos**

### **Fase 1: Setup Inicial**

1. ✅ Criar repositório principal
2. ✅ Configurar templates e workflows
3. ✅ Definir branch protection rules
4. ✅ Implementar CI/CD pipeline

### **Fase 2: Desenvolvimento**

1. 🔄 Implementar MVP web platform
2. 🔄 Desenvolver smart contracts
3. 🔄 Configurar monitoring
4. 🔄 Documentação completa

### **Fase 3: Comunidade**

1. 📢 Open source announcement
2. 👥 Community guidelines
3. 🎓 Contribution tutorials
4. 🏆 Recognition system

***

## 📋 **DOCUMENTOS POR PASTA - DETALHAMENTO**

### 📁 **Raiz do Projeto**

| Documento            | Descrição               | Conteúdo Principal                             |
| -------------------- | ----------------------- | ---------------------------------------------- |
| `README.md`          | Visão geral do projeto  | Overview, instalação, uso básico, contribuição |
| `LICENSE`            | Licença MIT             | Licença de código aberto                       |
| `.gitignore`         | Arquivos ignorados      | node\_modules, .env, builds, logs              |
| `.env.example`       | Exemplo de variáveis    | DATABASE\_URL, JWT\_SECRET, API\_KEYS          |
| `package.json`       | Configuração do projeto | Scripts, dependências, metadados               |
| `docker-compose.yml` | Orquestração Docker     | Serviços: web, api, db, redis                  |
| `CONTRIBUTING.md`    | Guia de contribuição    | Como contribuir, padrões, workflow             |
| `CODE_OF_CONDUCT.md` | Código de conduta       | Comportamento esperado da comunidade           |
| `SECURITY.md`        | Política de segurança   | Como reportar vulnerabilidades                 |
| `CHANGELOG.md`       | Histórico de mudanças   | Versões, features, correções                   |

### 📁 **.github/ (Automação GitHub)**

| Documento                  | Descrição           | Conteúdo Principal                  |
| -------------------------- | ------------------- | ----------------------------------- |
| `bug_report.md`            | Template de bug     | Estrutura para reportar bugs        |
| `feature_request.md`       | Template de feature | Estrutura para solicitar features   |
| `user_story.md`            | Template user story | Estrutura para histórias de usuário |
| `PULL_REQUEST_TEMPLATE.md` | Template PR         | Checklist para pull requests        |
| `ci.yml`                   | Pipeline CI/CD      | Build, test, deploy automático      |
| `security.yml`             | Análise segurança   | Snyk, CodeQL, dependency check      |
| `deploy.yml`               | Deploy automático   | Deploy para staging/production      |
| `tests.yml`                | Testes automáticos  | Unit, integration, e2e tests        |
| `dependabot.yml`           | Atualizações deps   | Configuração dependabot             |

### 📁 **docs/ (Documentação Técnica)**

| Documento         | Descrição             | Conteúdo Principal                    |
| ----------------- | --------------------- | ------------------------------------- |
| `ARCHITECTURE.md` | Arquitetura sistema   | Diagramas, padrões, decisões técnicas |
| `API.md`          | Documentação API      | Endpoints, parâmetros, exemplos       |
| `DEPLOYMENT.md`   | Guia de deploy        | Instruções de deployment              |
| `DEVELOPMENT.md`  | Setup desenvolvimento | Como configurar ambiente local        |
| `DATABASE.md`     | Schema banco dados    | Tabelas, relacionamentos, índices     |
| `PROTOCOL.md`     | Protocolo Black Tea   | Metodologia clínica detalhada         |
| `TOKENOMICS.md`   | Documentação token    | $BLACKSTAR tokenomics completa        |
| `ROADMAP.md`      | Roadmap técnico       | Milestones, timeline, features        |

### 📁 **frontend/ (Aplicação Web)**

| Pasta/Arquivo        | Descrição          | Conteúdo Principal                  |
| -------------------- | ------------------ | ----------------------------------- |
| `package.json`       | Deps frontend      | React, Next.js, Tailwind, Web3      |
| `next.config.js`     | Config Next.js     | Webpack, env vars, optimizations    |
| `tailwind.config.js` | Config Tailwind    | Tema customizado, cores brand       |
| `tsconfig.json`      | Config TypeScript  | Strict mode, paths, target          |
| `src/components/`    | Componentes React  | Header, Footer, Forms, Cards        |
| `src/pages/`         | Páginas Next.js    | Home, Dashboard, Profile, Therapy   |
| `src/hooks/`         | Hooks customizados | useAuth, useWeb3, useTherapy        |
| `src/utils/`         | Utilitários        | Helpers, formatters, validators     |
| `src/styles/`        | Estilos CSS        | Global styles, components CSS       |
| `src/lib/`           | Bibliotecas        | API clients, configs, constants     |
| `src/types/`         | Tipos TypeScript   | Interfaces, enums, type definitions |
| `public/`            | Arquivos estáticos | Images, icons, manifests            |
| `tests/`             | Testes frontend    | Jest, React Testing Library         |

### 📁 **backend/ (API e Servidor)**

| Pasta/Arquivo          | Descrição          | Conteúdo Principal                   |
| ---------------------- | ------------------ | ------------------------------------ |
| `package.json`         | Deps backend       | Fastify, Prisma, JWT, bcrypt         |
| `tsconfig.json`        | Config TypeScript  | Server-side configuration            |
| `Dockerfile`           | Container Docker   | Node.js container setup              |
| `src/controllers/`     | Controladores API  | Auth, Users, Therapy, Payments       |
| `src/models/`          | Modelos dados      | User, Session, Payment, Professional |
| `src/routes/`          | Rotas API          | REST endpoints organization          |
| `src/middleware/`      | Middlewares        | Auth, CORS, rate limiting, logging   |
| `src/services/`        | Lógica negócio     | Business logic, external APIs        |
| `src/utils/`           | Utilitários        | Helpers, validators, formatters      |
| `src/config/`          | Configurações      | Database, JWT, email, blockchain     |
| `src/server.ts`        | Servidor principal | Fastify server setup                 |
| `prisma/schema.prisma` | Schema banco       | Database models, relations           |
| `prisma/migrations/`   | Migrações DB       | Database migrations                  |
| `tests/`               | Testes backend     | Jest, supertest, API tests           |

### 📁 **mobile/ (React Native App)**

| Pasta/Arquivo     | Descrição          | Conteúdo Principal                 |
| ----------------- | ------------------ | ---------------------------------- |
| `package.json`    | Deps mobile        | React Native, Expo, navigation     |
| `app.json`        | Config Expo        | App settings, splash, icons        |
| `babel.config.js` | Config Babel       | Transpilation settings             |
| `src/screens/`    | Telas app          | Login, Dashboard, Chat, Profile    |
| `src/components/` | Componentes mobile | Buttons, Forms, Cards, Lists       |
| `src/navigation/` | Navegação          | Stack, Tab, Drawer navigation      |
| `src/services/`   | APIs serviços      | HTTP client, WebSocket, Push       |
| `src/hooks/`      | Hooks mobile       | useAuth, useChat, useNotifications |
| `src/utils/`      | Utilitários        | Helpers, storage, permissions      |
| `src/types/`      | Tipos TypeScript   | Mobile-specific types              |
| `assets/`         | Assets app         | Icons, images, fonts               |
| `tests/`          | Testes mobile      | Detox, Jest, component tests       |

### 📁 **smart-contracts/ (Blockchain)**

| Pasta/Arquivo          | Descrição        | Conteúdo Principal              |
| ---------------------- | ---------------- | ------------------------------- |
| `package.json`         | Deps contratos   | Hardhat, OpenZeppelin, ethers   |
| `hardhat.config.ts`    | Config Hardhat   | Networks, compilers, plugins    |
| `.env.example`         | Env contratos    | Private keys, RPC URLs          |
| `BlackStarToken.sol`   | Token ERC-20     | $BLACKSTAR token implementation |
| `HealthRegistry.sol`   | Registro saúde   | Patient records, privacy        |
| `TherapySession.sol`   | Sessões terapia  | Booking, payments, reviews      |
| `ProfessionalDAO.sol`  | DAO psicólogos   | Governance, voting, staking     |
| `MultiChainBridge.sol` | Bridge chains    | Cross-chain functionality       |
| `scripts/`             | Scripts deploy   | Deployment scripts              |
| `test/`                | Testes contratos | Solidity tests, coverage        |
| `deployments/`         | Deployments      | Contract addresses per network  |

### 📁 **ai-services/ (Serviços IA)**

| Pasta/Arquivo      | Descrição          | Conteúdo Principal                 |
| ------------------ | ------------------ | ---------------------------------- |
| `requirements.txt` | Deps Python        | TensorFlow, scikit-learn, pandas   |
| `Dockerfile`       | Container IA       | Python container setup             |
| `main.py`          | App principal      | FastAPI server for AI services     |
| `models/`          | Modelos IA         | Trained models, weights            |
| `training/`        | Scripts treino     | Training pipelines, datasets       |
| `inference/`       | Inferência         | Prediction endpoints               |
| `preprocessing/`   | Pré-processo       | Data cleaning, feature engineering |
| `utils/`           | Utilitários Python | Helper functions, validators       |
| `tests/`           | Testes IA          | Model tests, API tests             |

### 📁 **infrastructure/ (DevOps)**

| Pasta/Arquivo | Descrição           | Conteúdo Principal             |
| ------------- | ------------------- | ------------------------------ |
| `terraform/`  | Infrastructure Code | AWS/GCP resource definitions   |
| `kubernetes/` | K8s manifests       | Deployments, services, ingress |
| `docker/`     | Dockerfiles         | Specialized containers         |
| `nginx/`      | Config Nginx        | Load balancer, SSL, caching    |
| `monitoring/` | Monitoring          | Prometheus, Grafana configs    |
| `scripts/`    | Scripts automação   | Deployment, backup scripts     |

### 📁 **database/ (Banco de Dados)**

| Pasta/Arquivo | Descrição       | Conteúdo Principal          |
| ------------- | --------------- | --------------------------- |
| `migrations/` | Migrações SQL   | Database schema changes     |
| `seeds/`      | Dados iniciais  | Sample data, test fixtures  |
| `backups/`    | Scripts backup  | Automated backup procedures |
| `schema.sql`  | Schema completo | Full database schema        |

### 📁 **analytics/ (Analytics e BI)**

| Pasta/Arquivo      | Descrição         | Conteúdo Principal            |
| ------------------ | ----------------- | ----------------------------- |
| `requirements.txt` | Deps Python       | Pandas, Matplotlib, Jupyter   |
| `notebooks/`       | Jupyter notebooks | Data analysis, visualization  |
| `reports/`         | Relatórios        | Business intelligence reports |
| `dashboards/`      | Dashboards        | Grafana, Metabase configs     |
| `data/`            | Datasets          | Sample data, analysis results |

### 📁 **security/ (Segurança)**

| Documento            | Descrição            | Conteúdo Principal              |
| -------------------- | -------------------- | ------------------------------- |
| `security-policy.md` | Política segurança   | Security guidelines, procedures |
| `audits/`            | Relatórios auditoria | Security audit reports          |
| `penetration-tests/` | Testes penetração    | Pentest results, fixes          |
| `compliance/`        | Compliance           | LGPD, HIPAA documentation       |

### 📁 **legal/ (Documentos Legais)**

| Documento                | Descrição            | Conteúdo Principal        |
| ------------------------ | -------------------- | ------------------------- |
| `privacy-policy.md`      | Política privacidade | LGPD compliance document  |
| `terms-of-service.md`    | Termos serviço       | User agreement, liability |
| `gdpr-compliance.md`     | Compliance GDPR      | European data protection  |
| `professional-ethics.md` | Ética profissional   | CRP guidelines, ethics    |

### 📁 **marketing/ (Marketing)**

| Pasta/Arquivo    | Descrição          | Conteúdo Principal        |
| ---------------- | ------------------ | ------------------------- |
| `brand/`         | Identidade visual  | Logos, colors, typography |
| `presentations/` | Apresentações      | Pitch decks, demos        |
| `content/`       | Conteúdo marketing | Blog posts, case studies  |
| `social-media/`  | Redes sociais      | Post templates, campaigns |

### 📁 **tools/ (Ferramentas)**

| Pasta/Arquivo | Descrição        | Conteúdo Principal       |
| ------------- | ---------------- | ------------------------ |
| `generators/` | Geradores código | Code scaffolding tools   |
| `validators/` | Validadores      | Data validation scripts  |
| `linters/`    | Config linting   | ESLint, Prettier configs |
| `formatters/` | Formatadores     | Code formatting rules    |

***

## 🎯 **REPOSITÓRIOS SATÉLITES**

### 📂 **blackstar-token**

```
blackstar-token/
├── 📄 README.md                          # Token documentation
├── 📁 contracts/                         # Solidity contracts
├── 📁 scripts/                           # Deployment scripts
├── 📁 test/                              # Contract tests
├── 📁 docs/                              # Tokenomics docs
└── 📁 audits/                            # Security audits
```

### 📂 **therapy-mobile-app**

```
therapy-mobile-app/
├── 📄 README.md                          # Mobile app docs
├── 📁 src/                               # React Native source
├── 📁 assets/                            # App assets
├── 📁 docs/                              # Mobile documentation
└── 📁 store-assets/                      # App Store assets
```

### 📂 **blackmindz-ai-oracle**

```
blackmindz-ai-oracle/
├── 📄 README.md                          # AI system docs
├── 📁 models/                            # ML models
├── 📁 training/                          # Training scripts
├── 📁 api/                               # API endpoints
├── 📁 docs/                              # AI documentation
└── 📁 research/                          # Research papers
```

***

## 🚀 **PRIORIZAÇÃO DE DESENVOLVIMENTO**

### **Fase 1 - Core MVP (Mês 1-2)**

1. `README.md` - Visão geral impactante
2. `docs/PROTOCOL.md` - Metodologia clínica
3. `frontend/` - Landing page e dashboard básico
4. `backend/` - API básica e auth
5. `smart-contracts/BlackStarToken.sol` - Token ERC-20

### **Fase 2 - Features Básicas (Mês 3-4)**

1. `mobile/` - App React Native MVP
2. `ai-services/` - IA básica de triagem
3. `docs/API.md` - Documentação completa
4. `infrastructure/` - Deploy automático
5. `security/` - Auditoria inicial

### **Fase 3 - Escalabilidade (Mês 5-6)**

1. `analytics/` - Dashboard BI
2. `smart-contracts/` - Contratos avançados
3. `legal/` - Compliance completo
4. `marketing/` - Materiais profissionais
5. `tools/` - Ferramentas desenvolvimento

***
