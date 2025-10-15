# Relatório Snyk – Juice Shop

**Data do scan:** 14/10/2025  
**Ferramenta utilizada:** [Snyk CLI](https://snyk.io)  
**Tipo de scan:** Verificação de vulnerabilidades em dependências (npm)

---

## Resultado do scan

O Snyk analisou 1004 dependências e encontrou:

- **61 vulnerabilidades**
- **76 caminhos vulneráveis**

As vulnerabilidades estão distribuídas entre:

- **15 de severidade moderada**
- **3 de severidade alta**
- **Algumas críticas e sem correção disponível**

---

## Exemplos de vulnerabilidades encontradas

- **Prototype Pollution** em `lodash`, `unset-value`, `messageformat`
- **Authentication Bypass** e **Improper Authentication** em `jsonwebtoken`
- **Denial of Service (DoS)** em `ws`, `tar`, `moment`
- **Remote Code Execution (RCE)** em `vm2`
- **Cross-site Scripting (XSS)** em `sanitize-html`, `socket.io`

---

## Ações recomendadas

- Atualizar pacotes como `express-jwt`, `jsonwebtoken`, `sanitize-html`, `socket.io`, `multer`, `lodash`, entre outros
- Rodar `npm audit fix` e revisar os impactos de `npm audit fix --force`
- Avaliar dependências sem correção disponível e considerar alternativas ou isolamento

---

## Observação sobre o OWASP Dependency-Check

A tentativa de executar o OWASP Dependency-Check falhou devido a **restrições de acesso aos feeds da NVD**, resultando em erro 403 (Forbidden). Isso impediu o download dos arquivos de CVEs necessários para o scan. A falha está documentada no terminal e foi registrada como limitação técnica da ferramenta em ambientes protegidos.

---

## Conclusão

O scanner Snyk foi executado com sucesso sobre o código da aplicação Juice Shop, revelando vulnerabilidades reais e relevantes. A documentação foi atualizada para refletir os achados e a limitação do Dependency-Check.
