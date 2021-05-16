Agradecimentos

## Agradecimentos pela adaptação de JavaScript

A adaptação do JavaScript foi desenvolvida na National University of Singapore (NUS) para o curso CS1101S. O curso foi co-ministrado durante seis anos e a contar com Low Kok Lim, cujo sólido juízo pedagógico foi fundamental para o sucesso do curso e deste projeto. A equipe de ensino do CS1101S incluiu muitos colegas da Escola de Computação e mais de 200 alunos assistentes de graduação. Seu feedback contínuo nos últimos nove anos nos permitiu resolver incontáveis ​​problemas específicos do JavaScript e remover complicações desnecessárias e ainda reter os recursos essenciais do SICP e do JavaScript.

SICP JS é um projeto de software além de um projeto de livro. Obtivemos as fontes do livro L a T e X dos autores originais em 2008. Uma versão inicial da cadeia de ferramentas SICP JS foi desenvolvida por Liu Hang e refinada por Feng Piaopiao. Chan Ger Hean desenvolveu as ferramentas para a edição impressa, com base nas quais Jolyn Tan desenvolveu as ferramentas para a edição do e-book e He Xinyue e Wang Qian redesenharam as ferramentas para a edição da web atual.

A edição online do SICP JS e CS1101S depende fortemente de um sistema de software chamado _Source Academy_ , e as subinguagens de JavaScript que ele suporta são chamadas de _Source_ . Muitas dezenas de alunos contribuíram para a Source Academy nos últimos seis anos, e o sistema os lista com destaque como Colaboradores. Desde 2020, os alunos do curso NUS CS4215, Implementação de Linguagem de Programação, contribuíram com várias implementações de linguagem de programação que são usadas em SICP JS: A versão simultânea de Fonte usada na seção 3.4 foi desenvolvida por Zhengqun Koo e Jonathan Chan, a implementação preguiçosa usada em a seção 4.2 foi desenvolvida por Jellouli Ahmed, Ian Kendall Duncan, Cruz Jomari Evangelista e Alden Tan, e a implementação não determinística usada na seção 4.3 foi desenvolvida por Arsalan Cheema e Anubhav, e Daryl Tan ajudou a integrar essas implementações na Academia.

Somos gratos a STINT, a Fundação Sueca para Cooperação Internacional em Pesquisa e Ensino Superior, cujo programa sabático conectou Martin e Tobias e permitiu que Tobias trabalhasse como co-professor do CS1101S e participasse do projeto SICP JS.

Por fim, gostaríamos de agradecer o corajoso trabalho do comitê do ECMAScript 2015, liderado por Allen Wirfs-Brock. SICP JS depende muito de declarações constantes e let e expressões lambda, todas adicionadas ao JavaScript com ECMAScript 2015. Essas adições nos permitiram ficar perto do original na apresentação das idéias mais importantes do SICP.

> Martin Henz e Tobias Wrigstad

## Agradecimentos da segunda edição do SICP, 1996

Gostaríamos de agradecer às muitas pessoas que nos ajudaram a desenvolver este livro e este currículo.

Nosso assunto é um claro descendente intelectual de 6.231, um assunto maravilhoso sobre linguística de programação e cálculo lambda ensinado no MIT no final dos anos 1960 por Jack Wozencraft e Arthur Evans, Jr.

Temos uma grande dívida para com Robert Fano, que reorganizou o currículo introdutório do MIT em engenharia elétrica e ciência da computação para enfatizar os princípios do projeto de engenharia. Ele nos levou a dar início a esse empreendimento e escreveu o primeiro conjunto de notas de assunto a partir do qual este livro evoluiu.

Muito do estilo e estética da programação que tentamos ensinar foram desenvolvidos em conjunto com Guy Lewis Steele Jr., que colaborou com Gerald Jay Sussman no desenvolvimento inicial da linguagem Scheme. Além disso, David Turner, Peter Henderson, Dan Friedman, David Wise e Will Clinger nos ensinaram muitas das técnicas da comunidade de programação funcional que aparecem neste livro.

Joel Moses nos ensinou sobre como estruturar grandes sistemas. Sua experiência com o sistema Macsyma para computação simbólica forneceu o insight de que se deve evitar complexidades de controle e se concentrar em organizar os dados para refletir a estrutura real do mundo que está sendo modelado.

Marvin Minsky e Seymour Papert formaram muitas de nossas atitudes sobre programação e seu lugar em nossas vidas intelectuais. Devemos a eles o entendimento de que a computação fornece um meio de expressão para explorar ideias que, de outra forma, seriam complexas demais para serem tratadas com precisão. Eles enfatizam que a capacidade do aluno de escrever e modificar programas fornece um meio poderoso no qual explorar se torna uma atividade natural.

Também concordamos fortemente com Alan Perlis que programar é muito divertido e é melhor tomarmos cuidado para apoiar a alegria de programar. Parte dessa alegria deriva de observar grandes mestres no trabalho. Temos a sorte de ser programadores aprendizes aos pés de Bill Gosper e Richard Greenblatt.

É difícil identificar todas as pessoas que contribuíram para o desenvolvimento do nosso currículo. Agradecemos a todos os palestrantes, instrutores de recitação e tutores que trabalharam conosco nos últimos quinze anos e dedicaram muitas horas extras em nosso assunto, especialmente Bill Siebert, Albert Meyer, Joe Stoy, Randy Davis, Louis Braida, Eric Grimson, Rod Brooks, Lynn Stein e Peter Szolovits. Gostaríamos de agradecer especialmente as excelentes contribuições de ensino de Franklyn Turbak, agora em Wellesley; seu trabalho no ensino de graduação estabeleceu um padrão que todos nós podemos aspirar. Somos gratos a Jerry Saltzer e Jim Miller por nos ajudar a lidar com os mistérios da concorrência, e a Peter Szolovits e David McAllester por suas contribuições para a exposição da avaliação não determinística no capítulo ~ 4.

Muitas pessoas têm feito um esforço significativo para apresentar este material em outras universidades. Algumas das pessoas com quem trabalhamos são Jacob Katzenelson no Technion, Hardy Mayer na Universidade da Califórnia em Irvine, Joe Stoy em Oxford, Elisha Sacks em Purdue e Jan Komorowski na Universidade Norueguesa de Ciência e Tecnologia. Estamos excepcionalmente orgulhosos de nossos colegas que receberam importantes prêmios de ensino por suas adaptações desse assunto em outras universidades, incluindo Kenneth Yip em Yale, Brian Harvey na Universidade da Califórnia em Berkeley e Dan Huttenlocher em Cornell.

Al Moyé providenciou para que ensinássemos esse material aos engenheiros da Hewlett-Packard e para a produção de fitas de vídeo dessas palestras. Gostaríamos de agradecer aos talentosos instrutores - em particular Jim Miller, Bill Siebert e Mike Eisenberg - que desenvolveram cursos de educação continuada incorporando essas fitas e os ensinaram em universidades e indústrias em todo o mundo.

Muitos educadores em outros países realizaram um trabalho significativo na tradução da primeira edição. Michel Briand, Pierre Chamard e André Pic produziram uma edição francesa; Susanne Daniels-Herold produziu uma edição alemã; e Fumio Motoyoshi produziu uma edição japonesa. Não sabemos quem produziu a edição chinesa, mas consideramos uma honra ter sido selecionado como tema de um não autorizado tradução.

É difícil enumerar todas as pessoas que fizeram contribuições técnicas para o desenvolvimento dos sistemas Scheme que usamos para fins de ensino. Além de Guy Steele, os assistentes principais incluíram Chris Hanson, Joe Bowbeer, Jim Miller, Guillermo Rozas e Stephen Adams. Outros que dedicaram um tempo significativo são Richard Stallman, Alan Bawden, Kent Pitman, Jon Taft, Neil Mayle, John Lamping, Gwyn Osnos, Tracy Larrabee, George Carrette, Soma Chaudhuri, Bill Chiarchiaro, Steven Kirsch, Leigh Klotz, Wayne Noss, Todd Cass, Patrick O'Donnell, Kevin Theobald, Daniel Weise, Kenneth Sinclair, Anthony Courtemanche, Henry M. Wu, Andrew Berlin e Ruth Shyu.

Além da implementação do MIT, gostaríamos de agradecer às muitas pessoas que trabalharam no padrão IEEE Scheme, incluindo William Clinger e Jonathan Rees, que editaram o R $ ^ 4 $ RS, e Chris Haynes, David Bartley, Chris Hanson e Jim Miller, que preparou o padrão IEEE. 4

RS e Chris Haynes, David Bartley, Chris Hanson e Jim Miller, que prepararam o padrão IEEE.

Dan Friedman é um líder de longa data da comunidade Scheme. O trabalho mais amplo da comunidade vai além das questões de design de linguagem para abranger inovações educacionais significativas, como o currículo do ensino médio baseado no EdScheme da Schemer's Inc. e os livros maravilhosos de Mike Eisenberg e de Brian Harvey e Matthew Wright.

Agradecemos o trabalho daqueles que contribuíram para tornar este um livro real, especialmente Terry Ehling, Larry Cohen e Paul Bethge na MIT Press. Ella Mazel encontrou a maravilhosa imagem da capa. Para a segunda edição, somos particularmente gratos a Bernard e Ella Mazel pela ajuda com o design do livro, e a David Jones, extraordinário mago do T e X. Também somos gratos aos leitores que fizeram comentários penetrantes sobre o novo rascunho: Jacob Katzenelson, Hardy Mayer, Jim Miller e especialmente Brian Harvey, que fez para este livro como Julie fez para seu livro _Simply Scheme_ .

Finalmente, gostaríamos de agradecer o apoio das organizações que têm incentivado este trabalho ao longo dos anos, incluindo o apoio da Hewlett-Packard, possibilitado por Ira Goldstein e Joel Birnbaum, e o apoio da DARPA, possibilitado por Bob Kahn.

> Harold Abelson e Gerald Jay Sussman
