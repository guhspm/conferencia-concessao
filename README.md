# ✅ Conferência Automática de Concessões
> Auditoria automática de arquivos TXT de concessão de benefícios — valida regras de negócio (inclusão, exclusão, PS29) e gera relatório Excel multi-aba por arquivo.

![Python](https://img.shields.io/badge/Python-3.10+-8b5cf6?style=flat-square&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.x-8b5cf6?style=flat-square&logo=pandas&logoColor=white)
![xlsxwriter](https://img.shields.io/badge/xlsxwriter-3.x-8b5cf6?style=flat-square&logoColor=white)
![Status](https://img.shields.io/badge/Status-Em%20Produção-22c55e?style=flat-square)

---

## 📌 Sobre o Projeto

Sistema de auditoria de arquivos de concessão de benefícios em formato TXT (`;` separado).

O script detecta **todos os arquivos `.txt` da pasta automaticamente**, valida cada registro contra regras de negócio específicas e gera um relatório Excel com abas separadas por categoria — erros, duplicidades, análise PS29.

**Problema resolvido:** a conferência manual de arquivos de concessão/exclusão exigia leitura linha a linha com risco de inconsistências passarem despercebidas. O script garante cobertura de 100% dos registros em segundos.

---

## 🚀 Funcionalidades

- ✅ **Processamento em lote** — analisa todos os `.txt` da pasta em uma execução
- ✅ **Separação inclusões/exclusões** — trata `TIPO_OPERACAO = I` e `E` com regras distintas
- ✅ **Validações automáticas:**
  - Exclusão sem motivo de cancelamento
  - Exclusão com data inválida (`00000000`)
  - Data de concessão anterior ao limite mínimo (01/12/2021)
  - Carteirinhas duplicadas em inclusões e exclusões
- ✅ **Análise PS29** — verifica se a inclusão correspondente existe e se a data é o dia seguinte à exclusão
- ✅ **Relatório Excel multi-aba** por arquivo
- ✅ **Tolerância a erros** — arquivo problemático não interrompe os demais

---

## 🛠️ Stack

| Tecnologia | Uso |
|---|---|
| Python 3.10+ | Lógica principal |
| Pandas | Leitura e análise dos TXTs |
| xlsxwriter | Relatório Excel com múltiplas abas |
| glob | Descoberta automática de arquivos |
| datetime | Cálculo de datas (regra PS29) |

---

## 📁 Estrutura

```
conferencia-concessao/
├── conferenciaconcessao.py     # Script principal
├── requirements.txt
├── .gitignore
└── README.md

# Coloque os arquivos .txt na mesma pasta antes de executar
```

---

## ⚙️ Como Executar

```bash
pip install -r requirements.txt
python conferenciaconcessao.py
```

---

## 📈 Exemplo de Output

```
Iniciando processo de conferência automática...
Encontrados 3 arquivos para analisar.

-----------------------------------------------------
Analisando o arquivo: CONCESSAO_JAN2026.txt
Relatório salvo com sucesso em: 'Relatorio_Conferencia_CONCESSAO_JAN2026.xlsx'

-----------------------------------------------------
Processo de conferência concluído para todos os arquivos.
```

**Abas geradas no Excel por arquivo:**

| Aba | Conteúdo |
|---|---|
| Inclusoes | Todos os registros de inclusão |
| Exclusoes | Todos os registros de exclusão |
| Duplicados_Inclusao | Carteirinhas duplicadas em inclusões |
| Duplicados_Exclusao | Carteirinhas duplicadas em exclusões |
| Relatorio_de_Erros | Erros de validação com linha e CPF |
| Erros_Analise_PS29 | Inconsistências PS29 |

---

## 👤 Autor

**Gustavo** — Dev & Founder · Inside.co

[![LinkedIn](https://img.shields.io/badge/LinkedIn-8b5cf6?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/gustavo-henriquesp/)
[![Portfolio](https://img.shields.io/badge/Portfolio-8b5cf6?style=flat-square&logo=netlify&logoColor=white)](https://seusite.netlify.app)
[![Email](https://img.shields.io/badge/Email-8b5cf6?style=flat-square&logo=gmail&logoColor=white)](mailto:ghspdm@gmail.com)

---
> *"Construo soluções que outros apenas descrevem em planilhas."*
