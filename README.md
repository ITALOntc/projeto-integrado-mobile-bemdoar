# BemDoar

Projeto integrado para gestão de doações, campanhas, voluntariado e ações sociais de uma organização social.

## Equipe

- Responsável pelo repositório: [ITALOntc](https://github.com/ITALOntc)

## Tecnologias

- Frontend: React 18, Vite e React Router, com interface responsiva mobile-first.
- Backend: Java 21, Spring Boot 3.5, Spring Security, JWT, JPA e H2/PostgreSQL.

> **Observação de aderência:** o frontend atual é uma aplicação web responsiva. Ele não é um aplicativo React Native, Flutter, Android ou iOS nativo. Uma entrega que exija binário mobile nativo demandará uma migração tecnológica separada.

## Estrutura do repositório

```text
.
├── assets/                 recursos compartilhados e orientações de mídia
├── backend/                API e regras de negócio
│   └── src/                código-fonte e testes Java
├── docs/                   arquitetura, casos de uso, regras e wireframes
├── frontend/               aplicação principal
│   └── src/                código-fonte e testes React
├── tests/                  scripts e documentação de testes integrados
├── .github/                template de Pull Request
└── iniciar.ps1             inicialização local no Windows
```

Os diretórios `frontend/src` e `backend/src` preservam a organização idiomática dos frameworks adotados. O projeto não move esses fontes para uma pasta artificial na raiz, evitando quebrar Maven, Vite, imports e testes.

## Como executar

### Inicialização rápida no Windows

Na raiz do projeto:

```powershell
.\iniciar.ps1
```

O script verifica Java e Node.js, instala as dependências do frontend quando necessário, inicia os serviços e abre `http://localhost:5173`.

### Execução manual

Backend:

```powershell
cd backend
.\mvnw.cmd spring-boot:run
```

Frontend, em outro terminal:

```powershell
cd frontend
npm install
npm run dev
```

## Testes

Na raiz do projeto:

```powershell
.\tests\run-all.ps1
```

Também é possível executar cada módulo separadamente:

```powershell
cd backend
.\mvnw.cmd test

cd ..\frontend
npm test
npm run build
```

## Fluxo Git

- `main`: versão estável e de produção.
- `develop`: integração das funcionalidades aprovadas.
- `feature/*`: trabalho isolado criado a partir de `develop`.

Fluxo esperado:

```text
feature/* -> Pull Request -> develop -> Pull Request -> main
```

As branches `main` e `develop` exigem Pull Request e pelo menos uma aprovação. Push direto e bypass das regras não são permitidos.

## Documentação

- [Arquitetura](docs/ARQUITETURA.md)
- [Casos de uso](docs/CASOS_DE_USO.md)
- [Regras de negócio](docs/REGRAS_DE_NEGOCIO.md)
- [Wireframes](docs/WIREFRAMES.md)

## Baseline e releases

A primeira baseline deve ser publicada somente após as alterações passarem por Pull Request em `develop` e depois em `main`. A tag planejada é `v1.0.0-alpha`, seguindo versionamento semântico.

As credenciais demonstrativas e o console H2 são exclusivos do ambiente local. Consulte [backend/README.md](backend/README.md) e [frontend/README.md](frontend/README.md).
