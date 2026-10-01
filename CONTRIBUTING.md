# Guia de Contribuição

## Fluxo recomendado

1. Crie uma branch curta e descritiva a partir de `main`.
2. Mantenha a alteração focada em um único objetivo.
3. Use commits pequenos, compreensíveis e reversíveis.
4. Execute testes, lint e validações aplicáveis antes de abrir o PR.
5. Preencha o template do pull request com contexto, riscos e forma de validação.

## Convenção de commits

Preferir Conventional Commits quando aplicável:

- `feat:` nova capacidade
- `fix:` correção de defeito
- `docs:` documentação
- `refactor:` mudança estrutural sem alteração intencional de comportamento
- `test:` testes
- `chore:` manutenção e configuração
- `ci:` automação de integração/entrega
- `perf:` melhoria de desempenho
- `security:` correção ou endurecimento de segurança

Exemplo:

```text
feat(router): add NVIDIA NIM provider adapter
```

## Critérios de qualidade

- Sem credenciais ou segredos versionados.
- Tratamento explícito de erros e timeouts em integrações externas.
- Testes para comportamento novo ou alterado, quando aplicável.
- Documentação sincronizada com a implementação.
- Mudanças incompatíveis descritas explicitamente.
- Dependências novas justificadas.
- Código gerado por IA deve ser entendido e revisado antes do merge.

## Arquitetura para LLMs

Em projetos com múltiplos provedores, evitar chamadas diretas espalhadas pela aplicação. Centralizar integração em interfaces/adapters e manter roteamento de modelos separado da regra de negócio. Configurações, políticas, observabilidade e segredos devem permanecer em fronteiras próprias.

## Pull requests

PRs devem responder claramente:

- Qual problema está sendo resolvido?
- Por que esta abordagem foi escolhida?
- Como validar a mudança?
- Quais riscos existem?
- Como reverter se necessário?
