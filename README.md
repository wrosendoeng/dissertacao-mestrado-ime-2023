# Dissertação de Mestrado - IME 2023

Este é o modelo LaTex de dissertação de pós-graduação do Instituto Militar de Engenharia para o Programa de Pós-Graduação em Engenharia Mecânica.

Os objetivos deste trabalho são:

- Estudar a aerodinâmica de um projetil de calibre 155mm para desenvolver simulações CFD
- Predizer a trajetória da munição para criar tabelas de tiro.

## Capítulos

O trabalho possui 8 capítulos, onde cada 1 se encontra em uma pasta junto de suas imagens, quando houver.

O formato das referências bibliográficas é baseado em ordenação numérica de citação, o que é permitido pela ABNT. Caso queira usar o citação alfabética, e.g. (MOREIRA et al., 2019), procure e alterne o comentário do seguinte trecho do arquivo *main.tex*.

```
De:
\usepackage[num,abnt-etal-list=0,bibjustif]{./abntex2cite} % Citações numéricas (ordem de apresentação)
%\usepackage[alf,abnt-etal-list=0,bibjustif]{./abntex2cite} % Citações autor-data (ordem alfabética)

Para:
%\usepackage[num,abnt-etal-list=0,bibjustif]{./abntex2cite} % Citações numéricas (ordem de apresentação)
\usepackage[alf,abnt-etal-list=0,bibjustif]{./abntex2cite} % Citações autor-data (ordem alfabética)
```

### Capítulo 01 - Introdução

Neste capítulo o foco é desenvolver a revisão bibliográfica, além de explicar a motivação e o objetivo do estudo. Por fim, há uma seção somente para explicar o roteiro do trabalho para orientar a leitura a parte interessada.

### Capítulo 02 - Revisão Teórica

A revisão teórica concentra uma revisão sobre escoamentos compressíveis e descrever as equações de Navier-Stokes para um regime compressível e estacionário.

### Capítulo 03 - Métodos Numéricos

Nesta parte o objetivo é apresentar possíveis abordagens de discretização, com ênfase no Método dos Volumes Finitos (MVF). Também são apresentadas as técnicas que auxiliam a resolução deste método.

### Capítulo 04 - Modelagem da Turbulência

O problema envolve um regime turbulento, logo são apresentadas possíveis abordagens para descrever a turbulência ao resolver as equações de governo (Navier-Stokes). Como o foco é se aprofundar nos modelos RANS, o problema de fechamento será tratado, seja para os casos incompressíveis ou compressíveis. Os modelos RANS tratados serão o Spalart-Allmaras, $\kappa-\epsilon$ padrão, $\kappa-\omega$ padrão e *Shear-Stress Transport* (SST) \kappa-\omega.

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
