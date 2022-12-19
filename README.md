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

O problema envolve um regime turbulento, logo são apresentadas possíveis abordagens para descrever a turbulência ao resolver as equações de governo (Navier-Stokes). Como o foco é se aprofundar nos modelos RANS, o problema de fechamento será tratado, seja para os casos incompressíveis ou compressíveis. Os modelos RANS tratados serão o Spalart-Allmaras (SPALART,P.R. and ALLMARAS, S.R.,1994), $\kappa-\epsilon$ padrão (JONES, W.P and LAUNDER, B.E., 1972; LAUNDER, B.E and SHARMA, B.I.,1974), $\kappa-\omega$ padrão (WILCOX, D.C., 1988) e *Shear-Stress Transport* (SST) $\kappa-\omega$ (MENTER, F.L, 1994).

### Capítulo 05 - Modelagem de Trajetória

O modelo de trajetória implementado será o Modelo de Trajetória Ponto-Material (ou Ponto-Massa) Modificado (de sigla MPMTM, que vem do inglês *Modified Point-Mass Trajectory Model*), que foi deduzido na década de 60 (LIESKE, R.F. and REITER, M.L., 1966) e aprimorado (BARANOWSKI, L., 2013b). Neste modelo considera-se 3 graus de translação e apenas 1 para rotação, conhecido como *guinada de repouso*, cuja aplicação é restrita aos projetis axissimétricos estabilizados por rotação. Atualmente é padronizado pela OTAN através da norma STANAG 4355 (OTAN, 2009). Também é tratado neste capítulo os efeitos causados pela atmosfera e o método numérico implementado para predizer o voo da munição 155mm.

### Capítulo 06 - Descrição do Estudo Proposto

A descrição do estudo serve para orientar como se conceberam os resultados, sejam elas as simulações CFD ou as predições de trajetória. São descritos os modelos de turbulência utilizados, a construção do domínio computacional e as condições de contorno para resolver numericamente o escoamento no entorno do projetil, com ou sem *Base Bleed*. Acerca da trajetória, são relatadas as condições aerodinâmicas, ambientais, atmosféricas e balísticas.

### Capítulo 07 - Resultados

Os resultados das simulações CFD são observados inicialmente a partir de testes de convergência de malha sem *Base Bleed*; depois computando com *Base Bleed* a partir da variação dos seguintes parâmetros: diâmetro de saída; vazão mássica de injeção, temperatura e modelos RANS. Por fim, os resultados são acoplados ao modelo de trajetória para atestar o desempenho.

### Capítulo 08 - Considerações Finais

No último capítulo são inseridas as considerações finais, bem como as conclusões e sugestões para futuros trabalhos.

## Criar e remover arquivos de conteúdo

Arquivos podem ser incluídos no documento com o comando *\input{}*

```
\input{nome-do-arquivo_sem-tex}
```

ou se quiser usar o comando *\include{}*

```
\include{nome-do-arquivo_sem-tex}
```

Se o seu arquivo se chama resultados.tex, então:

```
\input{resultados}
\include{resultados}
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

### Referências

Nesta parte a bibliografia é inserida. Com o compilador de bibliografias *BibTeX*, basta criar um arquivo *.bib* e escrever no arquivo *main.tex* (antes dos apêndices)

```
\bibliography{arquivo-bibliografia_sem_ponto_bib}
```

### Apêndices

Os apêndices ao fim servem apenas para inserir as tabelas com os coeficientes aerodinâmicos necessários para modelar a trajetória. Sugiro escrever o apêndice como um arquivo *.tex* (nome-do-apendice.tex) 

```
\begin{apendicesenv}
    \partapendices
    \include{nome-do-apendice_sem_ponto_tex}
\end{apendicesenv}
```

ou se preferir com o comando \input{}:

```
\begin{apendicesenv}
    \partapendices
    \input{nome-do-apendice_sem_ponto_tex}
\end{apendicesenv}
```

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
