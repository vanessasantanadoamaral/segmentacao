# Segmentação de clientes
Projeto de análise de dados e segmentação de clientes da loja "O Mercado".

<details>
  <summary><strong style="font-size: 16px;">Equipe</strong></summary>
  Vanessa Santana do Amaral
  </details>
  
<details>
  <summary><strong style="font-size: 16px;">Objetivo</strong></summary>
Realizar uma análise descritiva e segmentação de clientes da loja O Mercado, especializada em produtos alimentícios importados, utilizando a metodologia RFM (Recência, Frequência e Valor Monetário). O objetivo é entender melhor o perfil dos consumidores, identificar padrões de comportamento e apoiar a tomada de decisões estratégicas de marketing, fidelização e crescimento, por meio de dashboards interativos no Google Sheets e Looker Studio.
</details>

<details>
  <summary><strong style="font-size: 16px;">Ferramentas e tecnologias</strong></summary>
Google Sheets para coleta e segmentação dos dados, Looker Studio para criação dos dashboards interativos, Google Slides para a apresentação, Google Documents para a documentação e ficha técnica, Trello e Miro para gestão do projeto e Loom para gravação da apresentação final.
</details>

<details>
  <summary><strong style="font-size: 16px;">Processamento e análises</strong></summary>
A primeira etapa do trabalho consistiu na limpeza e tratamento dos dados. Foram utilizadas as funções QUERY e IMPORTRANGE para consolidar as tabelas e duplicar os dados, evitando a perda de históricos. Também foi realizada a tradução e padronização de expressões, além da correção de formatações.
  
&nbsp;  
Durante a análise, optou-se pela exclusão de clientes com idade superior a 120 anos e transações sem ID, por entender que esses registros não representam clientes ativos. Para os casos em que não havia informação sobre o salário, mas os demais dados cadastrais estavam completos, foram atribuídos valores estimados com base na média salarial por nível de escolaridade.
Foram criadas novas variáveis, como faixa etária, total de filhos, número de compras em loja e online, separação de compras por trimestre, entre outras, utilizando funções como COUNTBLANK, INDEX MATCH, IF, IFS, VLOOKUP, CONCATENATE, SUM, MÉDIA, MÁX, DATADIF. Aplicou-se formatação condicional para identificar duplicatas, o que possibilitou a remoção de mais de 15 mil registros repetidos. 

Antes de integrar as tabelas “clientes”, “transações” e “resumo_compras” em um “consolidado_final” por meio da função INDEX MATCH, foi necessário garantir o tratamento completo de dados nulos, duplicados e também a exclusão de clientes sem transações, de forma a não comprometer a segmentação. Em seguida, os dados foram organizados em tabelas dinâmicas e foram criados gráficos simples para visualização e com o objetivo de compreender melhor os perfis dos clientes.

Com os gráficos finalizados, iniciou-se a etapa de análise dos dados. A função DATADIF foi usada para calcular a recência, enquanto INDEX MATCH foi aplicada para calcular a frequência de compras, e SUM para o valor total gasto por cliente (valor monetário). No cálculo de quartis, utilizaram-se as funções IFS e QUARTIL, classificando os clientes com base na recência de suas compras. Com a lógica do RFM (Recência, Frequência, Monetário), foi considerado como critério notas de 1 a 5, conforme os quartis. 
Com isso, foi possível aplicar uma classificação dos clientes com base na fórmula IFS, conforme a seguinte lógica:

- Cliente VIP: Compram com frequência, gastam bastante e são recentes (R=5, F=5, M=5).
- Cliente Leal: Compram regularmente, com bom valor de compra e são relativamente recentes (R ≥ 4, F ≥ 4, M ≥ 4).
- Cliente Novo: Recente, mas ainda com baixo volume e valor de compras (R = 5, F ≤ 2, M ≤ 3).
- Cliente em Risco: Já foram bons clientes, mas estão há muito tempo sem comprar (R ≤ 2, F ≥ 3, M ≥ 4).
- Cliente Perdido: Compram pouco, gastam pouco e estão inativos há bastante tempo (R ≤ 2, F ≤ 2, M ≤ 2).
- Cliente Potencial: Tem desempenho intermediário, com potencial para se tornar VIP (R ≥ 3, F ≥ 3, M ≥ 3).
- Cliente que Precisa de Atenção: Perfil médio, ainda sem destaque, mas com possibilidades de crescimento (R ≥ 2, F ≥ 2, M ≥ 2).
- Sem Classificação: Casos que não se enquadram nas regras anteriores, podendo indicar inconsistências ou valores extremos.

Com os dados tratados, estruturados e os clientes segmentados, finalizou-se a etapa de processamento e visualização, por meio da criação de dashboards no Google Spreadsheets e início da construção no Looker Studio. Isso permitiu apresentar as informações de forma visual, interativa e atualizada, facilitando a análise de perfis, hábitos de consumo e apoiando a definição de estratégias mais assertivas para o negócio.
  
  </details>

  <details>
  <summary><strong style="font-size: 16px;">Resultados e conclusões</strong></summary>
    
O Mercado possui atualmente 2.227 clientes ativos. Dentre esse total, 38% estão na faixa etária de 51 a 64 anos, sendo classificados como clientes de meia idade. A análise do mostra que 58,6% dos clientes demonstram preferência pelas compras realizadas na loja física e os produtos mais consumidos são vinhos e carnes.

Na segmentação realizada, foram identificados três grupos principais: clientes potenciais, clientes leais e clientes que precisam de atenção.
- Clientes potenciais são os que apresentam maior gasto ao longo do ano. A estratégia recomendada para esse grupo é o fortalecimento do vínculo com a marca, incentivando a fidelização e promovendo sua conversão em clientes VIPs. Algumas ações sugeridas incluem: kits exclusivos com desconto, clube de assinatura com brindes e acesso antecipado a lançamentos.
- Clientes leais realizam compras com frequência e mantêm um bom valor de consumo, representando uma base estável e estratégica para o negócio. Para manter o engajamento desse grupo, as sugestões são: realização de eventos exclusivos, premiações ao final do ano e programas de cashback.
- Clientes que precisam de atenção são aqueles que consomem produtos de maior valor agregado, porém com baixa frequência. Para estimular a recompra, recomenda-se o uso de cupons de desconto nos produtos mais consumidos, cashback para compras realizadas em até 30 dias e brindes como forma de incentivo.
  
Além desses grupos, é importante considerar ações específicas para clientes em risco ou clientes perdidos, com foco em campanhas de reativação. Algumas ideias de abordagem incluem: promoções especiais de retorno, cashbacks especiais, sorteios para aqueles que voltarem a comprar e ofertas personalizadas com base no histórico de consumo.
O público jovem adulto (entre 18 e 30 anos) ainda representa uma parcela pequena da base, com apenas 7 clientes, sendo um grupo que pode ser analisado e trabalhado futuramente. 
Dado que a maioria dos clientes é mais conservador e prefere realizar compras presencialmente, recomenda-se a integração de ações digitais com iniciativas no ponto de venda.

</details>

  
