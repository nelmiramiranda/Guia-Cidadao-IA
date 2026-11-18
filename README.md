# 🏛️ Guia Cidadão (Conecta Direitos)

> Assistente virtual inteligente desenvolvido em Python e Google GenAI para traduzir a linguagem burocrática de portais governamentais para uma linguagem acessível, acolhedora e segura, garantindo conformidade com a LGPD.

---

## 💡 Sobre o Projeto
O **Guia Cidadão** nasce da intersecção entre tecnologia e impacto social. A iniciativa busca mitigar barreiras de acesso a políticas públicas de assistência social (como o Cadastro Único e o Bolsa Família), orientando cidadãos de forma clara, humanizada e estritamente baseada em dados oficiais do Governo Federal.

Desenvolvido como projeto para o programa **Futures da Softplan**, o sistema utiliza técnicas de *grounding* (base de conhecimento governamental integrada) para evitar alucinações da inteligência artificial e protocolos rígidos de privacidade de dados.

---

## 🛠️ Tecnologias e Ferramentas Utilizadas
* **Python 3.10+** (Ambiente de desenvolvimento)
* **Google Colab** (Plataforma de execução e prototipagem)
* **Google GenAI SDK** (`google-genai`)
* **Modelo LLM:** `gemini-2.0-flash` (alta performance e eficiência para processamento de linguagem natural)
* **Gerenciamento de Segredos:** Colab Secrets (`GEMINI_API_KEY`) para proteção de credenciais

---

## ⚙️ Arquitetura e Boas Práticas
1. **Grounding Governamental:** O modelo é alimentado estritamente com trechos e diretrizes validadas (CadÚnico e Bolsa Família), restringindo suas respostas ao escopo oficial fornecido.
2. **Conformidade com a LGPD:** O prompt de sistema instrui a IA a identificar e ignorar dados sensíveis de identificação pessoal (como CPF ou RG), alertando educadamente o usuário sobre a importância da privacidade.
3. **Engenharia de Prompt Estruturada:** Uso de instruções de sistema (`System Instructions`) focadas em tom acolhedor, clareza e baixa temperatura (`temperature=0.2`) para respostas precisas e consistentes.

---

## 🚀 Como Executar o Projeto

1. Clone o repositório ou abra o arquivo `Guia_Cidadao_IA.ipynb` no **Google Colab**.
2. Configure a sua chave da API do Gemini no painel de **Segredos (ícone de chave 🔑)** do Colab com a chave nomeada como `GEMINI_API_KEY`.
3. Execute as células em sequência para testar as simulações de atendimento e o filtro de privacidade LGPD.

---

## 📂 Estrutura do Código

```python
# Exemplo simplificado da chamada do cliente Gemini com System Instructions
response = client.models.generate_content(
    model='gemini-2.0-flash',
    contents=prompt_completo,
    config=types.GenerateContentConfig(
        system_instruction=SYSTEM_INSTRUCTION,
        temperature=0.2,
    ),
)
