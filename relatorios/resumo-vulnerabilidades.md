# 🛡️ Resumo de Vulnerabilidades – Projeto DevSecOps

Este documento consolida os resultados dos scanners de segurança aplicados à aplicação Juice Shop, como parte da esteira DevSecOps.

---

## 🔍 Ferramentas utilizadas

- **Semgrep**: análise estática de código-fonte (SAST)
- **Trivy**: scan de vulnerabilidades em containers Docker
- **Snyk**: análise de segurança em dependências de projeto (SCA – Software Composition Analysis)

---
##🧪 Resultados do Snyk

**Data do scan:** 14/10/2025
**Tipo de análise:** Dependências (SCA – npm)
|  |  |  | 
|  |  | vm2multermarsdb | 
|  |  | lodashjsonwebtokensanitize-html | 
|  |  | momentsocket.iosanitize-htmlgot | 
|  |  | web3hbs | 



Observações
- Foram encontradas 61 vulnerabilidades em 76 caminhos vulneráveis
- Algumas dependências críticas não possuem correção disponível
- O scan foi realizado sobre o código da aplicação Juice Shop, após instalação das dependências via npm install
- O relatório completo está salvo em relatorios/snyk-result.txt
- A explicação detalhada está em relatorios/snyk-explicacao.md

Ações recomendadas
- Atualizar pacotes como express-jwt, jsonwebtoken, sanitize-html, socket.io, multer, lodash, entre outros
- Rodar npm audit fix e revisar os impactos de npm audit fix --force
- Avaliar dependências sem correção disponível e considerar alternativas ou isolamento

⚠️ Scanner OWASP Dependency-Check
Status: Não executado com sucesso
Motivo: Erro 403 ao acessar feeds da NVD (restrição de rede)
Resultado: Sem relatório gerado
Observação: A falha está documentada no terminal e explicada em snyk-explicacao.md


--
## 🧪 Resultados do Semgrep

**Data do scan:** 14/10/2025  
**Tipo de análise:** Código-fonte (SAST – Node.js)

| Severidade | Quantidade estimada | Exemplos                                   |
|------------|----------------------|--------------------------------------------|
| HIGH       | 1+                   | Uso inseguro de `eval` ou funções dinâmicas |
| MEDIUM     | 1+                   | Falta de validação de entrada em rotas     |
| LOW        | 1+                   | Comentários com dados sensíveis            |

---

### Observações

- Foram encontrados **179 alertas**, todos classificados como "blocking"
- O scan foi realizado com **Semgrep OSS**, sem acesso às regras avançadas do Semgrep Pro
- Algumas regras apresentaram **timeout** em arquivos da pasta `venv/` (ignorar)
- Recomendado revisar os achados manualmente e ativar o Semgrep Pro para reduzir ruído

---

### Ações recomendadas

- Priorizar revisão dos achados de alta severidade
- Ignorar alertas em dependências externas (`venv/`)
- Criar conta gratuita no [Semgrep Cloud](https://sg.run/cloud) para acesso a regras avançadas

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
- Complementar a análise com scanners de código-fonte (Semgrep) e dependências (OWASP Dependency-Check, Snyk)
- Documentar e tratar vulnerabilidades críticas conforme os CVEs identificados

---

## 📁 Evidências técnicas

- [`trivy-result.txt`](trivy-result.txt): relatório bruto gerado pelo Trivy  
- [`trivy-explicacao.md`](trivy-explicacao.md): análise detalhada das evidências  
- [`semgrep-result.txt`](semgrep-result.txt): relatório bruto gerado pelo Semgrep  
- [`semgrep-explicacao.md`](semgrep-explicacao.md): análise detalhada das evidências
