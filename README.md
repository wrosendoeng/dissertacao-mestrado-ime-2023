# Dissertação de Mestrado - IME 2023

Este é o modelo LaTex de dissertação de pós-graduação do Instituto Militar de Engenharia para o Programa de Pós-Graduação em Engenharia Mecânica.

Os objetivos deste trabalho são:

- Estudar a aerodinâmica de um projetil de calibre 155mm para desenvolver simulações CFD
- Predizer a trajetória da munição para criar tabelas de tiro.

## Capítulos

O trabalho possui 8 capítulos, onde cada 1 se encontra em uma pasta junto de suas imagens, quando houver.

Se quiser usar o citação alfabética, e.g. (MOREIRA et al., 2019), procure e alterne o comentário do seguinte trecho do arquivo *main.tex*.

```
De:
\usepackage[num,abnt-etal-list=0,bibjustif]{./abntex2cite} % Citações numéricas (ordem de apresentação)
%\usepackage[alf,abnt-etal-list=0,bibjustif]{./abntex2cite} % Citações autor-data (ordem alfabética)

Para:
%\usepackage[num,abnt-etal-list=0,bibjustif]{./abntex2cite} % Citações numéricas (ordem de apresentação)
\usepackage[alf,abnt-etal-list=0,bibjustif]{./abntex2cite} % Citações autor-data (ordem alfabética)
```

## Criar e remover arquivos de conteúdo

Arquivos podem ser incluídos no documento com o comando *\input{}*

```
\input{nome-do-arquivo_sem-tex}
```

Se o seu arquivo se chama resultados.tex, então:

```
\input{resultados}
```

Para remover os arquivos de exemplo do seu documento procure pelas linhas abaixo no arquivo *main.tex*.

```
\input{exemplo-intro}
\input{exemplo-cap-01}
\input{exemplo-cap-02}
\input{exemplo-conclusao}
...
\input{exemplo-apendice}
...
\input{exemplo-anexo}
```

Tenha cuidado para adicionar os elementos textuais, o apendice e o anexo nos locais onde estão no arquivo *main.tex*, pois a ordem e o local onde aparecem influi no documento final gerado.

## Outras informações

Mais informações podem ser encontradas em https://www.abntex.net.br/

# Perguntas Frequentes

### Como usar referências com nome e ano do autor (referência alfabética)

Veja a seção **Citações** acima.

### Uso de citações em legendas (figuras, quadros ou tabelas)

O sistema alfa-numério de citação, lista as referências na ordem que elas aparecem no texto. Quando você cita uma referência em uma legenda, ela aparece fora de ordem no lista de referências, pois a citação aparecerá primeiro no sumário e, portanto, antes de outras citações do corpo do texto. Para evitar isso, coloque o texto do sumário diferente do texto do documento no comando _**caption**_ (sem a referência).

```
\begin{figure}[!ht]
	\centering
	\includegraphics[opções]{imagem}
	\caption[Legenda dessa figura.]{Legenda dessa figura \cite{ALGUMA REFÊRENCIA}.}
	\label{fig:MANET STACK}
\end{figure}
```
