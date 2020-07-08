CSS селектори - питања
======================

.. mchoice:: selektori_q1
    :answer_a: Дефинишу на које елементе треба применити скуп CSS својстава.
    :answer_b: Дефинишу који елементи се могу смештати у друге елементе.
    :answer_c: Раздвајају CSS својства.
    :answer_d: Дефинишу која својства треба применити на дати елемент.
    :correct: a
    :feedback_a: Тачно!
    :feedback_b: Не.
    :feedback_c: Не.
    :feedback_d: Не.

    Чему служе *CSS* селектори?



.. mchoice:: selektori_q2
    :answer_a: Када имамо само један елемент одређеног типа на веб страни.
    :answer_b: Када за неки елемент желимо да задамо посебан стил, различит од осталих.
    :answer_c: Када имамо више елемената истог типа на веб страни.
    :answer_d: Када има елемената који не припадају ни једној класи.
    :correct: b
    :feedback_a: Не.
    :feedback_b: Тачно!
    :feedback_c: Не.
    :feedback_d: Не.

    У ком случају дефинишемо стил за идентификатор?



.. mchoice:: selektori_q3
    :answer_a: Блок број 1
    :answer_b: Блок број 2
    :answer_c: Блок број 9
    :answer_d: Ни један од понуђених
    :correct: b
    :feedback_a: Не.
    :feedback_b: Тачно!
    :feedback_c: Не.
    :feedback_d: Не.

    Који од блокова са слике је најбоље стилизовати користећи идентификатор?
    
    .. image:: ../../_images/css/selektori_test3.png
        :width: 500px
        :align: center



.. mchoice:: selektori_q4
    :answer_a: Свих 5 блокова.
    :answer_b: Блокове 1 и 2.
    :answer_c: За ове блокове класа није погодан начин стилизовања.
    :answer_d: Блокове 3, 4 и 5.
    :correct: d
    :feedback_a: Не.
    :feedback_b: Не.
    :feedback_c: Не.
    :feedback_d: Тачно!

    Које од блокова са слике је најбоље стилизовати користећи класу?
    
    .. image:: ../../_images/css/selektori_test4.png
        :width: 500px
        :align: center



.. mchoice:: selektori_q5
    :answer_a: <br/>.prva.kolona {background-color:darkgray;}<br/>.druga.kolona {background-color:lightblue;}<br/>.treca.kolona {background-color:lightgreen;}
    :answer_b: <br/>.kolona {float:left; max-width:180px; padding:10px;}<br/>.prva {background-color:darkgray;}<br/>.druga {background-color:lightblue;}<br/>.treca {background-color:lightgreen;}
    :answer_c: <br/>.kolona {float:left; max-width:180px; padding:10px;}<br/>.prva kolona {background-color:darkgray;}<br/>.druga kolona {background-color:lightblue;}<br/>.treca kolona {background-color:lightgreen;}
    :correct: b
    :feedback_a: Не.
    :feedback_b: Тачно!
    :feedback_c: Не.

    Ово је део *HTML* кôда једне веб стране.

    .. code-block:: html

        <body>
          <div class="prva kolona"> <h2> HTML </h2> <p> elementi, liste, tabele, hiperveze, multimedija </p> </div>
          <div class="druga kolona"> <h2> CSS </h2> <p> CSS stilovi, svojstva, selektori, raspored </p> </div>
          <div class="treca kolona"> <h2> Bootstrap </h2> <p> Biblioteka, klase, komponente, raspored </p> </div>
        </body>

    Који од понуђених стилова даје изглед у прегледачу као на следећој слици?
    
    .. image:: ../../_images/css/selektori_test5.png
        :width: 600px
        :align: center
    