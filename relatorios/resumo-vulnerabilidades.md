# 🛡️ Resumo de Vulnerabilidades – Projeto DevSecOps

Este documento consolida os resultados dos scanners de segurança aplicados à aplicação Juice Shop, como parte da esteira DevSecOps.

---

## 🔍 Ferramentas utilizadas

- **Trivy**: scan de vulnerabilidades em containers Docker
- *(Em breve: Semgrep, OWASP Dependency-Check, Snyk)*

---

## 📊 Resultados do Trivy

**Imagem escaneada:** `bkimminich/juice-shop`  
**Data do scan:** 13/10/2025  
**Sistema base:** Debian 12.11  
**Dependências Node.js:** Nenhuma vulnerabilidade detectada

| Componente escaneado                  | Tipo     | Vulnerabilidades | Segredos |
|--------------------------------------|----------|------------------|----------|
| bkimminich/juice-shop (debian 12.11) | debian   | 16               | 0        |
| package.json e node_modules          | node-pkg | 0                | 0        |

---

## 🧠 Análise inicial

- Todas as vulnerabilidades estão concentradas no sistema operacional base da imagem Docker.
- O código-fonte da aplicação (Node.js) está limpo segundo o Trivy.
- Nenhum segredo sensível foi identificado.

---

## ✅ Ações recomendadas

- Verificar se há uma versão mais recente da imagem `bkimminich/juice-shop` com base atualizada
- Complementar a análise com scanners de código-fonte (Semgrep) e dependências (OWASP Dependency-Check)
- Documentar e tratar vulnerabilidades críticas conforme os CVEs identificados

---

## 📁 Evidências técnicas

- [`trivy-result.txt`](trivy-result.txt): relatório bruto gerado pelo Trivy
- [`trivy-explicacao.md`](trivy-explicacao.md): análise detalhada das evidências

---

## ⏭️ Próximos passos

- Executar o scanner Semgrep para análise do código-fonte
- Atualizar este documento com os resultados e recomendações
