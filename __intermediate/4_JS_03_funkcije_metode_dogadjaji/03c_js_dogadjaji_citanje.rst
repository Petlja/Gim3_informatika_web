Догађаји
========

.. comment

    izmestiti
  

*JavaScript* програмски кôд даје живот веб странама и омогућава нам да додамо акције којима ћемо реаговати на догађаје. *JavaScript* нам омогућава да дефинишемо каква акција треба да се изврши када се нешто деси у веб страни или на неком њеном елементу. Примери таквих догађаја су: завршено учитавање веб стране, клик на неки елемент, прелазак мишем преко неког елемента, истек неког задатог времена и слично.

Догађаји на елементима стране
-----------------------------

Да бисмо омогућили реаговање на догађаје, потребно је да некако повежемо изабрани догађај са *JavaScript* функцијом која ће се извршити при настанку тог догађаја. 

Када се ради о догађајима који се дешавају на одређеном *HTML* елементу, један начин да повежемо догађаје са *JavaScript* функцијама је
да том елементу додамо атрибут који одговара изабраном догађају, а као вредност атрибута упишемо позив *JavaScript* функције која се том догађају придружује. Примери атрибута којима се догађаји повезују са акцијама су:

.. csv-table:: Атрибути и догађаји
    :header: "Атрибут", "Догађај"
    :widths: 20, 80
    :align: left

    ``onclick``,      "Клик мишем на *HTML* елемент"
    ``onmouseover``,  "Прелазак мишем преко *HTML* елемента"
    ``onmouseout``,   "Излазак (показивача) миша из области елемента"
    ``onkeydown``,    "Притисак на тастер на тастатури (док је дати *HTML* елемент у фокусу)"
    ``onchange``,     "Промена *HTML* елемента. Ово је догађај којие се углавном користи на елементима за унос података, о чему ће бити речи ускоро."

Следећи *HTML* кôд садржи комплетан пример. Покрените га и испробајте функционисање догађаја.

.. activecode:: dogadjaji_paragraf_html
    :language: html
    :nocodelens:
    
    <!DOCTYPE html>
    <html>
        <head>
            <title>Догађаји</title>
            <script>

                function klik(element) {
                    alert(`Кликнули сте на параграф у коме пише "${element.innerText}"`);
                }
                
                function prelazak(element) {
                    alert(`Прешли сте преко параграфа у коме пише "${element.innerText}"`);
                }
                
            </script>
        </head>
        <body>
            <h2>Пример дефинисања догађаја</h2>

            <p onclick="klik(this)">Кликни на овај параграф.</p>
            <p onmouseover="prelazak(this)">Пређи мишем преко овог параграфа.</p>
            <p onclick="klik(this)" onmouseover="prelazak(this)">Кликни или пређи мишем преко овог параграфа.</p>
         </body>
    </html>

У овом примеру функције ``klik`` и ``prelazak`` се позивају на одговарајући догађај и као параметар добијају *HTML* елемент на коме се десио тај догађај. На тај начин функција "зна" одакле је позвана и може да прочита вредности атрибута или текстуални садржај прослеђеног елемента. Аргумент ``this`` увек означава сам *HTML* елемент у коме се ``this`` помиње, то јест елемент на коме се десио догађај (тачније, ``this`` означава *JavaScript* објекат који представља поменути *HTML* елемент). На пример, у контексту


.. code-block:: html

    <p onclick="klik(this)">Кликни на овај параграф.</p>

аргумент ``this`` представља параграф у коме пише "Кликни на овај параграф." (у облику *JavaScript* објекта).

*JavaScript* објекти који представљају *HTML* елементе имају поље ``innerHTML``, које представља садржај елемента. Коришћењем овог поља, функција може не само да чита него и да мења садржај елемента. Испробајте!


Остали догађаји
---------------

Неки догађаји нису везани за одређени *HTML* елемент. У том случају можемо да користимо методу ``document.addEventListener`` да бисмо повезали дати догађај са *JavaScript* кодом који се на тај догађај извршава. Ова метода има два аргумента: назив догађаја и назив функције коју на тај догађај желимо да извршимо.

.. comment

    ``onload`` дешава се када се учита страна.

На пример, догађај ``DOMContentLoaded`` наступа када се садржај стане учита у објектни модел. Овом догађају можемо да придружимо функцију ``postavi`` на следећи начин:

.. code-block:: javascript

    document.addEventListener('DOMContentLoaded', postavi);

Овим постижемо да се функција ``postavi`` изврши након учитавања стране у објектни модел. На овај начин можемо да извршавамо и разна почетна подешавања изгледа и садржаја веб стране из *JavaScript* кода убрзо по отварању те стране.

Осим методе ``document.addEventListener`` можемо да користимо и методу ``setInterval``. Ова метода се користи када неку *JavaScript* функцију желимо да извршавамо периодично, на сваких *n* милиисекунди. Први аргумент методе ``setInterval`` је име функције коју извршавамо, а други аргумент је интервал у милиисекундама између узастопних покретања методе. Извршавањем методе ``setInterval`` постижемо да се догађај часовника који је повезан са наведеном *JavaScript* функцијом генерише у задатим интервалима. На пример, позивом

.. code-block:: javascript

    setInterval(tik, 1000);

постижемо да се догађај који покреће функцију ``tik`` генерише на сваких 1000 милиисекунди, тј. једном у секунди. Свако генерисање овог доагађаја покреће функцију ``tik``.

Ако постоји потреба да се касније престане са генерисањем овог догађаја, запамтићемо вредност коју враћа метода ``setInterval``:

.. code-block:: javascript

    tiktanje = setInterval(tik, 1000);

а на другом месту у коду можемо на овај начин да прекинемо са генерисањем догађаја који покреће функцију ``tik``:

.. code-block:: javascript

    clearInterval(tiktanje);

Следи комплетан пример који илуструје употребу метода ``document.addEventListener`` и ``clearInterval``. Испробајте га!

.. activecode:: casovnik_html
    :language: html
    :nocodelens:

    <!DOCTYPE html>
    <html>
        <head>
            <title>Часовник</title>
            <script>

                function tik() {
                    document.querySelector('h1').innerHTML = `${new Date().toLocaleTimeString()}`;
                }
                
                function postavi() {
                    setInterval(tik, 1000);
                }

                document.addEventListener('DOMContentLoaded', postavi);

            </script>
        </head>
        <body>
            <h1></h1>
        </body>
    </html>

.. comment

    Пример – тренутно време
    -----------------------

    Потребно је направити веб страну у којој ће се налазити једно заглавље (нпр. елемент <h1>). Када корисник пређе мишем преко тог заглавље потребно је приказати тренутно време у њему.

    .. code-block:: html

        <!DOCTYPE html>
        <html>
        <body>

        <h1 onmouseover="prikaziVreme(this)">Пређи мишем да видиш колико је сати!</h1>

        <script>
        function prikaziVreme(zaglavlje) {
          zaglavlje.innerHTML = `${new Date().toLocaleString()}. Пређи мишем опет!`;
        }
        </script>
        </body>
        </html>

Пример - повећавање слике
'''''''''''''''''''''''''

У следећем примеру дата је веб страна са ове 3 слике:

.. image:: ../../_images/js/emo1.png
    :width: 100px
.. image:: ../../_images/js/emo2.png
    :width: 100px
.. image:: ../../_images/js/emo3.png
    :width: 100px


За сваку слику догађај наиласка мишем на слику (``onmouseover``) и догађај одласка миша из области слике (``onmouseout``) повезани су са функцијом која мења величину слике. Конкретно, при наиласку мишем на слику, она постаје два пута већа од њене природне величине, а при одласку миша са слике она се враћа на природну величину.

.. activecode:: vece_i_manje_slike_html
    :language: html
    :nocodelens:

    <!DOCTYPE html>
    <html lang="sr">
        <head>
            <title>Слике</title>
            <script>

                // funkcija menja velicinu slike
                function vel(slika, faktor) {
                    slika.style.width = `${slika.naturalWidth * faktor}px`;
                    slika.style.height = `${slika.naturalHeight * faktor}px`;
                }

            </script>
        </head>
        <body>
            <h2>Повећававање и смањивање слика</h2>
           
            <img onmouseover="vel(this, 2)" onmouseout="vel(this, 1)" src="../_images/emo1.png">
            <img onmouseover="vel(this, 2)" onmouseout="vel(this, 1)" src="../_images/emo2.png">
            <img onmouseover="vel(this, 2)" onmouseout="vel(this, 1)" src="../_images/emo3.png">

            <p> Позиционирањем миша на слику, она се увећава. </p>
         </body>
    </html>

.. comment

    Пример – повећај слику
    ----------------------

    У примеру са низовима смо видели код који пролази кроз све слике на веб страни Потребно је направити веб страну у којој ће се налазити неколико слика (тј. елемент <img>). Kада корисник да кликне на слику потребно је повећати јој димензије два пута.

    .. code-block:: html

        <!DOCTYPE html>
        <html>
        <head>

        <script>

        function popraviSlike() {
          slike = document.images;
          i = 0
          while ( i < slike.length ) {
              let slika = slike[i];
                  if ( undefined == slike.title ) {
                     slika.title = slika.alt;
                  }
              i = i + 1
          }
        }
        </script>

        </head>
        <body onclick="popraviSlike(this)">

        <img src="…" alt="Prva slika" title="Prva slika" />
        <img src="…" alt="Druga slika" />
        <img src="…" alt="Treca slika" title="Treca slika" />
        <img src="…" alt="Cetvrta slika" />

        </body>
        </html>
