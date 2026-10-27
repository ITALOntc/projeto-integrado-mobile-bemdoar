# Casos de uso

## Visitante

- Consultar necessidades, campanhas, oportunidades e ações sociais públicas.
- Consultar indicadores de transparência.
- Criar uma conta e autenticar-se.

## Usuário autenticado

- Registrar e acompanhar doações.
- Candidatar-se a oportunidades de voluntariado.
- Consultar participação e notificações.
- Atualizar dados do próprio perfil.

## Administrador

- Gerenciar categorias e necessidades.
- Confirmar, receber ou cancelar doações.
- Gerenciar campanhas, comunicados e oportunidades.
- Avaliar candidaturas e registrar participações.
- Gerenciar ações sociais, resultados e evidências.
- Atualizar dados institucionais.

## Fluxo principal de doação

```mermaid
flowchart TD
    A[Usuário escolhe necessidade] --> B[Registra intenção de doação]
    B --> C[PENDENTE]
    C -->|Administrador confirma| D[CONFIRMADA]
    D -->|Item recebido| E[RECEBIDA]
    E --> F[Progresso da necessidade atualizado]
    C -->|Cancelamento| G[CANCELADA]
    D -->|Cancelamento| G
```
