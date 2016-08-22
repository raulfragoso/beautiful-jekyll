---
layout: post
title:  "Minhas Primeiras Colisões"
date:   2013-03-04 13:50:44 -0300
categories: waterdrops
---
Continuando com a série de artigos sobre water drops, conforme havia mencionado no final do [artigo anterior](https://raulfragoso.github.io/waterdrops/2013-02-07-esculpindo-2/ "Esculpindo a água – parte 2"), eu estava considerando a aquisição de novos equipamentos para continuar a evoluir nesse tipo de fotografia. Acabei cedendo e resolvi investir em uma válvula solenóide e num controlador mais versátil. Então esta semana, para minha alegria, o bom e velho amigo entregador dos Correios me presenteou com uma caixa contendo um controlador Camera Axe e uma válvula solenóide.

Apesar da minha euforia para começar a usar o equipamento o mais rápido possível, eu sabia que iria precisar de uma estrutura mais resistente para o conjunto do sifão e a válvula, pois não é tão leve quanto eu imaginava. Portanto fiz uma visita a um dos meus locais favoritos, uma casa de material para construção, e comprei uma barra de 6 metros de cano PVC para esgoto de 40mm. Pedi para que serrassem em partes iguais de 1 metro cada, pois não precisaria de pedaços maiores que isso para a montagem, e também para facilitar no transporte, além de comprar cotovelos e conexões do tip “T” para a montagem da estrutura. Comprei também algumas presilhas de aço e parafusos para fixar o sifão da válvula. A nova estrutura ficou assim:

![](https://lh6.googleusercontent.com/-qUSa5hEV02I/UTPlsmYADUI/AAAAAAAAEMg/DnPlqyPWzB4/s800/ca1.jpg)

E abaixo o detalhe da válvula solenóide e do circuito que a controla. Ele é alimentado por duas baterias de 9v. A conexão do tipo P2 (3.5mm) é para o cabo que vai na porta de sensores do Camera Axe.

![](https://lh4.googleusercontent.com/-vp5FyvMNf_I/UTQTg2noHAI/AAAAAAAAENI/669xgW5npYw/s800/IMG_5680.jpg)

E falando no [Camera Axe](http://www.cameraaxe.com/ "Camera Axe"), fiquei realmente impressionado com este controlador. Ele é muito mais versátil que o Triggertrap, pois possui duas portas para câmeras/flashes e mais duas portas para os sensores. Apesar do Triggertrap já vir com muitos sensores embutidos, diferente do Camera Axe, que necessita a compra/montagem de sensores à parte, a flexibilidade de poder trabalhar com portas independentes ou mesmo ligadas em série é bem bacana. Além disso o LCD é maior e possui iluminação, e o case é de melhor qualidade também. Assim como o Triggertrap, ele é baseado na plataforma Arduino, e o software que o controla é open-source e muito bem documentado, o que facilita modificações e customizações.

Com a estrutura já montada, o sifão e válvula fixados no lugar, o software do Camera Axe atualizado para a última versão, era hora de começar a brincar com os brinquedos novos :smiley:  Utilizei uma placa de acrílico branca na parte de trás da estrutura para servir de rebatedor para o flash (ainda está difícil trabalhar com um flash apenas, eu já encomendei duas unidades dos flashes Yongnuo YN-560 II, mas ainda não chegaram). Eu estava ansioso para fazer minhas primeiras fotos de colisão de gotas, que se dão pela colisão entre o retorno de uma primeira gota (ela literalmente ‘quica’ na água e forma uma coluna vertical) com uma segunda gota que cai logo em seguida, gerando formas muito interessantes. Eu também colori a água da válvula com anelina vermelha e também misturei meia colher de chá de [goma guar](http://pt.wikipedia.org/wiki/Goma_guar), para atuar como espessante. A água do recipiente abaixo da válvula eu misturei com um pouco de leite, para deixar o líquido mais viscoso e também tirar um pouco do reflexo da água, e colori com anelina verde. Com tudo pronto, era hora de começar a calcular todos os dados que iria precisar.

O Camera Axe com a válvula solenóide ajudam muito nessa hora, pois pode-se controlar o disparo das gotas com precisão de milissegundos. O bacana do Camera Axe é que dá para conectar a câmera na porta 1, colocar a câmera em modo Bulb e então configurar o software para controlar a abertura do obturador da câmera, a abertura da válvula solenóide, o disparo dos flashes e finalmente o fechamento do obturador da câmera. Todo o processo foi feito no meu escritório, com a janela fechada e a luz ambiente sendo a mínima possível.

O processo para fazer a colisão de gotas se divide em duas partes. A primeira delas consiste em encontrar o momento exato entre o disparo da primeira gota e a formação de uma coluna de água perfeita, e isso exige experimentação. A segunda parte exige encontrar o tempo ideal para o disparo da segunda gota de modo que ela colida com a formação da coluna feita na primeira parte do processo, e isso exige apenas matemática :-)&nbsp;Depois de alguns testes, eu comecei a disparar a primeira gota com tamanho de 25 (o tamanho é na verdade uma medida de tempo, ou seja, o tempo que a válvula permanece aberta, em milissegundos) e fui experimentando até consegui formar uma coluna de água por volta de 195 milissegundos após a abertura da válvula disparar a primeira gota:

![](https://lh6.googleusercontent.com/-6xaKt38rTc8/UTS1gi8zIdI/AAAAAAAAENc/xovhRSLag6Q/s800/IMG_4626.jpg)

Portanto a primeira etapa do processo estava concluída. Agora eu precisava calcular o tempo de disparo da segunda gota, para causar a colisão. Levando-se em conta que a coluna de água levou 220 milissegundos (25 milissegundos da abertura da válvula + 195 milissegundos) para se formar, concluí que precisava de um tempo menor que isso para que a segunda gota atingisse o topo da coluna. Começei a experimentar com a mesma abertura, 25 milissegundos, e introduzindo um atraso inicial de 70 milissegundos fui aumentando em incrementos de 5 milissegundos até obter a primeira colisão, cerca de 90 milissegundos após o disparo da primeira gota. Portanto meus cálculos agora estavam prontos: 25 + 195 + 25 + 90 = 335\. Então 335 era o tempo que eu precisava para saber exatamente quando disparar o flash (conforme expliquei no [artigo anterior](http://raulfragoso.com/blog/esculpindo-a-agua-parte-2/ "Esculpindo a água – parte 2"), é o flash que congela a imagem do splash das gotas). Obtive a imagem abaixo:

![](https://lh6.googleusercontent.com/-M2tAYPv0ohE/UTTQ8dmwS_I/AAAAAAAAENs/8ejTldVRqAk/s800/IMG_4650.jpg)

Gritos de euforia ecoavam nas paredes do meu escritório ! Eu finalmente havia conseguido obter minha primeira colisão de gotas, e não por mero acaso, pois agora eu dispunha do equipamento certo e também havia digerido todo o processo, facilitando a reprodução do experimento com outras variáveis. E essa é realmente uma sensação muito boa: chegar ao resultado esperado e ao mesmo tempo compreender como a coisa toda funciona. Raramente experimento essas duas coisas, simultaneamente, enquanto escrevo programas para computador (fim da piada de programador)

Passei o resto do dia experimentando com ajustes nos tempos das gotas e também do disparo do flash. Brinquei também com a posição e potência do flash, além de usar diferentes materiais para rebater a luz e outras cores para o líquido. É incrível como as formas das gotas são sempre distintas, são quase como flocos de neve, nunca dá para obter uma igual a outra. E acho que é isso o que me atrai tanto para esse tipo de fotografia, há uma infinidade de variações que podem ser obtidas pelas simples formas de uma ou mais gotas de água colidindo. Abaixo segue algumas fotos da mesma sessão daquele dia:

{% include gallery1.html %}


Fiquei muito contente com o resultado, mas sempre há espaço para melhorar. O próximo passo será um upgrade na iluminação com flashes adicionais e também fazer um fundo fosco para iluminar o fundo das fotos. Pretendo também experimentar com diferentes reagentes para os líquidos, para obter colunas e formas mais interessantes. Quero experimentar com alturas diferentes entre a válvula e o recepiente coletor, a fim de obter colunas mais altas. Depois já penso também em obter mais uma válvula para experimentar colisões duplas. As possibilidades são enormes !

O bacana é que até as crianças podem brincar. Ontem meus dois filhos (gêmeos, de 9 anos) me ajudaram na escolha das cores e passamos um bocado de tempo nos divertindo com formas e cores diferentes. Segue abaixo o nosso resultado:


Postarei mais outro artigo em breve, assim que os flashes chegarem e eu tiver melhorado a iluminação.
