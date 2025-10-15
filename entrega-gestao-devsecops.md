# 🧭 Justificativa para Adoção de DevSecOps

A adoção de DevSecOps representa uma evolução estratégica na forma como organizações desenvolvem, operam e protegem seus sistemas digitais. Ao integrar segurança desde o início do ciclo de desenvolvimento, é possível reduzir riscos, acelerar entregas e aumentar a confiança em ambientes críticos.

### 🎯 Benefícios para a Alta Gestão (C-Level)

- **Redução de riscos operacionais e reputacionais**  
  Vulnerabilidades são identificadas e corrigidas antes de chegarem à produção.

- **Agilidade com segurança**  
  Automatização de verificações permite entregas rápidas sem comprometer a integridade.

- **Conformidade contínua**  
  Facilita auditorias e aderência a normas como LGPD, ISO 27001, PCI-DSS.

- **Economia de recursos**  
  Corrigir falhas em produção custa até 30x mais do que em desenvolvimento (Fonte: IBM Security).

- **Casos reais**  
  Empresas como Netflix, Capital One e Mercado Livre adotaram DevSecOps para escalar com segurança e reduzir incidentes.

---

# 🛡️ Política de Segurança DevSecOps

Esta subseção define diretrizes mínimas para os times de desenvolvimento e operações, com foco em segurança contínua e colaborativa.

### 🔧 Diretrizes e Boas Práticas

- Integrar ferramentas de segurança automatizadas (SAST, SCA, Container Scan) desde o início do desenvolvimento.
- Garantir que todo código passe por análise estática antes de ser integrado à base principal.
- Validar dependências externas com scanners de vulnerabilidades (ex: Snyk, Trivy).
- Monitorar imagens de containers e ambientes de produção com ferramentas como Trivy e Falco.

### 👥 Responsabilidades

- **Time de Desenvolvimento**  
  Responsável por aplicar boas práticas de codificação segura e corrigir vulnerabilidades identificadas.

- **Time de Segurança (SecOps)**  
  Responsável por definir políticas, revisar achados críticos e garantir conformidade.

- **Gestores Técnicos (Tech Leads / Dev Managers)**  
  Responsáveis por garantir que a esteira DevSecOps esteja integrada e funcional.

### 📉 Metodologia de Avaliação e Mitigação de Riscos

- **Avaliação:**  
  Classificação de vulnerabilidades por severidade (CVSS), impacto no negócio e exposição pública.

- **Mitigação:**  
  Correção direta, substituição de dependências, isolamento de componentes e aplicação de patches.

- **Ferramentas utilizadas:**  
  Semgrep (SAST), Snyk (SCA), Trivy (Container), GitHub Actions (CI/CD)

---

# 📁 Localização no Repositório

Este documento está localizado em:Tech-Lead-DevSecOps/gestao-devsecops.md
