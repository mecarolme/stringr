Linguagem R - Pacote Stringr
================
caroline medeiros
03/04/2021

<img src="https://d33wubrfki0l68.cloudfront.net/45fd04ad9cdb2159fea08d07dbc11e742d68e4e3/df327/css/images/hex/stringr.png" width="150" />

## Introdução

Variáveis de texto são muito comuns nos bancos de dados e costumam dar
trabalho para serem manipuladas.  
O **R** possui várias funções para manipular esses textos(*strings*). No
entanto, as funções do `R base` não possuem uma interface consistente e
cada uma tem a sua forma de passar os parâmetros, dificultando a
programação.

Pensando nisso, *Hadley Wickham* contribuiu com a comunidade **R** e
criou o pacote **stringr**, que possui uma sintaxe consistente,
permitindo o usuário manipular textos com mais facilidade.

------------------------------------------------------------------------

## Sumário

-   [Como Instalar](#instalação)

-   [O Básico](#conceitos)

-   [Algumas funções](#uso)

-   [Observação](#observação)

------------------------------------------------------------------------

## Instalação

Instale o pacote direto do CRAN:

    install.packages("stringr")

Ou, baixe a versão em desenvolvimento direto do GitHub:  
*Se certifique de ter o “devtools” instalado.*

    install.packages ("devtools")

    devtools :: install_github ( " tidyverse / stringr " )

Então, execute o pacote para usá-lo.

``` r
library(stringr)
```

------------------------------------------------------------------------

## Conceitos

-   As funções de manipulação de texto começam com `str_`.  
-   Caso esqueça o nome de uma função, basta digitar `stringr::str_` e
    apertar **TAB** para ver quais são as opções.  
-   O primeiro argumento da função é sempre uma *string* ou um vetor de
    *strings*.

#### Algumas vantagens do stringr em relação às funções do *R base*

-   Sintaxe unificada, o que auxilia na memorização das funções e
    leitura do código.  
-   Todas as funções são vetorizadas.  
-   Construído sobre a *ICU C library*, implementada em C e C++, uma
    garantia de resultados mais rápidos.

------------------------------------------------------------------------

## Uso

### str\_length()

Esta função recebe como argumento um vetor de *strings* e retorna o
número de caracteres de cada *string*.

``` r
str_length("São Paulo")
```

    ## [1] 9

### str\_to\_upper / str\_to\_lower / str\_to\_title

Essas servem para modificar a caixa das letras.

    s <- "Eu sou legal-r"           

    str_to_upper(s)
    ## [1] "EU SOU LEGAL-R"

    str_to_lower(s)
    ## [1] "eu sou legal-r"

    str_to_title(s)
    ## [1] "Eu Sou Legal-R"

### str\_c

Semelhante a função `paste0()` do `R base`, une *strings* em uma única
*string*.

    string1 <- "O valor p é: "
    string2 <- 0.03

    str_c(string1, string2) 

### str\_trim

> É comum encontrar textos com espaços a mais, principalmente em
> formulários em que cada usuário escreve da forma que quer. Isso se
> torna um problema pois cria categorias diferentes para valores que
> deveriam ser iguais.

A função `str_trim` ajuda excluindo os espaços a mais.

    s <- c("M", "F", "F", " M", " F ", "M")
    as.factor(s)
    ## [1] M   F   F    M   F  M  
    ## Levels:  F   M F M

    string_aparada <- str_trim(s)
    as.factor(string_aparada)
    ## [1] M F F M F M
    ## Levels: F M

------------------------------------------------------------------------

## Observação

**stringr** é construído sobre *stringi* , que usa a biblioteca *ICU C*
para fornecer implementações corretas e rápidas de manipulações comuns
de strings.

-   **stringr** concentra-se nas funções de manipulação de string mais
    importantes e comumente usadas;

-   enquanto *stringi* fornece um conjunto abrangente que cobre quase
    tudo que você possa imaginar.

Se você descobrir que está faltando uma função necessária em
**stringr**, tente procurar em *stringi*. Ambos os pacotes compartilham
convenções semelhantes, portanto, depois de dominar o **stringr**, você
deverá achar o *stringi* igualmente fácil de usar.

**Para mais informações sobre os pacotes citados:**  
- [stringr](https://stringr.tidyverse.org/)  
- [stringi](https://stringi.gagolewski.com/)
