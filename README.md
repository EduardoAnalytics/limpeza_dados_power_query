# Limpeza de Arquivos SAP no Power BI usando Linguagem M
  Este projeto aborda um cenário comum em consultorias que utilizam Power BI: a ingestão e o tratamento de arquivos exportados do SAP, recebidos via e-mail e armazenados no SharePoint. O foco está na limpeza e padronização dos dados utilizando Power Query e a linguagem   M, antes do carregamento no modelo de dados.

---

# 💼 Contexto
Em muitos projetos de BI, especialmente em consultorias, é comum que o analista atue além da visualização, sendo responsável também pelas etapas de ETL, principalmente em cenários onde não há suporte de um time de engenharia de dados. Foi exatamente o que ocorreu neste caso.

O cliente utilizava o SAP para exportação diária de arquivos .txt, que eram enviados via Power Automate para um repositório no SharePoint. Esses arquivos alimentavam uma tabela fato utilizada em diversos dashboards.

---

## ⚠️ Problemas encontrados
Os arquivos apresentavam problemas recorrentes que impactavam diretamente o relacionamento entre tabelas e a performance do modelo:

Espaços em branco no início e no fim dos textos;

Linhas completamente vazias;

Colunas 100% em branco.

Esses problemas exigiam retrabalho frequente e comprometiam a confiabilidade do modelo.

# Exemplo:

![image](https://github.com/user-attachments/assets/6b253370-18a2-474f-b591-b1efb1185553)


---

## 🛠️ Solução aplicada
Após estudar a linguagem M com mais profundidade, elaborei um script de limpeza automatizada no Power Query, utilizando as seguintes práticas:

Remoção de linhas em branco:
Uso de List.IsEmpty e List.RemoveMatchingItems para filtrar linhas vazias.

Limpeza de textos:
Aplicação de Text.Clean(Text.Trim(_)) para remover espaços em branco e caracteres ocultos.

Remoção de colunas vazias:
Identificação e exclusão de colunas cujo conteúdo era 100% nulo.

Padronização em todas as colunas de texto:
Uso de Text.Trim em todas as colunas do tipo texto para garantir consistência.

![image](https://github.com/user-attachments/assets/1e9ccfdc-2d86-49b0-89b6-4375c0c41eba)


---

## ✅ Resultados
Com o script implementado, foi possível:

Eliminar retrabalhos relacionados à limpeza manual;

Garantir a consistência dos relacionamentos entre tabelas;

Melhorar a performance e qualidade do modelo de dados.

---

## 💡 Conclusão
Nem sempre teremos à disposição um ambiente ideal ou infraestrutura de dados robusta. Compreender o potencial da linguagem M e aplicar boas práticas no Power Query pode fazer toda a diferença na entrega de soluções escaláveis e confiáveis no Power BI.

![image](https://github.com/user-attachments/assets/18969cf0-a118-4fb7-b134-293105b381de)



