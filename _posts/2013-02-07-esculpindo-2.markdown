---
layout: post
title:  "Esculpindo a água - parte 2"
date:   2013-02-07 13:50:44 -0300
categories: waterdrops
---

No meu [artigo anterior](https://raulfragoso.github.io/waterdrops/2013-02-05-esculpindo-1 "Esculpindo a água – parte 1"), falei da minha paixão por water drops, do magnífico trabalho feito pelo fotógrafo alemão Markus Reugels e também apresentei o resultado da minha primeira experiência com water drops há 3 anos. Neste artigo tentarei explicar um pouco mais sobre o que aprendi em minhas pesquisas e também das minhas experiências mais recentes.

### Como os profissionais fazem

Abaixo está a foto de um dos setups do Markus Reugels, onde pode-se observar o uso de um temporizador microprocessado que controla o fluxo das gotas através de uma válvula solenóide, um sensor do tipo photogate para detectar a passagem da gota de água durante seu trajeto, e também o disparo da câmera e/ou do flash.

[![](http://i.imgur.com/12qjjSy.jpg)](http://www.telegraph.co.uk/culture/culturepicturegalleries/9025139/Out-of-this-world-planets-captured-within-water-drops-by-Markus-Reugels.html?image=4)

Apesar de parecer complicado, o processo é relativamente simples de entender.

O maior desafio nesse tipo de fotografia é conseguir fotografar o impacto das gotas no momento exato em que elas se colidem, e isso tudo acontece numa fração de segundo. Portanto, é necessário ter um controle preciso sobre algumas variáveis:

*   o objeto em movimento, ou seja, o fluxo da liberação das gotas;
*   o cálculo do tempo que uma gota leva para gerar o evento a ser fotografado;
*   o momento exato da captura da imagem, isto é, o disparo da câmera ou do flash externo;

Para o controle do fluxo das gotas, usa-se uma válvula solenóide (o pequeno mecanismo conectado ao sifão no topo da imagem acima), que é uma espécie de bomba ativada eletro-mecanicamente. É o mesmo tipo de válvula utilizada em muitos sistemas automáticos de irrigação e também em máquinas de lavar roupas, geralmente para dispensar líquidos como amaciante ou detergente de maneira periódica durante o ciclo de lavagem. Por ser controlada eletronicamente, a válvula solenóide pode ser conectada a um circuito eletrônico onde um processador (usualmente baseado na plataforma Arduino) pode controlar e temporizar a abertura e fechamento da válvula. Por exemplo, é possível programar o controlador para ativar a válvula e liberar uma gota a cada 100 **mili**ssegundos (1 **mili**ssegundo é a milésima parte de um segundo). Ou então programa-lo para liberar uma gota a cada 200 milissegundos e uma segunda gota 400 milissegundos depois da primeira, entre muitas outras variações possíveis. É possível eliminar este passo quando um outro sensor é utilizado para detectar a gota de água durante o trajeto, mas a válvula é muito importante no caso de se querer fotografar a colisão entre uma segunda gota e a coluna de água formada pela primeira, pois será possível controlar a liberação da segunda gota usando-se do tempo para formação da coluna da primeira gota.

O cálculo do tempo do evento pode ser conseguido de diversas maneiras. Uma delas é simplesmente calculando a diferença de tempo entre a abertura da válvula que libera a gota e o evento a ser fotografado. Isso geralmente funciona bem, mas dependendo da precisão da válvula solenóide, poderá haver variações entre o tempo que o sinal é enviado à válvula e o tempo em que a gota é realmente liberada. Para um controle mais preciso, como no caso do conjunto acima, uma opção mais precisa é a utilização de um sensor do tipo _photogate_ (o pequeno dispositivo em forma de “U” entre o bico cor-de-rosa da válvula solenóide e a vasilha branca embaixo). O funcionamento do photogate é bem simples: numa ponta do U, coloca-se um [diodo emissor de luz](http://pt.wikipedia.org/wiki/Diodo_emissor_de_luz) infravermelha, e na outra ponta do U fica um [fototransístor](http://pt.wikipedia.org/wiki/Fototrans%C3%ADstor) alinhado com o LED de IR. Quando a gota de água passa por entre a linha formada pelo LED e o fototransístor, este detecta a interrupção de emissão de luz e o sensor envia um sinal ao controlador, que então reagirá ao evento. A partir deste evento gerado, é possível utilizar o controlador para introduzir um atraso preciso de tempo antes de disparar a câmera/flash no momento desejado.

Já para o controle do disparo da câmera, um outro temporizador é utilizado, geralmente em conjunto com o controlador da válvula solenóide e do sensor que detecta a passagem das gotas. Uma vez calculado o tempo necessário para disparar a câmera, este é introduzido no controlador para que o disparo seja feito no momento desejado, geralmente através de um cabo conectado à câmera ou diretamente na sapata do flash.

Este é um bom momento para explicar a diferença entre disparar a câmera em conjunto com o flash, e a utilização da câmera em modo [Bulb](http://en.wikipedia.org/wiki/Bulb_%28photography%29) num ambiente escuro e com o disparo do flash externo sendo feito separadamente. Como o momento da colisão da(s) gota(s) de água ocorre numa fração mínima de tempo, é importante ‘congelar’ a imagem para que o evento seja registrado sem rastros ou borrões (motion blur), e o momento exato da captura é crucial para obter a imagem esperada com consistência. Qualquer atraso de tempo que não pode ser controlado produzirá resultados inconsistentes. De maneira geral, fotos de objetos em velocidade, como é o caso de colisões de gotas de água, exigem o uso de velocidades altas no obturador (cortina) da câmera, e isso demanda luz em abundância, ou então uma abertura grande do diafragma da lente.

Em fotografia de water drops geralmente utiliza-se lentes para macrofotografia ou tele-objetivas com o intuito de aproximar o quadro onde a pequena gota de água produzirá a colisão, portanto se faz necessário utilizar uma abertura menor no diafragma da lente para que o ‘splash’ produzido permaneça em foco na imagem fotografada, então não podemos usar uma abertura muito grande. E ao usar uma abertura menor do diafragma, consequentemente precisamos de mais luz para compensar a velocidade do obturador. A falta de luz pode ser compensada com a utilização de um ou mais flashes.

Mas ao disparar a câmera em conjunto com o flash, introduzimos uma outra variável no processo: o atraso do obturador ([shutter lag](http://en.wikipedia.org/wiki/Shutter_lag), em inglês), que é o tempo que a câmera leva entre o sinal para disparar o obturador e quando a imagem é realmente gravada pelo sensor da câmera. Esse atraso é de aproximadamente 100 milissegundos nas câmeras DSLR mais modernas, variando para mais ou para menos dependendo do modelo. Este atraso pode ser compensado com o controlador que envia o sinal de disparo para a câmera (por exemplo adicionando 100 milissegundos ao tempo calculado no passo anterior), mas por ser um valor que pode sofrer variações, é prudente pensar em outras opções.

Uma melhor solução é deixar a câmera em modo Bulb (ou Manual, com um tempo de exposição longo suficiente) em um ambiente escuro e utilizar o controlador apenas para acionar o flash. Desta maneira, é o pulso do flash que irá congelar a imagem, e não a velocidade do obturador. Além disso, o flash pode ter sua potência configurada manualmente, fazendo com que o pulso de luz emitida seja ainda mais curto, e portanto ainda mais eficiente para congelar objetos em alta velocidade. Por exemplo, meu flash Canon 430EX quando configurado em potência de 1/8 (ou seja, um oitavo da sua potência total), emite um pulso de luz que dura cerca de 1/7000 segundos, ou seja, cerca de 0.00014 segundos, ou cerca de 140 **micro**ssegundos (1 **micro**ssegundo é a milionésima parte de 1 segundo, ou 1 segundo dividido por 1.000.000). Quando configurado em potência de 1/64, que é a potência mínima possível, a duração do pulso de luz é de 1/25000 segundos, ou 0.00004 segundos, ou 40 microsegundos! Ou seja, ainda mais rápido que uma [diarréia](http://www.vestibularseriado.com.br/humor/item/135-qual-a-coisa-mais-rapida-do-mundo)! :smiley:

Recapitulando, o processo todo se resume ao seguinte:

1.  a gota é liberada
2.  o sensor detecta o início do evento e envia um sinal ao controlador
3.  o controlador utiliza um tempo previamente calculado para gerar o efeito esperado e então efetua o disparo da câmera ou flash

Como explicado anteriormente, é possível eliminar a válvula no passo 1 acima, ou então o sensor do passo 2, mas isso poderá causar falta de precisão no resultado final. E isso eu aprendi na prática, como mostrarei abaixo.

### Minha segunda experiência

Depois de minha primeira experiência, eu passei a mero observador de fotografias de water drops, mas também dediquei algum tempo para estudar outras maneiras para melhorar meus resultados, o que fica bem evidente na explicação técnica acima.

No ano passado, eu encontrei um projeto muito bacana lançado no [Kickstarter](http://www.kickstarter.com/), que é um portal que concentra muitos projetos das mais diversas áreas para serem ‘financiados’, caso a idéia seja boa. O nome do projeto em questão era [Triggertrap](http://www.kickstarter.com/projects/photocritic/trigger-trap-the-universal-camera-trigger), um controlador/disparador de câmeras genérico baseado na plataforma Arduino e que facilita muito a fotografia de [time-lapses](http://pt.wikipedia.org/wiki/Time-lapse), e também vem acompanhado de alguns sensores, entre eles um sensor de som, outro para laser (similar ao fototransístor de um photogate) e também uma porta auxiliar, caso você deseje utilizar ou construir um sensor diferente.

A idéia me pareceu muito boa. Fui em frente e acabei sendo um dos ‘investidores’ do Triggertrap. Gastei US\$ 75 (mais US\$ 10 para o envio) e, três meses depois, recebi em casa o meu Triggertrap:

![](http://i.imgur.com/TiAkuaV.jpg)

Claro que o primeiro uso que me veio à cabeça foi para fazer fotos de water drops, embora ele seja bastante versátil para muitos outros tipos de fotografia.

Então algumas semanas atrás eu resolvi brincar com água novamente. Montei um suporte de PVC para facilitar as coisas, e a idéia foi utilizar o sensor de laser do Triggertrap para detectar a passagem de gota de água e encontrar o atraso ideal para disparar a câmera com o flash. Para o gotejamento, utilizei um desses frascos de remédio vazio com conta gotas na ponta, prendi com durepox numa haste de metal para facilitar o alinhamento. Depois fiz um pequeno furo com agulha na base do frasco, para conseguir um gotejamento mais lento. O conjunto pode ser visto na foto abaixo:

![](http://i.imgur.com/iHYv8qQ.jpg)

O laser utilizado é um desses chaveiros simples, vendido em lojas de utilidades por R$ 5,00. Na foto abaixo dá para ver o laser alinhado com o sensor do Triggertrap, e também os furos que eu fiz em ambos os lados do cano para a passagem da gota de água (usei uma Dremel com disco de corte para plástico):

![](http://i.imgur.com/7bvAWp0.jpg)

Liguei o cabo do Triggertrap à minha Canon T3i. A minha boa e velha Sigma 150mm f/2.8 macro foi a lente escolhida. Também meu bom e velho Canon 430EX foi o flash escolhido, até porque é meu único flash externo :smiley: Tudo montado e com a luz do ambiente mantida no mínimo possível, coloquei a câmera em modo Manual, com tempo de 5 segundos, abertura em f/16 e ISO 100 (para reduzir o ruído), então comecei a experimentar com o tempo de atraso do sinal do laser sendo cortado. Depois de algumas fotos, cheguei a valores entre 70 e 140 milissegundos para compor algumas formas diferentes. O resultado está abaixo:


[![](https://farm9.staticflickr.com/8465/8435750635_b3f75cb560_z_d.jpg)](https://www.flickr.com/photos/raul-fragoso/8435750635)


[![](https://farm9.staticflickr.com/8468/8435749449_558fe89c63_z_d.jpg)](https://www.flickr.com/photos/raul-fragoso/8435749449/)


[![](https://farm9.staticflickr.com/8190/8436834896_785d3dbbc5_z_d.jpg)](https://www.flickr.com/photos/raul-fragoso/8436834896)

[![](https://farm9.staticflickr.com/8185/8435750201_536452cdf5_z_d.jpg)](https://www.flickr.com/photos/raul-fragoso/8435750201)

As cores foram obtidas através do mesmo método utilizado anteriormente, rebatendo o flash em papéis coloridos. Fiquei satisfeito, pois utilizando o Triggertrap eu consegui chegar a resultados mais consistentes, eliminando o elemento da “tentativa e erro”, mas ainda está muito longe do que eu quero fazer. Cheguei a algumas conclusões:

*   o gotejamento não possui controle algum, então a velocidade das gotas atrapalhou bastante;
*   foi difícil conseguir compensar o tempo de atraso do obturador (shutter lag) da câmera, pois ele parece variar entre cada foto;
*   a iluminação está ruim, com muitas sombras nos limites das gotas e também o fundo está muito sem graça;

** Lição 2: usar a ferramenta certa para o trabalho ajuda bastante, mas encontrar a ferramenta certa também exige experimentar com o que se tem. Mas o mais importante é o que se aprende no meio do caminho. **

Devo admitir que me rendi e já decidi investir em uma válvula solenóide e mais flashes. Meu maior problema será adaptar esse conjunto ao Triggertrap, pois ele possui apenas uma porta auxiliar para um novo sensor e eu terei que bolar um circuito eletrônico para controlar a válvula e liga-lo à entrada auxiliar do Triggertrap. Outro problema é que o Triggertrap possui apenas uma saída para o disparo da câmera/flash, e como pretendo utilizar pelo menos dois flashes, terei que achar uma solução para isso.

Ultimamente tenho lido bastante sobre o [Camera Axe](http://www.cameraaxe.com/), que é outro disparador/controlador também baseado na plataforma Arduiono, mas bem mais avançado que o Triggertrap, pois possui mais de uma entrada para câmera/flash e também duas entradas para sensores externos. Eles até já têm um [sensor para válvula solenóide](http://www.cameraaxe.com/wiki/index.php?title=Sensors#Valve_Sensor) com um [sifão de Mariotte](http://en.wikipedia.org/wiki/Mariotte's_bottle) acoplado. Estou bastante tentado a experimentar esse conjunto. Postarei aqui meu progresso depois que me decidir.
