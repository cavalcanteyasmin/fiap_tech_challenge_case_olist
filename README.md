# Tech Challenge – Case Olist
## Objetivo

Analisar os dados de e-commerce da Olist entre 2016 e 2018 para identificar oportunidades de melhoria e propor intervenções.

**Contexto:** a Olist é uma empresa brasileira que conecta pequenos vendedores a grandes marketplaces. O vendedor anuncia pela Olist e envia o produto diretamente ao cliente.

## Pergunta norteadora

> Como os atrasos na entrega afetam a satisfação do cliente, e onde a Olist deve agir para reduzi-los?

A pergunta foi definida a partir de um panorama inicial dos dados. Nele, as avaliações ruins (14,7%) e os pedidos atrasados (8,1%) apareceram em proporções parecidas, sugerindo uma possível relação entre eles.

## Principais achados

### Atraso e satisfação

- Pedidos atrasados recebem 54,1% de avaliações ruins (nota 1 ou 2), contra 9,2% dos pedidos no prazo: quase 6 vezes mais.
- O efeito cresce com o tempo de atraso: até 3 dias, 19,2% de avaliações ruins; a partir de 4 dias, mais de 60%.
- Os atrasos são 8,1% dos pedidos, mas geram 33,8% de todas as avaliações ruins.

### Onde o atraso acontece

- O principal gargalo é o transporte: nos pedidos atrasados, essa etapa leva 17,8 dias a mais, contra 2,9 dias a mais na etapa do vendedor.
- Norte e Nordeste têm as maiores taxas de atraso (9,8% e 14,3%) e os maiores tempos de transporte. Os dados indicam relação com a distância: 95% dos vendedores estão no Sudeste e no Sul.
- O Rio de Janeiro é uma exceção: mesmo perto dos vendedores, tem taxa de atraso de 13,5% e concentra 21,3% de todos os atrasos do país.

### Recompra

- Só 2,2% dos clientes voltam a comprar.
- Quem recebeu a primeira compra com atraso volta cerca de 26% menos (1,6% contra 2,2%). A experiência ruim reduz a recompra, mas não explica sozinha por que ela é tão baixa.

### Simulação de impacto

- Se os atrasos fossem contidos em até 3 dias, a Olist teria cerca de 21,8% menos avaliações ruins (aproximadamente 2.674 a menos).

## Propostas de intervenção

As propostas estão em ordem de facilidade de execução.

1. **Agir antes que o atraso passe de 3 dias:** acompanhar pedidos perto da data prevista, priorizar o envio, avisar o cliente e oferecer compensação quando necessário.
2. **Investigar os atrasos no Rio de Janeiro:** analisar transportadoras e rotas no estado.
3. **Cobrar prazo de postagem dos vendedores:** nos pedidos atrasados, o tempo do vendedor dobra.
4. **Melhorar a entrega para o Norte e o Nordeste:** transportadoras regionais e avaliação de um centro de distribuição na região.

## Ressalvas

- Os dados mostram associação, não causa. Dois terços das avaliações ruins vêm de pedidos entregues no prazo, o que indica outras causas não analisadas.
- A distância entre vendedor e cliente foi inferida, não medida diretamente.
- A simulação de impacto é uma estimativa simples, que indica a ordem de grandeza do ganho.
- Os dados cobrem apenas o período de 2016 a 2018.

## Dados

Os dados estão na pasta `files/` deste repositório. São 9 arquivos CSV (pedidos, itens, pagamentos, avaliações, clientes, produtos, vendedores, geolocalização e tradução de categorias).

A base é pública e foi obtida no Kaggle: [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).

## Como executar

É necessário ter o Python 3.11 ou superior instalado.

1. Clone o repositório:

   ```bash
   git clone https://github.com/yasminpecavalcante-droid/fiap_tech_challenge_case_olist.git
   cd fiap_tech_challenge_case_olist
   ```

2. Crie um ambiente virtual e instale as bibliotecas (pandas e matplotlib, além do Jupyter para abrir o notebook):

   **Windows (PowerShell):**

   ```powershell
   python -m venv .venv
   .venv\Scripts\python -m pip install -r requirements.txt
   ```

   **Linux ou macOS:**

   ```bash
   python3 -m venv .venv
   .venv/bin/python -m pip install -r requirements.txt
   ```

3. Abra e execute o notebook `notebooks/tech_challenge_olist.ipynb` de uma das formas abaixo. Ele lê os dados da pasta `files/`, sem necessidade de configurar caminhos.

   **No VS Code** (com as extensões Python e Jupyter):

   1. Abra a pasta do projeto e, em seguida, o notebook.
   2. Clique em **Select Kernel** (ou no nome do Python), no canto superior direito, e escolha **Python Environments → .venv**. Se o `.venv` não aparecer na lista, feche e abra o notebook de novo.
   3. Clique em **Restart** e depois em **Run All**.

   **No Jupyter:**

   1. Inicie o Jupyter com o comando do seu sistema:

      ```powershell
      # Windows (PowerShell)
      .venv\Scripts\python -m jupyter notebook notebooks/tech_challenge_olist.ipynb
      ```

      ```bash
      # Linux ou macOS
      .venv/bin/python -m jupyter notebook notebooks/tech_challenge_olist.ipynb
      ```

   2. Use **Kernel → Restart Kernel and Run All Cells**.

> **Erro `ModuleNotFoundError: No module named 'pandas'`?** O notebook está usando um Python sem as bibliotecas instaladas. Confira se o ambiente selecionado é o `.venv` e execute o notebook novamente.

## Estrutura do repositório

```text
fiap_tech_challenge_case_olist/
├── files/                          # os 9 arquivos CSV da base
├── notebooks/
│   └── tech_challenge_olist.ipynb  # notebook com toda a análise
├── .gitignore                      # arquivos que o Git deve ignorar
├── requirements.txt                # bibliotecas do projeto
└── README.md                       # este arquivo
```

## Estrutura do notebook

| Seção | Conteúdo |
| --- | --- |
| 01. Preparação | Bibliotecas e caminho dos dados |
| 02. Carregamento | Leitura das 9 tabelas |
| 03. Entendimento dos dados | Tipos, nulos, duplicados e granularidade |
| 04. Panorama inicial | Satisfação, regiões, recompra, pagamentos, preços e prazos; escolha da pergunta |
| 05. Preparação dos dados | Tratamento das avaliações e junção das tabelas |
| 06. Análise | Atraso × satisfação, regiões, etapas da entrega, simulação e recompra |
| 07. Conclusões | Resposta à pergunta, propostas de intervenção e ressalvas |

## Integrantes

- Yasmin Pereira Cavalcante
