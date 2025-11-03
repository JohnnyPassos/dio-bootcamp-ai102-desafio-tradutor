# 🌐 Tradutor Inteligente com Azure OpenAI (ChatGPT 5 Mini)

Este projeto foi desenvolvido durante o **Bootcamp da DIO** como parte da **preparação para a certificação Microsoft AI-102 (Designing and Implementing an Azure AI Solution)**.  
O objetivo é criar um **tradutor profissional em Python** capaz de **traduzir textos, páginas da web e gerar documentos Word**, utilizando o modelo **ChatGPT 5 Mini** por meio do **Azure OpenAI Service**, tudo executado diretamente no **Google Colab**.

---

## 🚀 Funcionalidades Principais

✅ Tradução automática entre idiomas usando **ChatGPT 5 Mini (Azure OpenAI)**  
✅ Extração de conteúdo textual de **páginas da web (HTML)**  
✅ Geração automática de **documentos Word (.docx)** com formatação elegante  
✅ Download direto dos arquivos no **Google Colab**  
✅ Suporte a variáveis de ambiente para maior segurança  
✅ Código modular e didático, ideal para estudos e certificações  

---

## 🧩 Tecnologias Utilizadas

- **Python 3.10+**
- **Google Colab**
- **Azure OpenAI (ChatGPT 5 Mini)**
- **Bibliotecas:**
  - `openai`
  - `requests`
  - `beautifulsoup4`
  - `python-docx`
  - `python-dotenv`
  - `google.colab`
  - `datetime`, `os`, `typing`

---

## ⚙️ Como Executar no Google Colab

### 1️⃣ Acesse o Google Colab
- Vá para [Google Colab](https://colab.research.google.com/)
- Faça upload do notebook:
  ```
  tradutorazureai.ipynb
  ```

### 2️⃣ Instale as dependências (executar a primeira célula)
O notebook já contém o comando:
```python
!pip install -q requests beautifulsoup4 python-docx openai python-dotenv
```
> 💡 Isso garante que tudo será instalado automaticamente no ambiente do Colab.

### 3️⃣ Configure suas credenciais Azure
Antes de usar o modelo, defina suas chaves:
```python
import os

os.environ["AZURE_OPENAI_KEY"] = "sua_chave_aqui"
os.environ["AZURE_OPENAI_ENDPOINT"] = "seu_endpoint_aqui"
os.environ["AZURE_OPENAI_API_VERSION"] = "2024-02-01"
```

### 4️⃣ Crie a instância do Tradutor
```python
tradutor = TradutorGPT5Mini(
    api_key=os.getenv("AZURE_OPENAI_KEY"),
    api_version=os.getenv("AZURE_OPENAI_API_VERSION"),
    azure_endpoint=os.getenv("AZURE_OPENAI_ENDPOINT")
)
```

### 5️⃣ Traduza textos ou páginas da web
```python
# Tradução direta de texto
traducao = tradutor.traduzir_texto("Olá, como você está?", "pt", "en")
print(traducao)
```

```python
# Extração e tradução de conteúdo de uma página da web
titulo, texto = tradutor.extrair_texto_url("https://pt.wikipedia.org/wiki/Intelig%C3%AAncia_artificial")
traducao_site = tradutor.traduzir_texto(texto, "pt", "en")
```

### 6️⃣ Gere e baixe o documento Word traduzido
```python
tradutor.gerar_documento_word(texto, traducao_site, "pt", "en")
```
O arquivo será baixado automaticamente via `google.colab.files.download()`.

---

## 🧠 Estrutura do Projeto

```
tradutor-azureai/
│
├── tradutorazureai.ipynb     # Notebook principal
├── README.md                  # Documentação do projeto
└── assets/                    # (opcional) imagens, exemplos, etc.
```

---

## 💡 Exemplo de Saída

📄 O Word gerado contém:
- Título e data de tradução  
- Texto original e traduzido lado a lado  
- Formatação com cores, fontes e alinhamentos  
- Pronto para compartilhamento ou revisão  

---

## 🧾 Licença

Este projeto está sob a licença **MIT** — veja o arquivo `LICENSE` para mais detalhes.

---

## 👨‍💻 Autor

Desenvolvido por **Johnny Pasos**  
💼 Bootcamp: *DIO - Microsoft AI-102 Preparation*  
📧 Contato: johnnypassos07@gmail.com  
🔗 LinkedIn: https://www.linkedin.com/in/johnny-passos-1aa06359/

---

## 🏷️ Badges 

```markdown
![Feito no Google Colab](https://img.shields.io/badge/Google%20Colab-Notebook-blue?logo=googlecolab)
![Azure OpenAI](https://img.shields.io/badge/Azure%20OpenAI-ChatGPT%205%20Mini-0078D4?logo=microsoftazure)
![Python 3.10+](https://img.shields.io/badge/Python-3.10+-green?logo=python)
![Licença MIT](https://img.shields.io/badge/Licença-MIT-yellow)
```
