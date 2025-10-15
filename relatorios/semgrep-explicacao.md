# Relatório Semgrep – Juice Shop

**Data do scan:** 14/10/2025  
**Ferramenta utilizada:** [Semgrep OSS](https://semgrep.dev)  
**Tipo de scan:** Análise estática de código-fonte (SAST)

---

## 📊 Resumo do scan

- **Arquivos escaneados:** 5135 (apenas arquivos rastreados pelo Git)
- **Regras aplicadas:** 479
- **Achados totais:** 179 (todos classificados como "blocking")
- **Linhas analisadas:** ~100%
- **Arquivos ignorados:**  
  - 4 arquivos maiores que 1 MB  
  - 133 arquivos ignorados via `.semgrepignore`

---

## ⚠️ Alertas e limitações

- 2 regras apresentaram erro de timeout em arquivos da pasta `venv/`, relacionadas à `hardcoded-token` da biblioteca `boto3`
- O scan foi realizado com Semgrep OSS, sem acesso às regras avançadas do Semgrep Pro (1390 regras adicionais não aplicadas)
- Semgrep Supply Chain (SCA) e Semgrep Code (SAST avançado) não foram executados por falta de login

---

## 🧠 Interpretação dos achados

- Os 179 achados indicam potenciais vulnerabilidades ou más práticas no código-fonte
- Como o scan foi feito com regras básicas, os resultados podem conter falsos positivos ou alertas genéricos
- Para uma análise mais precisa, recomenda-se ativar o Semgrep Pro e revisar os achados manualmente

---

## ✅ Ações recomendadas

- **Revisar os 179 achados** no arquivo `semgrep-result.txt`, priorizando os de maior severidade
- **Ignorar achados em arquivos da pasta `venv/`**, pois são dependências externas
- **Criar uma conta gratuita no Semgrep Cloud** para desbloquear regras avançadas e reduzir ruído: [https://sg.run/cloud](https://sg.run/cloud)
- **Rodar Semgrep com `--verbose`** para identificar arquivos e linhas ignoradas

---

## 📁 Evidência técnica

O relatório completo gerado pelo Semgrep está disponível em:
relatorios/semgrep-result.txt

---

## 🧪 Observação final

O Semgrep OSS oferece uma boa cobertura inicial para vulnerabilidades em código próprio, mas para uma análise mais refinada e com menos falsos positiv

