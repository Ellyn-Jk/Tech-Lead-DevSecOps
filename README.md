# 🛡️ Tech Lead DevSecOps – Juice Shop

Este projeto demonstra a implementação de uma esteira DevSecOps com foco em segurança de aplicações, utilizando scanners automatizados e documentação de evidências.

---

## 🚀 Objetivo

Integrar práticas de segurança na pipeline de desenvolvimento, identificando vulnerabilidades em containers e código-fonte, documentando achados e propondo correções.

---

## 🔍 Scanners utilizados

### Trivy – Vulnerabilidades em containers

```bash
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock aquasec/trivy image bkimminich/juice-shop

### Semgrep – Análise estática de código-fonte
semgrep --config auto --output relatorios/semgrep-result.txt

###📁 Relatórios gerados
- relatorios/trivy-result.txt: relatório bruto do Trivy
- relatorios/trivy-explicacao.md: explicação das evidências do Trivy
- relatorios/semgrep-result.txt: relatório bruto do Semgrep
- relatorios/semgrep-explicacao.md: explicação das evidências do Semgrep
- relatorios/resumo-vulnerabilidades.md: visão consolidada dos achados

###🧠 Boas práticas de segurança
- Atualizar imagens base regularmente
- Validar entradas de usuário
- Evitar funções perigosas como eval
- Monitorar dependências com ferramentas como Snyk e OWASP Dependency-Check

###🛡️ Política de segurança
Este projeto segue os princípios de segurança contínua:
- Detecção proativa de vulnerabilidades
- Documentação clara e rastreável
- Correção baseada em severidade e impacto




