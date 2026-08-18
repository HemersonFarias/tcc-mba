# Painel de acompanhamento de projetos de análise de dados

Artefato do meu TCC no MBA em Gestão de Projetos e Metodologias Ágeis (PUCRS Online), 2026.

Painel online: https://dashboard-gestao-de-projetos-mba.vercel.app

## O que é

Um painel para acompanhar projetos de construção de dashboards. A ideia central é que contar entregáveis concluídos não diz muito, porque um painel simples e um painel complexo contam igual. Aqui o progresso também é medido por esforço, estimado em escala Fibonacci (1, 2, 3, 5, 8, 13).

O painel tem duas partes: uma com os números do contrato (meta, progresso, previsão de término, SPI) e outra com o fluxo do trabalho (funil, lead time, CFD, throughput, bloqueios, itens parados, ciclos de validação).

Os dados são fictícios, criados só para demonstrar o painel. Não há informação real de nenhuma empresa.

## Arquivos

- `dashboard_gestao_projetos.html` — o painel, em arquivo único
- `dataset.csv` — 100 entregáveis fictícios em 10 áreas de negócio

## Como rodar

Pelo link acima, ou localmente:

```bash
git clone https://github.com/HemersonFarias/tcc-mba.git
cd tcc-mba
python3 -m http.server 8000
```

Depois abra http://localhost:8000/dashboard_gestao_projetos.html

Se abrir o HTML direto no navegador, o CSV não carrega sozinho (restrição do próprio navegador). Nesse caso o painel usa os dados embutidos e mostra um botão para escolher o arquivo manualmente.

## Colunas do CSV

Separador é ponto e vírgula.

`id` · identificador do entregável
`tema` · área de negócio
`nome` · nome do dashboard
`pontos` · esforço em Fibonacci (1, 2, 3, 5, 8, 13)
`status` · backlog, bloqueado, execucao, qa, valcliente ou finalizado
`dataBacklog`, `dataExecucao`, `dataQA`, `dataValCliente`, `dataFinalizado` · datas de entrada em cada etapa
`bloqueadoDesde` e `motivoBloqueio` · quando o item está travado
`ciclosValidacao` · quantas rodadas de validação até aprovar
`dadosProntos` · se a fonte de dados já está disponível

Para usar com seus dados, troque o conteúdo do CSV mantendo os nomes das colunas. Os indicadores recalculam sozinhos.

## Tecnologia

HTML, CSS e JavaScript, com Chart.js para os gráficos. Sem framework e sem build. Os cálculos rodam no navegador.

## Licença

MIT.

## Citação

FARIAS DA SILVA, H. Painel de acompanhamento de projetos híbridos de análise de dados. 2026. Disponível em: https://github.com/HemersonFarias/tcc-mba
