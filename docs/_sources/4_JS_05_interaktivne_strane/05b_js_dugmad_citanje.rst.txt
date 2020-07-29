Дугмад
======

Догађаји се дешавају на неким *HTML* елементима и на њима се постављају *JavaScript* функције које реагују на те догађаје и врше акције. У примерима у претходној секцији смо директно постављали функције на елементе на којима ће се дешавати догађаји. У правим веб странама ћете често имати случајеве где би требало да поставите некакво дугме на које треба кликнути да би се покренула акција

.. code-block:: html

    <button type="button">Кликни на ово дугме</button>

Као и у случају претходних елемената, на ово дугме се може поставити функција која би требало да буде извршена када неко кликне на дугме:

.. code-block:: html

    <button type="button" onclick="mojaFunkcija(`prikazi`)" >Кликни на ово дугме</button>

У претходним примерима смо функцији предавали објекат на којем се десио догађај (предат као параметар ``this``), како би функција која ће бити позвана могла лакше да приступи објекту који ју је позвао и да га измени или прочита неке информације из њега. У случају дугмади се ретко прослеђује референца на дугме и чешће се позива функција без параметара или се прослеђује неки стринг или број који само говори функцији шта треба да уради. У овом случају је прослеђен стринг ``prikazi``. 

Случају да користите *Twitter Bootstrap* за стилизовање страна, можете лако да примените различите стилове за дугмад, као на пример:

.. image:: ../../_images/bootstrap/dugmad_stil.png
    :width: 624px
    :align: center

Примарни и секундарни стилови дугмета су стилови који се најчешће користе на странама. Често би требало да обележите неку дугмад тако да означите да је то дугме које треба да се притисне да би се успешно извршила нека акција (енгл. *success*) или да ће се десити нека потенцијално опасна акција или акција која ће приказати упозорење. 

Дугмад се могу лако стилизовати помоћу библиотеке *Twitter Bootstrap* додавањем класа ``btn-primary``, ``btn-secondary``, ``btn-success``, ``btn-danger`` и слично као што је приказано у следећем примеру:

.. code-block:: html

    <button type="button" class="btn btn-primary">Primary</button>
    <button type="button" class="btn btn-secondary">Secondary</button>
    <button type="button" class="btn btn-success">Success</button>
    <button type="button" class="btn btn-info">Info</button>
    <button type="button" class="btn btn-warning">Warning</button>
    <button type="button" class="btn btn-danger">Danger</button>
    <button type="button" class="btn btn-dark">Dark</button>
    <button type="button" class="btn btn-light">Light</button>
    <button type="button" class="btn btn-link">Link</button>

Када поставите неко од оваквих дугмади на страну, на њега можете поставити функцију која ће бити извршена када се притисне дугме, као на пример:

.. code-block:: html

    <button type="button" class="btn btn-primary" onclick="mojaFunkcija()">Притисни ово дугме</button>

Више информација о дугмади можете наћи на 
*w3schools* страни `о дугметима <https://www.w3schools.com/bootstrap4/bootstrap_buttons.asp>`_ или 
*Bootstrap* `документацији о дугметима <https://getbootstrap.com/docs/4.1/components/buttons/>`_.

Пример – ћир/лат
''''''''''''''''

У веб страни о Николи Тесли се налазе заглавља, пасуси и остали *HTML* елементи који садрже текст написан или на ћирилици или латиници. Елементи који садрже текст на ћирилици имају класу ``cirilica`` и приказани су, док елементи који садрже текст на латиници имају класу ``latinica`` и иницијално су сакривени.

.. code-block:: html

    <h1 class="cirilica">Биографија</h1>
    <h1 class="latinica">Biografija</h1>
    <p class="cirilica">…</p>
    <p class="latinica">…</p>
    <h1 class="cirilica">Остало</h1>
    <h1 class="latinica">Ostalo</h1>
    <p class="cirilica">…</p>
    <p class="latinica">…</p>
    <h1 class="cirilica">Референце</h1>
    <h1 class="latinica">Reference</h1>
    <p class="cirilica">...</p>
    <p class="latinica">…</p>

Потребно је поставити два дугмета којима би посетилац стране могао да бира да ли жели да чита садржај на ћирилици и латиници. 

.. code-block:: html

    <button type="button" class="btn btn-primary" onclick="postaviJezik(`cirilica`)">Ћирилица</button>
    <button type="button" class="btn btn-secondary" onclick="postaviJezik(`latinica`)">Латиница</button>

Функција која реагује на притисак на дугме које приказује текст на латиници, а сакрива текст на ћирилици је приказан у следећем примеру:
function postaviJezik(jezik) {

.. code-block:: javascript

      if( `latinica` == jezik )
          latinica();
      else
          cirilica();
    }

    function latinica() {

      latinica = document.querySelectorAll(".latinica");

      i = 0
      while ( i < latinica.length ) {
          let element = latinica[i];
              element.style.visibility = `hidden`;
          i = i + 1;
      }

      cirilica = document.querySelectorAll(".cirilica");
      i = 0
      while ( i < cirilica.length ) {
          let element = cirilica[i];
              element.style.visibility = `visible`;
          i = i + 1;
      }
    }

Елементи у страни се могу приказивати или сакривати тако што им се промени вредност стила ``visibility`` на ``visible`` или ``hidden``. Веома слично би изгледала функција која приказује текст на ћирилици, а сакрива текст на латиници. Више информација о својству ``visibility`` можете наћи на `w3schools <https://www.w3schools.com/jsref/prop_style_visibility.asp>`_ сајту.

Задатак ћир/лат
'''''''''''''''

Напишите *HTML* код овакве стране у коју ћете укључити библиотеку *Twitter Bootstrap* и дефинишете функције које приказују текст на латиници односно ћирилици. Обратите пажњу на чињеницу да сви елементи који имају класу ``latinica`` морају да иницијално буду сакривени, тако да бисте вероватно морали да у дефиницију класе латиница поставите *CSS* својство ``visibility: hidden`` у овој класи.

