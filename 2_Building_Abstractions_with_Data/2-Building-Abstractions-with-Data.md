2 Construindo Abstrações com Dados

> Agora chegamos à etapa decisiva da abstração matemática: esquecemos o que os símbolos representam. … [O matemático] não precisa ficar ocioso; há muitas operações que ele pode realizar com esses símbolos, sem nunca ter que olhar para as coisas que eles representam.
>
> Hermann Weyl A maneira matemática de pensar

Concentramos no capítulo 1 os processos computacionais e o papel das funções no projeto do programa. Vimos como usar dados primitivos (números) e operações primitivas (operações aritméticas), como combinar funções para formar funções compostas por meio de composição, condicionais e o uso de parâmetros e como abstrair processos usando declarações de função. Vimos que uma função pode ser considerada um padrão para a evolução local de um processo e classificamos, raciocinamos e realizamos análises algorítmicas simples de alguns padrões comuns para processos incorporados em funções. Também vimos que as funções de ordem superior aumentam o poder de nossa linguagem, permitindo-nos manipular e, portanto, raciocinar em termos de métodos gerais de computação. Isso é muito da essência da programação.

Neste capítulo, veremos dados mais complexos. Todas as funções no capítulo 1 operam com dados numéricos simples, e dados simples não são suficientes para muitos dos problemas que desejamos abordar usando computação. Os programas são normalmente projetados para modelar fenômenos complexos e, na maioria das vezes, é necessário construir objetos computacionais que tenham várias partes para modelar fenômenos do mundo real que tenham vários aspectos. Assim, enquanto nosso foco no capítulo 1 era construir abstrações combinando funções para formar funções compostas, voltamos neste capítulo para outro aspecto-chave de qualquer linguagem de programação: os meios que ela fornece para construir abstrações combinando objetos de dados para formar _dados compostos_ .

Por que queremos dados compostos em uma linguagem de programação? Pelas mesmas razões pelas quais queremos funções compostas: elevar o nível conceitual em que podemos projetar nossos programas, aumentar a modularidade de nossos projetos e aumentar o poder expressivo de nossa linguagem. Assim como a capacidade de declarar funções nos permite lidar com processos em um nível conceitual mais alto do que o das operações primitivas da linguagem, a capacidade de construir objetos de dados compostos nos permite lidar com dados em um nível conceitual mais alto do que o do objetos de dados primitivos da linguagem.

Considere a tarefa de projetar um sistema para realizar aritmética com números racionais. Poderíamos imaginar uma operação add*ratque pega dois números racionais e produz sua soma. Em termos de dados simples, um número racional pode ser considerado como dois inteiros: um numerador e um denominador. Assim, poderíamos projetar um programa em que cada número racional seria representado por dois inteiros (um numerador e um denominador) e ondeadd_ratseria implementado por duas funções (uma produzindo o numerador da soma e outra produzindo o denominador). Mas isso seria estranho, porque precisaríamos acompanhar explicitamente quais numeradores correspondem a quais denominadores. Em um sistema destinado a realizar muitas operações em muitos números racionais, esses detalhes contábeis desordenariam os programas substancialmente, para não falar do que fariam com nossas mentes. Seria muito melhor se pudéssemos cola junto um numerador e denominador para formar um par - um \_objeto de dados composto* - que nossos programas poderiam manipular de uma forma que seria consistente com a consideração de um número racional como uma unidade conceitual única.

O uso de dados compostos também nos permite aumentar a modularidade de nossos programas. Se pudermos manipular números racionais diretamente como objetos em seu próprio direito, então podemos separar a parte de nosso programa que lida com números racionais per se dos detalhes de como os números racionais podem ser representados como pares de inteiros. A técnica geral de isolar as partes de um programa que tratam de como os objetos de dados são representados das partes de um programa que tratam de como os objetos de dados são usados ​​é uma metodologia de design poderosa chamada _abstração de dados_ . Veremos como a abstração de dados torna os programas muito mais fáceis de projetar, manter e modificar.

O uso de dados compostos leva a um aumento real no poder expressivo de nossa linguagem de programação. Considere a ideia de formar um combinação linear a x + b y

. Gostaríamos de escrever uma função que aceitariauma, b, x, e y como argumentos e retorna o valor de a x + b y

. Isso não apresenta dificuldade se os argumentos forem números, porque podemos declarar prontamente a função

função linear_combination ( a , b , x , y ) { return a _ x + b _ y ; }

Mas suponha que não estamos preocupados apenas com números. Suponha que gostaríamos de descrever um processo que forma combinações lineares sempre que adição e multiplicação são definidas - para números racionais, números complexos, polinômios ou o que quer que seja. Poderíamos expressar isso como uma função da forma

função linear_combination ( a , b , x , y ) { return add ( mul ( a , x ), mul ( b , y )); }

onde adde mulnão são as funções primitivas +e \*mas as coisas um pouco mais complexas que irão realizar as operações apropriadas para quaisquer tipos de dados que passam em como os argumentos a, b, x, e y. O ponto-chave é que a única coisa que linear_combinationdeve precisar de saber sobre a, b, x, e yé que as funções adde mulirá executar as manipulações apropriadas. Do ponto de vista da função linear_combination, é irrelevante que a, b, x, e ysão e ainda mais irrelevantes como podem ser representados em termos de dados mais primitivos. Este mesmo exemplo mostra por que é importante que nossa linguagem de programação forneça a capacidade de manipular objetos compostos diretamente: Sem isso, não há como uma função linear_combinationpassar seus argumentos adiante adde mulsem precisar conhecer sua estrutura detalhada. [[1]](https://so45nujb3h4koud7nsjm2lne4u-ac4c6men2g7xr2a-github.translate.goog/sicp/chapters/2.html#footnote-1)

Começamos este capítulo implementando o sistema aritmético de números racionais mencionado acima. Isso formará o pano de fundo para nossa discussão sobre dados compostos e abstração de dados. Tal como acontece com as funções compostas, a principal questão a ser tratada é a abstração como uma técnica para lidar com a complexidade, e veremos como a abstração de dados nos permite erguer _barreiras de abstração_ adequadas entre as diferentes partes de um programa.

Veremos que a chave para formar dados compostos é que uma linguagem de programação deve fornecer algum tipo de Cola para que os objetos de dados possam ser combinados para formar objetos de dados mais complexos. Existem muitos tipos de cola possíveis. Na verdade, vamos descobrir como formar dados compostos sem usar dados operações em tudo, apenas funções. Isso confundirá ainda mais a distinção entre função e dados, que já estava se tornando tênue no final do capítulo 1. Também exploraremos algumas técnicas convencionais para representar sequências e árvores. Uma ideia-chave ao lidar com dados compostos é a noção de _fechamento_ - que a cola que usamos para combinar objetos de dados deve nos permitir combinar não apenas objetos de dados primitivos, mas também objetos de dados compostos. Outra ideia-chave é que os objetos de dados compostos podem servir como _interfaces convencionais_ para combinar os módulos do programa de maneiras combinadas. Ilustramos algumas dessas idéias apresentando uma linguagem gráfica simples que explora o fechamento.

Em seguida, aumentaremos o poder de representação de nossa linguagem introduzindo _expressões simbólicas -_ dados cujas partes elementares podem ser símbolos arbitrários em vez de apenas números. Exploramos várias alternativas para representar conjuntos de objetos. Veremos que, assim como uma determinada função numérica pode ser calculada por muitos processos computacionais diferentes, há muitas maneiras pelas quais uma determinada estrutura de dados pode ser representada em termos de objetos mais simples, e a escolha da representação pode ter um impacto significativo sobre o requisitos de tempo e espaço dos processos que manipulam os dados. Investigaremos essas idéias no contexto da diferenciação simbólica, da representação de conjuntos e da codificação da informação.

A seguir, abordaremos o problema de trabalhar com dados que podem ser representados de maneira diferente por diferentes partes de um programa. Isso leva à necessidade de implementar _operações genéricas_ , que devem lidar com muitos tipos diferentes de dados. Manter a modularidade na presença de operações genéricas requer barreiras de abstração mais poderosas do que podem ser erguidas apenas com a abstração de dados simples. Em particular, apresentamos _a programação direcionada a dados_ como uma técnica que permite que representações de dados individuais sejam projetadas isoladamente e, em seguida, combinadas _aditivamente_(ou seja, sem modificação). Para ilustrar o poder dessa abordagem para o projeto de sistema, fechamos o capítulo aplicando o que aprendemos à implementação de um pacote para realizar aritmética simbólica em polinômios, em que os coeficientes dos polinômios podem ser inteiros, números racionais, números complexos , e até mesmo outros polinômios.

---

[[1]](https://so45nujb3h4koud7nsjm2lne4u-ac4c6men2g7xr2a-github.translate.goog/sicp/chapters/2.html#footnote-link-1) A capacidade de manipular funções diretamente fornece um aumento análogo no poder expressivo de uma linguagem de programação. Por exemplo, na seção [1.3.1](https://so45nujb3h4koud7nsjm2lne4u-ac4c6men2g7xr2a-github.translate.goog/sicp/chapters/1.3.1.html) introduzimos a sumfunção, que recebe uma função termcomo argumento e calcula a soma dos valores de termalgum intervalo especificado. Para definir sum, é crucial que possamos falar de uma função termcomo uma entidade por si mesma, sem levar em conta como ela termpode ser expressa com operações mais primitivas. Na verdade, se não tivéssemos a noção de uma função, é duvidoso que algum dia pensemos na possibilidade de definir uma operação como sum. Além disso, no que diz respeito à realização da soma, os detalhes de como termpodem ser construídos a partir de operações mais primitivas são irrelevantes.