CSS стилови
===========

Ако распоредите *HTML* елементе у документу као што је описано у претходним лекцијама, ти елементи ће бити постављени један испод другог и прегледач ће користити неке подразумеване стилове (боје, величине слова, размаке) како би их приказао.

Елементе на правим веб странама је често потребно распоредити и стилизовати у складу са наменом сајта. **Веб дизајн** је активност којом се описује како ће страна и елементи на њој изгледати. Веб дизајн је тесно повезан и са другим областима дизајна као што је организација информација на сајту и правила за једноставно коришћење сајта (енгл. *User Experience*).

Као што је *HTML* језик којим се описује структура и садржај елемената који ће бити приказани на веб страни, тако постоји и посебан језик који се користи за описивање изгледа и геометријског распореда ових елемената. Овај језик се назива *CSS* (енгл. Cascading Style Sheets).

Језиком *CSS* се представљају правила која дефинишу како треба да изгледају елементи на веб страни. На пример, на језику *CSS* се *HTML* елементима додељују својства као што су ``color``, ``background-color`` и слично, како би се дефинисало којом бојом треба приказати текст у елементу, или која ће бити боја позадине. 

У сваком веб прегледачу можете да пронађете *HTML* код било ког елемента приказане веб стране и да испитате која својства има тај елемент и зашто баш тако изгледа. Код већине прегледача притиском на тастер *F12* отвара се додатни прозор у доњем делу прегледача, као на следећој слици:

.. image:: ../../_images/css/browser_inspect.png
    :width: 600px
    :align: center

|

На пример, у прегледачу *Chrome* се у доњем делу отвара прозор у коме се види *HTML* кôд којим је описана структура елемената стране, као и стилови (доле десно) који су примењени на те елементе да би се добио жељени изглед стране.

Померајте миша преко *HTML* кода и посматрајте шта се дешава. Ако, на пример, задржите миша изнад текста 

.. code-block:: html

    <h1>Никола Тесла</h1>

(означено стрелицом и бројем 2), тај део кода постаје осенчен, а биће означен и одговарајући део документа (наслов) у приказу у горњем делу прегледача. Изглед наслова је дефинисан кодом на десној страни

.. code-block:: css

  h1 {
    font-size: 18px;
    color: blue;
  }

Овако изгледа скуп подешавања било ког стила. У сваком подешавању се са леве стране двотачке налази име својства које треба подесити, а са десне вредност. У примеру се дефинише да ће боја слова бити плава, а величина фонта 18 пиксела.

Прегледачи имају неке предефинисане (подразумеване) стилове за велики број *HTML* елемената, да би знали како да их прикажу ако стил није прецизиран. У случају да нам ти предефинисани стилови не одговарају, ми увек можемо да дефинишемо своје стилове којима ћемо описати како стране треба да изгледају у прегледачу.

Дефинисање *CSS* стилова
------------------------

Изглед *HTML* елемената се може дефинисати на више начина. Препоручени начин дизајна модерних веб страна је формирање одвојеног *CSS* фајла који садржи дефиниције стилова. У *HTML* фајлу се на одговарајући начин наводи име једног или више *CSS* фајлова, чији стилови ће бити примењени на елементе наведене у *HTML* фајлу. Овим се обезбеђује конзистентан изглед свих страна у великим сајтовима, јер више *HTML* фајлова може да укључи исти *CSS* документ, па више веб страна користи исти стил дефинисан на једном месту - у *CSS* документу.

Повезивање *CSS* фајла са *HTML* документом je слично (међусобном) повезивању *HTML* докумената помоћу елемената ``<a>``, када се при дефинисању везе наводи локација документа на који треба прећи ако читалац одабере линк. У случају повезивања са *CSS* фајлом је потребно користити елемент ``<link>``, којим се у *HTML* документу дефинише где се налази *CSS* фајл са стиловима.

.. code-block:: html

    <!DOCTYPE html>
    <html>
        <head>
          <link rel="stylesheet" href="stilovi.css">
        </head>
        <body>

        </body>
    </html>

Атрибут ``href`` у овом елементу представља име фајла, који садржи дефиниције стилова који ће бити примењени на елементе у документу. Прегледач чита *CSS* правила из наведеног фајла и, у складу са њима, приказује *HTML* елементе у *HTML* документу.

.. image:: ../../_images/css/html-css-fajlovi.png
    :width: 648px
    :align: center

Адресе *CSS* докумената се наводе на исти начин као и адресе екстерних *HTML* докумената у ``href`` атрибуту елемента ``<a>``. Вредности могу бити релативне адресе ка *CSS* документима на истом сајту, или апсолутне адресе, које најчешће референцирају *CSS* документе на неком другом сајту.

Као што се у елементима ``<a>`` могу користити апсолутни линкови ка удаљеним фајловима, наш документ може да буде повезан са неким *CSS* фајлом ван нашег сајта, којим се дефинишу стилови, на пример:

.. code-block:: html

    <!DOCTYPE html>
    <html>
        <head>
          <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
        </head>
        <body>

        </body>
    </html>

Апсолутни линкови се често користе у случају да је фајл са стиловима јавно доступан на неком сајту и желите да директно искористите те стилове уместо да копирате тај фајл у ваше локално окружење. Довољно је само да ставите ``<link>`` елемент који садржи локацију *CSS* фајла, као у претходном примеру. Мана оваквог приступа је то што је, чак и за веб стране сачуване на вашем рачунару, за правилан приказ потребан приступ интернету.

~~~~

Поред референцирања стилова смештених у посебан фајл помоћу елемента ``<link>``, стилови могу да се дефинишу и у самом *HTML* документу помоћу елемента ``<style>`` у заглављу стране, као што је приказано у следећем коду, који можете одмах да испробате:

.. activecode:: stilovi_u_html_fajlu
   :language: html
   :nocodelens:

    <!DOCTYPE html>
    <html>
        <head>
            <style>
                 h1 {color:red;}
                 p {color:blue;}
            </style>
        </head>
        <body>
            <h1> Наслов </h1>
            <p> Неки текст. </p>
        </body>
    </html>

Овако дефинисани стилови се могу применити само на елементе *HTML* документа у коме су наведени. 

Такође, могуће је дефинисати стил појединих елемената стране додавањем атрибута ``style`` у сам *HTML* елемент, на пример:

.. code-block:: html

    <p style="padding:1.5em;font-size:1.25em;color:#fff;background-color:#0f0">
        Неки текст.
    </p>

Задавање стила помоћу атрибута ``style`` у HTML елементу је познато као инлајн стил (енгл. *inline CSS*).

Употреба *HTML* елемента ``<style>`` у заглављу веб стране и атрибута ``style`` у њеним елементима **се данас сматра лошом праксом и не треба их користити при дизајнирању сајтова**. Овакав начин задавања стила може узроковати неконзистентност у изгледу страна и захтева експертско знање да би се идентификовали проблеми. Овај приступ је имао више смисла у почетку развоја веба, када је због спорог интернета било важно да се све што је потребно за дефинисање изгледа и садржаја стране налази у једном фајлу, и када су сајтови били мањи и једноставнији него данас.

Овај начин дефинисања стилова и даље може бити погодан за једноставне примере, у којима се у једном документу у потпуности дефинише и структура и изглед стране. Ми ћемо за наше примере користити овај начин у наставку, а сличне примере можете наћи и на сајтовима као што је *W3CSchools*. 

Још једном наглашавамо да у пројектима који садрже више страна (на пример, ако правите једноставан сајт ради вежбе) треба да користите само препоручени начин рада, а то је држање *CSS* кода у посебном фајлу.
