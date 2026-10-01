# Política de Segurança

## Relato responsável

Não publique credenciais, tokens, chaves privadas, cookies, dados pessoais, endpoints internos ou evidências sensíveis em issues, pull requests, commits ou logs públicos.

Ao identificar uma vulnerabilidade ou exposição de segredo, interrompa qualquer exploração além do necessário para confirmar o problema e faça a rotação/revogação imediata das credenciais afetadas quando aplicável.

## Tratamento de segredos

- Nunca versionar arquivos `.env` com valores reais.
- Nunca armazenar tokens ou chaves diretamente no código-fonte.
- Utilizar variáveis de ambiente ou secret managers apropriados.
- Aplicar princípio do menor privilégio.
- Preferir credenciais de curta duração e rotação quando suportado.
- Evitar logs de `Authorization`, cookies, prompts sensíveis ou payloads completos de provedores.

## Integrações com IA e LLMs

Antes de enviar dados a um provedor externo, considerar classificação da informação, privacidade, retenção do provedor e necessidade real de transmissão. Fallbacks entre provedores devem ser explícitos quando puderem alterar privacidade, custo ou semântica.

## Dependências e supply chain

- Revisar novas dependências e sua necessidade real.
- Evitar dependências sem manutenção quando houver alternativa adequada.
- Em automações CI/CD, preferir permissões mínimas e versões imutáveis/pinadas quando viável.
- Não conceder permissões de escrita a workflows que necessitam apenas leitura.

## Resposta a incidentes

Quando houver suspeita de exposição:

1. Revogar ou rotacionar o segredo afetado.
2. Verificar logs e histórico de uso.
3. Remover o segredo do código e da configuração.
4. Avaliar necessidade de limpeza do histórico Git.
5. Registrar causa raiz e ações preventivas sem republicar o segredo.
