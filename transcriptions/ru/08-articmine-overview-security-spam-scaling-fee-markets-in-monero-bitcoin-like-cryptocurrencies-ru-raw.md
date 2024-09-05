# ArticMine

_**Обзор безопасности, устойчивости к спаму, масштабируемости и рынка комиссий криптовалют, подобных Monero и Bitcoin**_

[https://youtu.be/KuIRDTsyzkQ](https://youtu.be/KuIRDTsyzkQ)

---

_**Франциско:**_ Меня зовут Франциско Кабаньяс, также я известен как ArticMine. Мы рассмотрим некоторые вопросы безопасности, устойчивости к спаму, масштабирования и рынка комиссий в криптовалютах, подобных Monero и Bitcoin.

И сейчас я приведу несколько определений и вкратце расскажу о них. TR - некий базовый размер транзакции, MB - размер блока в байтах. Я ввожу понятие периода блока, выраженного в секундах, означающее количество секунд между блоками. В Monero он составляет около 120 секунд, то есть, две минуты, в Bitcoin и Bitcoin Cash - 10 минут. Некоторые монеты работают быстрее. У Zcash период равен 75 секундам, у Litecoin - около 150. Одна из действительно быстрых монет - Ethereum, где между блоками проходит от 12 до 15 секунд. Далее RBase - размер вознаграждения за блок. F - общий размер комиссии за блок.

Кроме того, существуют штрафы и расходы. О расходах мы, как правило, не говорим. Но на эту тему были написаны некоторые работы. Речь идёт о расходах майнера, связанных, например, с вычислением блоков. В статье, написанной в 2015 году, некто Питер Ризум выдвинул теорию на этот счёт. По сути, в конце вы просто добавляете второй штрафной коэффициент, зависящий от вероятности вычисления блоков. Главное, что я узнал об этом, это то, что размер расходов пропорционален размеру вознаграждения за блок. Это позволяет использовать данный коэффициент для расчёта рыночной стоимости для майнера. В Monero, конечно же, заглавная M означает штраф и используется для его вычисления.

Далее следует то, что я называю максимальным размером блока на момент майнинга. По сути, это то значение, до которого майнер в определённый момент времени может увеличить размер блока. Это не означает, что оно не может вырасти в будущем. Да, в одних случаях оно фиксировано, в других - нет. Так, например, в Monero при расчёте штрафа в любой момент времени оно в два раза превышает среднее значение. То есть, его можно увеличить. В других криптовалютах оно абсолютно неизменно и представляет собой некое статичное число.

И, конечно же, увеличение размера блока в процентах - B. Это параметр, который мы часто используем в Monero. Он означает, что если у меня, например, есть блок размером 300 000 байт, и я решу увеличить его до 3 миллионов байт, это станет десятикратным увеличением. Мы не сможем этого сделать, но в случае с 300 000 байт, допустим, я увеличу размер на 10%, что составит 30 000 байт, тогда это и будет увеличением, составляющим 0,1. И если увеличить размер на 1% или 0,01, то это и будет увеличением, выраженным в процентах. Самое большее увеличение B в Monero равно 1. И, конечно же, это требование протокола Monero.

Теперь давайте рассмотрим, что такое рынок комиссий в криптовалютах, основанных на алгоритме доказательства работы. Мы часто говорим о рынке комиссий, но что это на самом деле? Итак, рынок комиссий - это процесс свободного коммерческого взаимодействия между майнерами и пользователями криптовалюты, где и майнеры, и пользователи действуют в своих собственных известных интересах. То есть, это свободный рынок между майнерами и пользователями. Они действуют в своих собственных интересах, устанавливая цену за передачу транзакций, то есть, фактическую отправку транзакций. Правила рынка комиссий определяются протоколом консенсуса криптовалюты. Поэтому, когда мы говорим о рынке комиссий, мы, по сути, говорим о том, какой набор правил имеется в криптовалюте и определяет рынок комиссий. То есть всё определено заранее. Это заложено в самом устройстве криптовалюты. Хотя многие и думают, что рынки комиссий возникают только в случае с отдельными монетами, но у других монет его нет. Рынок комиссий существует, и вопрос лишь в том, какую форму он примет.

Итак, это типы рынков комиссий. И как же нам установить максимальный размер блока? Для этого существует целый ряд решений. Можно сделать это в рамках протокола консенсуса. Самый известный пример - Bitcoin, где максимальный размер блока задан на уровне одного мегабайта. Они думали над этим решением лет десять и решили: "Ладно, будем учитывать только часть транзакций", реализовали SegWit, и фактически увеличили размер блока. Так что, этот параметр задаётся на уровне протокола консенсуса, и изменить его может быть очень и очень сложно.

Другой метод, который, например, довольно активно применялся в Ethereum, - голосование майнеров. То есть, майнеры сами указывают желаемый размер блока. Как правило, это делается путём размещения дополнительной информации, которая помещается в хэш блока, например, в сам блок. А затем они создают блоки на основе согласованного путём голосования размера блока. В случае Ethereum всё будет зависеть от лимита газа. Как результат возникают политические споры. Вы можете ознакомиться с историей сообщества Ethereum, связанной с вопросом изменения лимитов газа, слишком высоких комиссий и слишком высоких расценок на газ. Кстати, газ в Ethereum можно примерно соотнести с размером блока. Ethereum - это криптовалюта, связанная с обработкой данных, а не просто с их хранением, как, например, Bitcoin и Monero.

Затем существует понятие адаптивного размера блока на базе некоторой средней величины, предусматривающее или не предусматривающее наличие штрафа. Один из вариантов был предложен BitPay и Bitcoin примерно в 2016 году. Среднее значение вычислялось более чем по 2000 блоков Bitcoin. И это среднее значение затем использовалось для корректировки размера блока. Это очень похоже на Monero, за исключением отсутствия штрафа.

Когда речь заходит о размере блока, определяемого штрафами, Monero, безусловно, является самым крупным проектом, реализующим такой подход. Первоначально он был разработан CryptoNote. Суть концепции заключается в том, что, увеличивая размер блока выше среднего значения, вы лишаетесь части своего вознаграждения за блок. Именно такую концепцию использует Monero для масштабирования. Вы лишаетесь какой-то части своего вознаграждения за блок, то есть, части положенных вам активов. Это то, о чём следует помнить. И даже если вообще убрать вознаграждение за блок и оставить только штраф, но без затрат, это не решит проблему.

Итак, существует два сценария. Нет никакого штрафа: ни просто штрафа, ни иных затрат со стороны майнера при достижении  MBMax, то есть вашего максимального размера блока, или же штраф или прочие затраты со стороны майнера присутствуют. Эти два сценария, действующие в случае с рынками комиссий.

А теперь рассмотрим проблему с точки зрения рационального майнера. Рациональный майнер, рациональный пользователь в условиях свободного рынка комиссий действует в своих собственных и очевидных интересах. Он не является ни альтруистом, ни злоумышленником. Рациональный майнер желает получить максимальную прибыль, но при этом имеет дело с рациональными пользователями, которые хотят платить наименьшую комиссию за добавление их транзакций в блоки.

Таким образом, мы сталкиваемся с интересной проблемой. На самом деле проблема немного сложнее, чем может показаться на первый взгляд, учитывая конечное число транзакций в пуле, с распределением весовые значения и комиссии. Сейчас я использую термин "весовые значения" в обобщенном смысле. Например, в Bitcoin при расчёте этой части, которая войдёт в один мегабайт, с после обновления SegWit используются весовые значения, а не фактический размер. А Monero использует их в некоторых транзакциях наоборот, чтобы учесть стоимость верификации доказательств Bulletproofs для выходов, количество которых больше 2, например 4, 8, 16. Таким образом, мы получаем дополнительный параметр, который фактически используется вместо строгого размера блока.

И тогда возникает вопрос: как максимизировать прибыль майнера и минимизировать затраты пользователя? На самом деле это так называемая задача дискретной оптимизации, решаемая довольно точно. Но в практическом смысле решение такого рода задач может занять много времени и оказаться бесполезным. Её можно аппроксимировать. Её можно упростить. Но на самом деле задача дискретной оптимизации возникает по причине наличия транзакций разного размера и необходимости их оптимизации, позволяющей максимально удобно "упаковать" такие транзакции.

Давайте рассмотрим простой пример рынка комиссий без штрафов и без затрат со стороны майнеров. Итак, мы выполняем аппроксимацию задачи дискретной оптимизации. Я называю это "стремящейся к нулю аппроксимацией транзакций". Мы говорим, что размер каждой транзакции намного меньше размера блока или той части блока, которую мы пытаемся увеличить. И вот что делает майнер: он выбирает транзакции в порядке размера комиссии, уплачиваемой за байт. Затем майнер добавляет транзакции в блок, начиная с самых высокооплачиваемых транзакций. После чего в зависимости от определённых критериев майнер останавливается. Допустим, у майнера больше нет транзакций или места в блоке для их включения, то есть достигается значение MBMax.

Таким образом, возможны две ситуации. В первом случае примером может служить модель Bitcoin с большим размером блока. Bitcoin Cash, Bitcoin SV, а также множество других монет, таких как Litecoin, Dash, FIT, Profile, Dogecoin. По сути, у всех них фиксированный размер блока, который не заполняется постоянно. Теоретически, и на самом деле так было с Bitcoin в первые годы его существования - там не вообще не было никаких комиссий. Если вы торговали и имели дело с Bitcoin в 2011, 2012, 2010, даже в 2013 и 2014 годах, вы могли проводить транзакции в блокчейне Bitcoin, вообще не уплачивая никаких комиссии. По сути, это и есть сценарий с большим размером блока. Другой сценарий, широко обсуждавшийся в Bitcoin, а также в некоторой степени в Ethereum, заключается в достижении максимального размера блока с последующим возникновением проблемы спроса и предложения, когда, сколько бы ни увеличивалась цена, предложение остаётся прежним. Именно поэтому в случае Bitcoin и Ethereum мы наблюдаем очень высокие комиссии. Итак, у вас есть фиксированный размер блока. И единственное, что вы можете сделать, если хотите достичь его, - платить всё более высокую цену. Но независимо от того, насколько высокую цену вы платите, и это очень важно, предложение не увеличивается.

Как правило, рынки так не работают. Повышение цены либо увеличивает предложение, либо, как я полагаю, может произойти, покупатель начинает искать что-то другое. И очень известный пример: в 2017 году объём транзакций Litecoin вырос в 80 раз. Почему? Потому что блокчейн Bitcoin достиг предела. Если человеку было нужно, например, перевести Bitcoin в другую монету или другой токен, скажем, из фиата, Bitcoin, во что-то другое, для этого выбирался Litecoin. Таким образом, произошел резкий всплеск спроса на транзакции в блокчейне Litecoin. Впоследствии в сети появился Bitcoin Cash, который снял часть давления. А затем в Bitcoin всё чаще стали проводиться транзакции SegWit, что также значительно сняло давление. Поэтому, хотя в 2017 году Litecoin пережил огромный рост объёма транзакций, с тех пор он выровнялся. Но это хорошо иллюстрирует проблему, которая возникает в ситуации, когда рынок комиссий, подобный существующему в Bitcoin, по сути, является рынком, где, сколько бы вы ни повышали цену, предложение останется прежним.

А теперь сделаем ещё кое-что - добавим штраф на затраты майнера. И снова используется та же аппроксимация, дискретная аппроксимация. Тор есть, мы снова делаем то же самое. Майнеры выбирают транзакции в порядке возрастания платы за байт. Идея та же. Майнер добавляет транзакции в блок, начиная с самой оплачиваемой. Однако майнер должен сделать кое-что ещё. Майнер должен проверить каждую транзакцию на предмет её доходности относительно штрафа или обеих затрат, в зависимости от того, что будет применимо. Майнер останавливается, когда заканчиваются транзакции, приносящие прибыль, или, опять же, заканчивается место в блоке, и достигается MBMax.

Теперь, что действительно интересно в этой модели, так это то, как она влияет на рынок комиссий. Мы видим, что майнер упорядочивает транзакции, и это очень важно, и выбирает сначала самые доходные для себя. Так что возможна ситуация, когда майнер остановится на самой низкооплачиваемой транзакции, соответствующей стоимости её добавления, будет остановлена. Таким образом, наибольший штраф или затраты оплачивает самая низкооплачиваемая транзакция в блоке. После этого майнеру становится не выгодно работать дальше. Распространенное заблуждение в подобной ситуации заключается в том, что если у вас есть X штрафов, и вам нужно X транзакций, то вы сможете добавить все эти транзакции. Нет, потому что майнер будет оптимизировать добавление. И сначала он добавит в блок самые доходные транзакции. А самая низкооплачиваемая транзакция будет платить штраф. Это очень важный момент, который приводит нас к следующему слайду, где речь уже пойдёт о рынке комиссий Monero.

В Monero используется долгосрочное среднее значение, ML, равное 100 000 блоков, и краткосрочное среднее значение, MS, равное 100 блокам. Двухминутным, 120-секундным блокам. Итак, ML - это среднее значение одного блока. Формула представляет собой рекурсивное вычисление. MB - это размер вашего блока. А затем у нас есть 1,7 ML, ZM - это не облагаемая штрафом зона в Monero. Мы вернёмся к этому вопросу позже. А теперь посмотрим на ML/1,7. По сути, мы смотрим на минимальный размер блока и 1,7 ML. Таким образом, мы имеем дело с самостоятельным определением предела. А затем вы доводите до максимума предельное значение минимального размера блока, ZM, и вашего базового значения, который является эквивалентным ML/1,7. Это обеспечивает стабильность. И это рекурсивное вычисление.

В анализе, который я добавил буквально в последнюю минуту, внеся таким образом изменения, рассматривается действительно интересный вопрос. Что такое ZM и как задаётся это значение? Итак, ZM имеет значение, равное существующему на данный момент уровню в 300 000 байт. Эталонный размер транзакции составляет 3000 байт. То есть, мы имеем дело с 1%. И этот параметр задаётся изначально. Он необходим для того, чтобы размер комиссии не превышал разумных пределов. Если, например, как уже говорилось в чрезвычайно интересном выступлении сегодня утром, вы захотите увеличить типичный размер транзакции в Monero до 10 000 байт, то вам придётся изменить этот параметр, определяющий пределы не облагаемой штрафами зоны, до миллиона байт. Так вы сохраните прежнее соотношение. Если этого не сделать, то можно столкнуться с серьёзными проблемами, поскольку размер комиссий резко возрастёт. Фактически, комиссии вырастут примерно в десять раз. Кроме того, возникнут проблемы с аппроксимацией, о которой я уже говорил, к бесконечно малым транзакциям, потому что теперь размер транзакций будут составлять, например, около 3%, а не 1% от не облагаемой штрафами зоны. И поэтому в Monero существует такая зона, составляющая первые 300 000 байт. Но как только данное значение превышается, уплачивается штраф. Вот именно этот параметр и нужно изменить в данном примере. Но это простое изменение.

Теперь у нас есть среднее и сверхдлинное значения. Итак, это MS, краткосрочное среднее значение. И я хочу отметить пару моментов, которые очень важны. Это максимум MB, ML. ML - это динамическая зона, не облагаемая штрафами. Она должна быть больше базовой, составляющей 300 000 байт. Если вы превысите это значение, вас заблокируют. Так что это значение будет выше. Минимальное из этих двух значений - 50ML. И это не что иное, как коэффициент резкого повышения.

Коэффициент резкого повышения указывает на то, насколько вы позволяете краткосрочному среднему значению подняться выше долгосрочного. Зачем он нужен, и каково обоснование? Изначально говорилось, что он позволяет немного расширить масштабирование без смещения долгосрочного среднего значения. Но одна из главных причин его использования кроится в понимании того, как работают транзакции в случае с кредитными картами, в частности, в сети Visa.

Как правило, 23 декабря в Европе и Северной Америке наблюдается пик объёма проводимых в сети Visa транзакций. Увеличение является примерно 16-кратгным. Это связано с праздничными расходами. Есть ещё несколько праздников, которые могут спровоцировать такой всплеск, но и у них другой цикл. Китайский Новый год - один из них. Кроме того, существуют исламские праздники, а они соответствуют лунному календарю. И они тоже могут вызвать всплеск экономической активности, причём достаточно значительный. И можно составить сценарий, в рамках которого все они совпадут, максимизировать вероятность того, что Ураза-Байрам и Рождество выпадут на одно и то же время, и таким образом вы получите ещё больший всплеск, чем обычно.

Но самое главное при проектировании платёжной сети - возможность увеличения масштаба в очень короткий период времени, позволяющая удовлетворить резко возникающий спрос. И у Visa есть много подходящих для этого примеров. Обычно они управляют сетью, но в ней есть средняя скорость проведения транзакций, потому что они знают, что в эти два-три дня или один день в году будет совершено в 16 или в 17 раз больше транзакций, и поэтому они этот день следует учитывать. И если мы всерьёз собираемся заняться платёжными каналами, мы должны последовать их примеру. Я не знаю ни одной другой криптовалюты, которая бы делала что-то подобное, но речь заходит о размере блоков, очень интересное эмпирическое правило гласит, что для решения проблемы возрастания динамики в праздничные дни вам потребуется объём проводимых транзакций Bitcoin, и шестнадцатикратный объём проводимых транзакций Bitcoin Cash. Я же могу сказать, что это обостряет противоречия в сообществе Bitcoin. Но дело в том, что после реализации SegWit разница между Bitcoin и Bitcoin Cash является примерно шестнадцатикратной. И это тот коэффициент резкого повышения, который им действительно нужен. 50, скорее всего, будет многовато, но это именно тот параметр, который можно было бы ужесточить.

Теперь рассмотрим различные имеющиеся у нас сценарии. Ну, у вас есть штраф Rbase(B+BT)2. По сути, берётся вознаграждение за блок и умножается на увеличение размера блока. Всё это возводится в квадрат. По сути, это и есть штраф. В первом случае краткосрочное среднее значение получается больше долгосрочного. То есть, мы находимся в штрафной зоне. И размер транзакции меньше 50ML. Значит, мы не хотим преодолевать этот барьер. И я называю это чистым сценарием Monero.

Затем добавляется проверка транзакции T в точке B в зоне штрафа и определяется B, BT, MS - это, собственно, и есть постепенное увеличение штрафа. И мы получаем формулу, в которой разница между старым и новым штрафом заключается в том, что наше базовое вознаграждение будет в точке B, в которой находится штраф. Например, это может быть 10% или 2%. А BT - это дополнительный штраф, то есть дополнительное увеличение размера блока за счёт добавленной вами транзакции. Таким образом, мы получаем дополнительный штраф, который будет уплачен за добавление транзакции. И это очень важная формула, потому что она говорит, какую комиссию майнер запросит за включение транзакции в блок. То есть майнер, включая транзакцию в блок, как минимум, захочет покрыть штраф. И это та формула, которая определяет размер комиссий в Monero. Это тонкая вещь, но, по сути, мы наблюдаем увеличение штрафа в зависимости от добавления транзакции в блок. И комиссия также должна увеличиться, чтобы покрыть штраф за добавление транзакции.

Но возможен и другой сценарий. В этом случае MS больше ML, а MB больше 50ML. Это уникальный случай, поскольку краткосрочное среднее значение достигает максимума. Вы не можете больше увеличивать его, но всё равно получаете удвоение размера блока. Таким образом, возникает ситуация, когда приходится заплатить максимальный штраф Monero, и это единственный случай в Monero, когда поведение напоминает Bitcoin. Все транзакции конкурируют друг с другом за уменьшающееся место в блоке. Так что в этом исключительном случае вы, по сути, платите комиссию Monero плюс комиссию Bitcoin. Происходит именно так.

Так что в этом случае вам снова придётся не только заходить за штрафной барьер, но и конкурировать в стиле Bitcoin с другими транзакциями относительно фиксированного MBMax, поскольку значение MS больше не может масштабироваться. Таким образом, мы используем оба этих коэффициента и получаем очень дорогой барьер. Так что вместо жёсткого ограничения по достижении долгосрочного среднего значения, лучше представить всё как очень жёсткую пружину, которая становится только жёстче по мере того, как вы её сжимаете. Как железнодорожную пружину, например, поглощающую энергию. Он сжимается очень медленно, и при остановке поезда обеспечивает целостность всего, что находится позади локомотива. И Monero также смягчает ход на определённом уровне, а не просто ударяется о жёсткий барьер. Так что это действительно работает, как жёсткая пружина.

Теперь рассмотрим другой пример - "сценарий большого блока Bitcoin". В этом случае какие-либо штрафы отсутствуют. Поэтому значение FT и значение BT равны нулю. Теоретически, комиссия тоже должна быть нулевой. Так и было в случае с Bitcoin или Bitcoin Cash, поскольку в тот период, примерно до 2014-2016 года, это была, по сути, одна монета, и когда в блоках оставалось место, комиссия за блок могла быть ниже, чем в Monero. И не было никакого трения. И если говорить о рынке комиссий, большинство транзакций были нулевыми. В Monero применяется штраф, так что и размер комиссий будет меньше. Фактически, комиссии Bitcoin Cash сейчас ниже, чем комиссии Monero, что отчасти доказывает мои слова.

Причина, по которой Monero может поддерживать минимальный размер комиссии, а именно так сейчас и происходит, заключается в угрозе выплаты штрафа. И сегодня в Monero, чтобы не попасть в штрафную зону, мы устанавливаем примерно половину от размера блока. Так что вероятность попадания в эту зону присутствует. На самом деле, так и произошло как раз перед последним хардфорком. Поэтому нам необходимо поддерживать минимальный размер комиссии, который будет соответствовать штрафу в будущем. И это, опять же, важно. Эта угроза штрафа. В прошлом, эта сумма была значительно меньше. Она составляла около 20% от суммы штрафа. Таким образом, у нас была очень низкая комиссия за ретрансляцию, просто потому что мы были далеки от нынешнего состояния. Но опять же, одна из проблем, с которой мы сталкиваемся в подобных сценариях с большим размером блока Bitcoin, - это риск спам-атаки, когда значение MB, то есть блока, намного меньше максимального размера блока.

Отличным примером является недавняя атака на Zcash, где сложилась именно такая ситуация. В Zcash решили: "Ладно, возьмём Bitcoin, и сделаем наши транзакции примерно в восемь раз больше, увеличим скорость добавления блоков в восемь раз и как бы таким образом скопируем модель. Да! В придачу мы ещё будем обеспечивать приватность". Ведь одна из причин, по которой в Bitcoin транзакции могли проводиться бесплатно, заключалась в том, что транзакции были похожи друг на друга. Теперь они не похожи. Итак, Zcash подвергся атаке с использованием очень большой Z-транзакции, которая является приватной транзакцией Zcash, занимающей половину блока. После они заявили, что это произошло из-за неправильного ценообразования. Атака обошлась злоумышленнику очень и очень дёшево. И спам-атака продолжалась несколько месяцев. Примерно с августа и до осени прошлого года. И было похоже, что они никого при этом не видели, а просто наблюдали за блоками с одной конкретной транзакцией, по сути, занимавшей половину блока. Очень простой способ атаки.

Поэтому, при отсутствии правильного ценообразования, существует вполне реальный риск спам-атаки. Более того, при наличии приватности спам становится ещё большим риском, потому что вы не можете использовать цензуру для борьбы со спамом. Именно так мы боремся с большим количеством спама в электронной почте. Мы подвергаем его цензуре. Мы не любим это слово, но именно так мы и поступаем. Если с какого-то сервера приходит спам, мы блокируем его. Анализируя транзакции на предмет спама, мы будем их блокировать. Я использую спам-фильтр, который, по сути, отслеживает динамику транзакций. В моём ящике Linux есть папка для спама, полная вирусов Windows, которые я за многие годы научил его воспринимать как спам. Таким образом, в моём почтовом ящике Linux собрана огромная коллекция вирусов Windows. Это спам, потому что именно этому я обучил фильтр. Это становится интересным. Но цензура - это не выход. Поэтому, при наличии приватности, единственным способом борьбы со спамом является грамотное ценообразование.

Хорошим примером является метод атаки под названием "Большой взрыв". Атака методом большого взрыва сводится к тому, что вы, по сути, просто проводите множество транзакций одновременно. И ваши затраты на оплату, опять же, сводятся к штрафу. То есть, по сути, злоумышленник платит в четыре раза больше, чем размер вознаграждения за блок, при условии, что майнеры не действуют сообща. В данном случае майнеры честны, и завышение базового значения приводит к штрафу, и майнеры свободно добавляют транзакции базового размера. И опять же, суть в том, что злоумышленник не просто рассчитывает покрыть штраф. По той самой причине, о которой я говорил, майнер не станет сотрудничать и будет наживаться за счёт злоумышленника. Вот почему атака такого типа обходится гораздо дороже, чем в случае с уплатой штрафа, хотя в данном случае речь и идёт о вознаграждении за блок. Если злоумышленник уже контролирует 51% сети и вдобавок хочет провести атаку методом большого взрыва, то дополнительные затраты будут связаны с вознаграждением за блок, потому что, по сути, добавляется штраф. Но без 51% затраты составят в четыре раза больше, чем награда за блок.

Вариант атаки методом большого взрыва, который довольно много обсуждался, является атака на кольцевые подписи Monero путём отправки достаточного количества транзакций с целью получения необходимого объёма информации о кольцах. Проблема в том, что для этого вам нужно в 16 раз больше транзакций, чем позволяет реальная скорость проведения транзакций. В этой связи возникали некоторые сомнения, и были написаны некоторые работы. Члены сообщества подозревали, что что-то не так, и даже обнаружили какую-то организацию или какую-то структуру, продвигающую эту концепцию. В результате, когда они добрались до точки наложения штрафа, то поняли, что это просто не работает, и лучше попытаться сделать что-то другое. Так что это заблуждение - спам-атака на Monero не будет дешёвой. Но при наличии сосредоточенного подхода вы оказываетесь под ударом.

А теперь перейдём к другому интересному вопросу. Одна из идей Bitcoin, и она изложена в главном документе Bitcoin, написанным Сатоши, идея заключается в том, что в итоге сокращающееся в размере вознаграждение за блок Bitcoin можно заменить комиссией за проведение транзакций. И мы можем утверждать, лично я могу категорически утверждать, что в Monero такого никогда не будет. И причина заключается в том, что комиссия в Monero пропорциональна вознаграждению за блок. Но ещё интересней тот факт, что сумма получаемой в итоге комиссии будет зависеть от размера вознаграждения за блок. Если вознаграждение за блок равно нулю, то и комиссия будет нулевой. Другое дело, что по мере увеличения размера блока Monero у вас появляется возможность масштабировать его с меньшей скоростью. И это говорит о том, что при увеличении размера блока в лучшем случае комиссия и вознаграждение Monero останутся неизменными, а скорее всего даже снизятся. Так что избавиться от этой угрозы безопасности Bitcoin таким способом не получится.

У меня состоялось несколько интересных бесед с людьми из сообщества Bitcoin SV, и они рассказывали мне обо всех этих замечательных решениях, а я смотрел на их комиссию и на вознаграждение, и понимал, что они не заменят комиссию на вознаграждение, по крайней мере, на постоянной основе. На самом деле лучше всего использовать подход Bitcoin Core, который заключается в сохранении размера блока, ну, и, собственно, полного ухода от использования в качестве транзакционной валюты в интересах безопасности. Что ж, возможно. И такая вероятность довольно велика.

И вот некоторые из тех вещей, которые мы наблюдали в криптовалютах с высокой комиссией, таких как Bitcoin и Ethereum. Если вы посмотрите на размер комиссии и вознаграждения - а у меня там есть ссылка, bitinfocharts, которая отлично подходит для этих целей, поскольку вы можете взглянуть на их размер в исторической перспективе - вы обнаружите, что в случае Bitcoin наблюдаются небольшие скачки, если в сети возникает какой-то спрос или всплеск. А затем размер снижается примерно до 1 %. И это происходит несмотря на то, что не было никаких существенных изменений. Даже несмотря на халвинги. То есть они даже не поспевают за ними. И это говорит о том, что комиссии никогда не заменят вознаграждения за блок Bitcoin. Многое на это указывает, и это называется дефицитом безопасности Bitcoin.

В случае Ethereum, опять же, наблюдаются аналогичные скачки, может, немного больший процент, потому что эта монета используется очень интенсивно, и они позволили этим параметрам расти. Но всё же вы не увидите признаков возможной замены вознаграждения за блок на комиссию.

Мне неприятно это говорить, но я не могу отрицать тот факт, что в 2014, 2015 годах я продал свои Bitcoin за Monero именно из-за этих проблем. Но по этой причине я испытываю серьёзные опасения в отношении безопасности Bitcoin в долгосрочной перспективе. Мне также хорошо известно, что некоторые разработчики Bitcoin также испытывают подобную озабоченность. Так что вокруг этой проблемы существует множество опасений. Это очень деликатная проблема, поскольку единственный способ решить её - по сути, отказаться от самого священного аспекта протокола Bitcoin, которым является ограничение денежной массы 21 миллионом монет. Так что они как бы находятся между молотом и наковальней. Но да, это трудно признать. И это случится не завтра. Я имею в виду, что следующее снижение курса Bitcoin в два раза поставит его на один уровень инфляции с Monero. Так что на этом пути может произойти ещё несколько халвингов, но, если ничего не предпринять, в конце концов возникнет проблема. Таков мой прогноз.

Перейдём к следующему вопросу - постэмиссия Monero. Насколько мне известно, Monero - единственная монета, которая сделала это намеренно. Dogecoin ввёл постэмиссию, потому что это был баг, и они просто сохранили его. Но, по крайней мере, они спаслись, сохранив ошибку в коде. При этом Dogecoin имеет более высокую инфляцию, чем Monero. Она составляет около 5%. А в Monero постэмиссия была намеренно заложена первой командой ведущих разработчиков сразу после запуска. Я сильно подозреваю, что в этой первой команде было много майнеров. В то время я не состоял в команде. Но именно они приняли это решение. Они поверили в эту идею и будучи майнерами сделали именно так. А потом они сделали нечто невероятно умное - установили цену чуть ниже исторического уровня инфляции золота. Я много говорил на эту тему, выступая на Monoerotopia. И это означает, что уровень инфляции Monero очень близок к оптимальному. Чуть ниже уровня инфляции золота. Так что Monero отвечает всем стандартам австрийской экономики, и даже превосходит их. Да, именно не отвечает, а превосходите их, если сравнивать с твёрдыми национальными валютами.

Таким образом, вы не можете утверждать, что это решение выводит инфляцию из-под контроля, или что-то в этом роде, но в то же время вы максимально повышаете уровень безопасности. Единственное, что я могу сказать вполне однозначно: если бы мы перешли к модели вознаграждения с понижающимся размером вознаграждения за блок, Monero стала бы небезопасной и очень уязвимой для спама и атак 51%. Если вы хотите рассчитать затраты на проведение любой атаки на Monero, будь то спам-атака или атака 51%, они всегда будут пропорциональны вознаграждению за блок. Эти 0,6 XMR за блок - это то, что делает Monero безопасной, и то, что обеспечивает её надёжность. Monero очень сложно заспамить.

И теперь поговорить о том, что можно было бы сделать немного жёстче. И мы можем ужесточить сразу несколько вещей. Первое, что нужно сделать, - это изменить средние значения. Помните цифру, связанную с MS, о которой я говорил, - 50ML как предел, как фактор резкого повышения. Её можно снизить до 16ML. Таким образом, мы можем значительно снизить средний коэффициент повышения до того уровня, который реально необходим для покрытия коэффициентов повышения по опыту Visa. И да, вы допускаете превышение, если произойдёт своего рода наложение рождественских праздников с другими. Я имею в виду мусульманские праздники. Поскольку одни праздники отмечаются по солнечному календарю, а другие - по лунному, то теоретически в один момент они сойдутся в одной точке. Но эта проблема всё же решаема, поскольку вы можете определить окончательный размер штрафа, произвести двадцатикратное увеличение или сделать что-то в этом роде. Пусть это и дороговато, но с этим можно справиться. Кроме того, можно увеличить значение ML с 1,7 до 2. Знаю, что это спорное решение, но это позволит нам справиться с всплесками, подобными тем, что мы наблюдали в Litecoin, когда у Bitcoin возникли проблемы.

Одна из вещей, которая меня очень беспокоит, особенно в связи с политической обстановкой, сложившейся в мире, - как сообщество Monero справится с атакой на ненавистную фиатную банковскую систему? Знаю, многие люди в нашем сообществе не любят банки и не любят банковскую систему. Но я хочу быть уверенным в том, что если кто-то атакует её, некий государственный актор атакует Visa, то сеть Monero справится, сможет взять на себя часть нагрузки и будет работать. А это значит, что нам необходимо усилить защиту. Значит, нам нужно купить дополнительный компьютер, возможно, увеличить пропускную способность, может быть, купить дополнительное оборудование, чтобы обеспечить возможность запуска больших узлов. Так что мы должны осознать, что атака на финансовую систему возможна, и мы должны стать частью решения этой проблемы. А это предполагает тяжёлую работу. Это означает, что нам придётся засучить рукава. Мы не должны радоваться тому, что этих негодяев банкиров атаковали. Нет. У нас возникает проблема. У нас есть люди, которым нужно совершать транзакции. У нас есть сеть, которая позволяет это делать. И мы как сообщество должны стать частью этого решения. И мы можем это сделать. То есть, одной из вещей, которые я всегда учитываю с точки зрения укрепления Monero, - это сценарий Litecoin в более широком масштабе. И это одна из идей.

Другая идея заключается в том, что мы можем установить сверхдолгосрочное разумное среднее значение. Многим членам сообщества станет от этого немного не по себе, поскольку ситуация может выйти из-под контроля. И один из способов реализовать это сводится к его ограничению существующим, по сути, начальным. А это значит, что вы удваиваете его примерно каждые два года, что, собственно, и будет делать среднее значение в 1 миллион блоков по формуле, которую я представил. И тогда вы делаете, по сути, то же самое, что мы делаем не с MS, а с ML. Тогда среднее значение становится коэффициентом для ML. И опять же, у вас есть MA - свободная от штрафов зона в ML. А затем вы используете формулу, производите рекурсивные вычисления, запускаете ML и делаете это в случае миллиона или одного блока.

И это только один из способов, которым мы можем воспользоваться для укрепления. Я считаю его необязательным, но думаю, что члены сообщества почувствуют себя более комфортно, когда в их распоряжении появится нечто подобное. Поэтому я считаю, что это было бы полезно. Среднее значение должно быть установлено с запасом. И я объясню почему  на следующем слайде, когда буду говорить о ещё одном способе решения проблемы масштабирования, а именно об узлах ретрансляции. Эта тема заслуживает отдельного обсуждения, поскольку о такой ретрансляции сложилось неверное представление.

Ретрансляция - это отправка транзакций узлами. И транзакции размером с блок едва ли будут добавляться майнерами. И логика узлов такова: "За эту транзакцию манер получит меньшую комиссию, поэтому он не станет добавлять её, а следовательно, я не стану её ретранслировать". И это имеет смысл. То есть, это даже имеет большой смысл, но при этом работает только с точки зрения политики. Это не обеспечивает защиту от майнинга в ущерб голодающим. Поэтому одно из распространённых заблуждений заключается в том, что Litecoin и Bitcoin Cash, например, скопировали решение Monero и ввели соответствующие комиссии. Проблема в том, что это, конечно же, здорово - получать вознаграждение за добавление блоков. Но майнеры готовы перегрызть друг другу глотку, чтобы получить доступ к транзакциям, и  при этом они могут принимать транзакции напрямую, минуя узлы. Поэтому ретрансляция посредством узлов должна осуществляться в соответствии с неким достаточно сильным консенсусом, поддерживаемым сообществом. Это просто отлично, когда вы имеете дело с гибким, изменяемым консенсусом, отражающим текущее настроение сообщества. Отличный способ. И он не имеет ничего общего с жёстким консенсусом, навязываемым сообществу, и которому не станут следовать многие. Потому что такой консенсус майнер всегда будет в состоянии обойти, например, просто создав веб-сайт, где будет сказано: "Мы возместим вам уплаченную комиссию" или "Предоставьте нам ваши личные данные, и мы сделаем всё бесплатно", или что-то ещё в этом духе.

Вы можете, о чём уже было много сказано, реализовать постоянно изменяемый консенсус или что-то в этом роде - ну, не совсем так - но всё же это тоже отличная идея. И мы уже делаем это, например, в случае с округлением комиссий. Если комиссия не соответствует определённым требованиям или не округляется, мы не будем её отправлять. И это делается ради того, чтобы пользователь не оставлял никаких следов, и чтобы в принципе повысить уровень приватности.

Так же можно поступить и с размером блока. Просто реализуется щедрый размер блока и соответствующий консенсус. А затем он может быть ужесточён для некоторых узлов, особенно для тех, которые не работают в полную силу: "У меня не хватает пропускной способности, поэтому я не стану ретранслировать такое количество транзакций". Такие узлы делают это выборочно, сдерживая таким образом рост сети. И тогда, поскольку узлов становится меньше, создаётся рынок, где немногие из оставшихся узлов будут согласны делать это. Но цена вырастет, поскольку узлов станет меньше. И это может позволить сдержать какой-нибудь внезапный рост сети. Так что это один из вариантов. Ретрансляция транзакций узлами - очень интересная тема. Мы можем коснуться её далее, когда я перейду к вопросам. В сообществе было озвучено много предложений по её использованию в самых разных целях. И при наличии сильного консенсуса, это отличный метод, ещё один инструмент, который можно использовать для укрепления Monero.

А теперь мы можем перейти к вопросам и обсуждению.