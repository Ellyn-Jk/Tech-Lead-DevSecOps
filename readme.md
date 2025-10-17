## 👩‍💻 Autoria

Este projeto foi conduzido por **Angelina**, **Bruna**, **Ellyn**, **Gabriela**

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
## ✅ Instruções de Avaliação do Projeto DevSecOps

Este documento orienta o avaliador sobre como instalar, executar e verificar os resultados do projeto DevSecOps automatizado via GitHub Actions.

---

## 1. Clonar o repositório

```bash
git clone https://github.com/Ellyn-Jk/seu-repositorio.git
cd seu-repositorio

##2. Verificar os arquivos principais
Certifique-se de que o repositório contém:
- .github/workflows/devsecops.yml → workflow automatizado
- Código-fonte ou arquivos de dependência (ex: package.json, requirements.txt)
- Pasta relatorios/ (gerada automaticamente após execução)

##3. Acessar o GitHub Actions
- Vá até a aba Actions no repositório
- Clique no workflow chamado DevSecOps Scan
- Verifique os passos executados:
- Rodar Semgrep
- Rodar Trivy via Docker
- Autenticar e rodar Snyk
- Upload dos relatórios

##4. Baixar os relatórios
- Ao final da execução, localize a seção Artifacts
- Clique em relatorios-devsecops
- Baixe o arquivo compactado
- Dentro dele estarão:
- semgrep-result.txt
- trivy-result.txt
- snyk-result.txt

##5. Validar os resultados
Abra os arquivos .txt e verifique:
- Vulnerabilidades encontradas
- Qual scanner detectou o quê
- Se os resultados estão coerentes com o código

##6. Confirmar automação
O workflow é disparado automaticamente em:
- push para a branch main
- pull_request para a branch main

##7. Requisitos atendidos
- ✔️ Integração de três scanners: Semgrep, Trivy e Snyk
- ✔️ Execução automatizada via GitHub Actions
- ✔️ Geração e entrega de relatórios
- ✔️ Organização em um único fluxo (DevSecOps Scan)

##🧠 Observação
Para que o scanner Snyk funcione corretamente, é necessário configurar o token SNYK_TOKEN como segredo no GitHub. O projeto já está preparado para isso.




---
## 📌 Observações finais

- A aplicação Juice Shop foi escaneada em ambiente local via Docker (`localhost:3000`)
- Todos os scanners foram executados manualmente e documentados
- O relatório consolidado está disponível em `relatorios/resumo-vulnerabilidades.md`

---
