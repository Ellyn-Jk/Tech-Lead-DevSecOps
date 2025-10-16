---

## 👩‍💻 Autoria
Angelina, Bruna, Ellyn e Gabriela

---

# 🛡️ Projeto DevSecOps – Juice Shop

Este repositório documenta a aplicação de uma esteira DevSecOps sobre o projeto [Juice Shop](https://github.com/juice-shop/juice-shop), utilizando ferramentas de análise de segurança em código-fonte, dependências e containers.

---

## 🎯 Objetivo

Implementar uma esteira de segurança automatizada que identifique vulnerabilidades em diferentes camadas da aplicação, promovendo práticas de desenvolvimento seguro e rastreabilidade dos achados.

---

## 🔍 Ferramentas utilizadas

- **Semgrep**: análise estática de código-fonte (SAST)
- **Trivy**: scan de vulnerabilidades em containers Docker
- **Snyk**: análise de segurança em dependências de projeto (SCA – Software Composition Analysis)
- **OWASP Dependency-Check**: tentativa de scan de dependências (não executado com sucesso)

---

## 🧪 Scanners aplicados

### ✅ Semgrep

- Tipo: SAST (Node.js)
- Total de alertas: 179
- Severidade: alta, média e baixa
- Relatório: `relatorios/semgrep-result.txt`
- Explicação: `relatorios/semgrep-explicacao.md`

### ✅ Trivy

- Tipo: Container (Docker)
- Imagem escaneada: `bkimminich/juice-shop`
- Vulnerabilidades encontradas: diversas em pacotes do sistema
- Relatório: `relatorios/trivy-result.txt`
- Explicação: `relatorios/trivy-explicacao.md`

### ✅ Snyk

- Tipo: SCA (npm)
- Total de vulnerabilidades: 61
- Caminhos vulneráveis: 76
- Severidade: crítica, alta, média e baixa
- Relatório: `relatorios/snyk-result.txt`
- Explicação: `relatorios/snyk-explicacao.md`

### ⚠️ OWASP Dependency-Check

- Status: não executado com sucesso
- Motivo: erro 403 ao acessar feeds da NVD
- Explicação: incluída em `snyk-explicacao.md`

---

## 📁 Estrutura do repositório
Tech-Lead-DevSecOps/ ├── relatorios/ │   ├── semgrep-result.txt │   ├── trivy-result.txt │   ├── snyk-result.txt │   ├── resumo-vulnerabilidades.md │   ├── semgrep-explicacao.md │   ├── snyk-explicacao.md │   └── trivy-explicacao.md ├── infra/ │   └── docker-compose.yml (se aplicável) ├── README.md


---

## 📌 Observações finais

- A aplicação Juice Shop foi escaneada em ambiente local via Docker (`localhost:3000`)
- Todos os scanners foram executados manualmente e documentados
- O relatório consolidado está disponível em `relatorios/resumo-vulnerabilidades.md`

---

