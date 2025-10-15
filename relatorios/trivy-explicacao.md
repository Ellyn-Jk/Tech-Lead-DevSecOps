# Relatório Trivy – Juice Shop

**Data do scan:** 13/10/2025  
**Imagem escaneada:** `bkimminich/juice-shop`  
**Ferramenta utilizada:** [Trivy](https://github.com/aquasecurity/trivy)  
**Tipo de scan:** Container (imagem Docker)

---

## 📊 Resumo dos resultados

| Componente escaneado                      | Tipo     | Vulnerabilidades encontradas | Segredos detectados |
|------------------------------------------|----------|-------------------------------|----------------------|
| bkimminich/juice-shop (debian 12.11)     | debian   | 16                            | 0                    |
| juice-shop/package.json (e demais módulos)| node-pkg | 0                             | 0                    |

---

## 🔍 Análise das vulnerabilidades

As 16 vulnerabilidades foram encontradas no sistema operacional base da imagem (`debian 12.11`). Nenhuma vulnerabilidade foi detectada nas dependências Node.js da aplicação.

**Principais observações:**

- As vulnerabilidades estão relacionadas a pacotes do sistema Debian, como bibliotecas nativas e utilitários.
- Nenhum segredo sensível (como tokens, senhas ou chaves) foi identificado.
- O código-fonte da aplicação (Node.js) está limpo segundo o Trivy.

---

## ✅ Ações recomendadas

- **Atualizar a imagem base**: Verificar se há uma versão mais recente da imagem `bkimminich/juice-shop` que utilize uma base Debian atualizada.
- **Monitorar dependências do sistema**: Usar ferramentas como [Grype](https://github.com/anchore/grype) ou [Snyk](https://snyk.io) para complementar a análise.
- **Complementar com scanner de código-fonte**: Integrar o [Semgrep](https://semgrep.dev) para detectar vulnerabilidades lógicas no código da aplicação.

---

## 📁 Evidência técnica

O relatório completo gerado pelo Trivy está disponível em: relatorios/trivy-result.txt


---

## 🧠 Conclusão

O scan inicial com Trivy revelou vulnerabilidades no sistema operacional da imagem Docker, mas nenhuma falha nas dependências Node.js. Isso indica que o Juice Shop está bem mantido em termos de código, mas pode se beneficiar de uma atualização da imagem base para mitigar riscos no ambiente de execução.

