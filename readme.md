## 👩‍💻 Autoria
Este projeto foi conduzido por **Angelina Maria**, **Bruna Alves**, **Ellyn Josefik**, **Gabriela Lindenberg**

---

# 🛡️ Projeto DevSecOps – Juice Shop
Este repositório documenta a aplicação de uma esteira DevSecOps sobre o projeto [Juice Shop](https://github.com/juice-shop/juice-shop), utilizando ferramentas de análise de segurança em código-fonte, dependências e containers.

---

# 💬 Observações gerais 
- Para que o scanner Snyk funcione corretamente, é necessário configurar o token SNYK_TOKEN como segred>
- Optamos por incluir o projeto Juice Shop como submódulo Git porque ele possui muitos arquivos e dependências pesadas. Durante a execução do projeto, ao tentar subir o projeto juice-shop o git exibiu a mensagem de erro informando que alguns arquivos excediam o limite de tamanho.
- Como opção também deixamos o projeto .zip
- A aplicação Juice Shop foi escaneada em ambiente local via Docker (`localhost:3000`)
- Todos os scanners foram executados manualmente e documentados
- O relatório consolidado está disponível em `relatorios/resumo-vulnerabilidades.md`

---

## 📁 Estrutura do repositório
Tech-Lead-DevSecOps/
├── infra/                          # Scripts e arquivos de infraestrutura como código
│   ├── docker-compose.yml          # Arquivo de orquestração para subir serviços em containers
│   └── README.md                   # Explicação sobre a infraestrutura utilizada
│
├── juice-shop/                     # Aplicação vulnerável usada para testes de segurança
│   ├── README.md                   # Instruções sobre como executar e testar a aplicação
│   └── docker-compose.yml          # Configuração para subir o Juice Shop via Docker
│
├── relatorios/                     # Relatórios e explicações das ferramentas de segurança utilizadas
│   ├── .gitkeep                    # Arquivo para manter a pasta no repositório mesmo vazia
│   ├── resumo-vulnerabilidades.md # Resumo consolidado das vulnerabilidades encontradas
│   ├── semgrep-explicacao.md      # Explicação sobre a ferramenta Semgrep
│   ├── semgrep-result.txt         # Resultados da análise com Semgrep
│   ├── snyk-explicacao.md         # Explicação sobre a ferramenta Snyk
│   ├── snyk-result.txt            # Resultados da análise com Snyk
│   ├── trivy-explicacao.md        # Explicação sobre a ferramenta Trivy
│   ├── trivy-result.txt           # Resultados da análise com Trivy
│
├── README.md                       # Documento principal com visão geral do projeto

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

## ✅ Instruções de Avaliação do Projeto DevSecOps

Este documento orienta o avaliador sobre como instalar, executar e verificar os resultados do projeto DevSecOps automatizado via GitHub Actions.

---

## 1. Clonar o repositório
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


---
