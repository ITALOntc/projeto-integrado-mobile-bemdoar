# Regras de negócio

- Cadastro público sempre cria usuário comum; privilégios administrativos não são concedidos pelo frontend.
- Senhas são armazenadas de forma criptografada e a API usa JWT para autenticação.
- Cada usuário acessa apenas seus próprios dados privados; operações administrativas exigem perfil de administrador.
- Quantidades de doação devem ser positivas.
- Uma doação segue o fluxo `PENDENTE -> CONFIRMADA -> RECEBIDA`; cancelamentos respeitam as regras do estado atual.
- Somente doações recebidas alteram o progresso de uma necessidade.
- Necessidades atendidas ou encerradas não devem aceitar novas doações.
- Candidaturas aprovadas ocupam vagas; candidaturas pendentes não ocupam.
- Evidências públicas podem ser exibidas ao visitante; evidências privadas ficam restritas à administração.
- Indicadores de transparência apresentam dados agregados, sem expor dados pessoais.

As implementações autoritativas dessas regras ficam nos serviços do backend. Esta documentação resume o comportamento e não substitui validações e testes automatizados.
