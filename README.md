# Assistente de Receitas Culinárias com Google Gemini

Este projeto utiliza o modelo Gemini do Google para criar um assistente de receitas culinárias. O assistente é capaz de buscar receitas, planejar o passo a passo, redigir a receita em detalhes e revisar o texto final para garantir clareza e precisão.

## Funcionalidades

* **Busca de Receitas:** O assistente busca receitas na web com base em um ingrediente fornecido pelo usuário.
* **Planejamento de Receitas:** Cria um plano detalhado da receita, incluindo porções e sugestões de variações.
* **Redação de Receitas:** Escreve a receita completa, com lista de ingredientes, quantidades e modo de preparo passo a passo.
* **Revisão de Receitas:** Revisa o texto da receita para garantir clareza, precisão e concisão.

## Como Usar

1.  **Pré-requisitos:**
    * Conta Google com acesso à API Gemini.
    * Chave da API do Google Gemini configurada como variável de ambiente (`GOOGLE_API_KEY`). Você pode usar o `userdata.get()` do Google Colab para armazenar sua chave de forma segura.
    * Python 3.6 ou superior.
    * Bibliotecas Python: `google-generativeai`, `google-adk`.

2.  **Instalação:**

    ```bash
    !pip install -q --upgrade google-generativeai google-adk
    ```

3.  **Configuração da Chave da API:**

    No Google Colab, você pode configurar a chave da API usando:

    ```python
    import os
    from google.colab import userdata
    os.environ["GOOGLE_API_KEY"] = userdata.get('GOOGLE_API_KEY')
    ```

    Certifique-se de substituir `'GOOGLE_API_KEY'` pelo nome da chave que você configurou no Colab Secrets.

4.  **Execução:**

    Execute o script Python. Ele solicitará que você digite um ingrediente. O assistente irá gerar a receita completa com base nesse ingrediente.

    ```python
    ingrediente = input("Digite o ingrediente para buscar receitas: ")
    # O restante do código irá processar e exibir a receita
    ```

## Arquitetura

O assistente é construído utilizando múltiplos agentes, cada um responsável por uma etapa do processo de criação da receita:

* **Agente Buscador de Ingredientes:** Utiliza a ferramenta de busca do Google (`google_search`) para encontrar receitas relacionadas ao ingrediente fornecido.
* **Agente Planejador de Receitas:** Cria um plano detalhado da receita com base nos resultados da busca.
* **Agente Redator de Receitas:** Escreve a receita completa em formato de texto.
* **Agente Revisor de Receitas:** Revisa e edita o texto da receita para garantir a qualidade final.

## Tecnologias Utilizadas

* **Google Gemini:** Modelo de linguagem do Google para geração de texto.
* **Google ADK (Agent Development Kit):** Framework para construção de agentes.
* **Google Search Tool:** Ferramenta para realizar buscas na web.
* **Python:** Linguagem de programação.

## Observações

* Certifique-se de que sua chave da API do Google Gemini está configurada corretamente para que o script funcione.
* O script foi desenvolvido e testado no Google Colab.
* A qualidade da receita gerada depende da precisão do ingrediente fornecido e da capacidade do modelo Gemini.

## Contribuição

Contribuições são bem-vindas! Se você tiver alguma sugestão de melhoria ou encontrar algum problema, sinta-se à vontade para abrir uma issue ou enviar um pull request.

## Licença

[MIT License]
