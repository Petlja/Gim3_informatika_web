Bootstrap подршка компонентама
==============================

Погодним стилизовањем и распоређивањем већ познатих *HTML* елемената можемо да градимо сложеније функционалне целине, као што су табови, менији, галерије слика, картице, формулари и слично. Такве функционалне целине се често и визуелно издвајају на веб странама и лако се уочавају. Ове визуелне и функционалне целине називамо **компонентама** на веб страни. 

Компоненте могу бити:

- Основне компоненте, које представљају стандардне *HTML* елементе као што су поља за унос, листе или табеле.
- Сложене компоненте, које градимо користећи једну или више једноставнијих компоненти. Груписањем компоненти на неки од уобичајених начина добијамо поменуте често коришћене конструкције (табови, менији, галерије слика, картице...).

Једна од највећих вредности *Twitter Bootstrap* библиотеке је могућност једноставног стилизовања и мењања стила често коришћених компоненти, што смо већ имали прилике да видимо. Када желите да упознате ефекте појединих стилова основних компоненти као што су табеле или поља за унос, треба само да пронађете стил који вас интересује, копирате пример *HTML* кода и ставите га у своју страну. Ако вам стил одговара и желите да га употребите, у великом броју случајева ће бити довољно само да промените садржај у компоненти. 

Поред конзистентног стилизовања основних компоненти, у *Twitter Bootstrap* библиотеци можемо наћи неке врло корисне стилове за формирање сложених компоненти. У наставку ће бити описане неке од сложених компоненти које можемо једноставно дизајнирати помоћу ове библиотеке.

Навигационе траке
-----------------

Навигационе траке (*Navbar*, скраћено од енгл. *navigation bar*) су компоненте које се налазе на врху стране и садрже меније, логое и поља за претрагу која се виде на многим веб странама.

.. image:: ../../_images/bootstrap/navbar.png
    :width: 600px
    :align: center

Када вам буде била потребна оваква компонента, довољно је само да убаците *HTML* кôд сличан овом:

.. code-block:: html

    <nav class="navbar navbar-light bg-light">
      <a href="https://petlja.org" class="navbar-brand">Линк 1</a>
      <a href="https://petlja.org" class="navbar-brand">Линк 2</a>
      <form class="form-inline">
        <input class="form-control mr-sm-2" type="search" placeholder="тражени појам" aria-label="Search">
        <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Тражи</button>
      </form>
    </nav>

Из примера видимо да је навигациона линија у суштини *HTML* елемент који се зове ``<nav>`` блок, а са којим смо се упознали у секцији о распореду елемената. Да би ``<nav>`` блок изгледао као навигациона линија са слике, потребно је ддоелити му одговарајуће *CSS* класе. 

У овом блоку се налазе два линка, поље за претрагу и дугме којим се може претражити сајт (ако би била имплементирана функционалност претраге).

Страничење
----------

Страничење (енгл. *pagination*) је често коришћена компонента која се ставља на странама где се не приказују сви резултати, него је потребно преласком на следећу страну приказати нови скуп резултата. Пример једне компоненте за страничење која омогућава да се преће на претходну или следећу страну или да се директно пређе на прву, другу или трећу страну је приказана на слици:

.. image:: ../../_images/bootstrap/stranicenje.png
    :width: 400px
    :align: center

|

Ако вам је потребно да ставите компоненту за страничење на неку страну, довољно је да напишете *HTML* кôд приказан у следећем примеру:

.. code-block:: html

    <nav aria-label="Пример страничења">
      <ul class="pagination">
        <li class="page-item"><a class="page-link" href="#">претходна</a></li>
        <li class="page-item"><a class="page-link" href="#">4</a></li>
        <li class="page-item"><a class="page-link" href="#">5</a></li>
        <li class="page-item"><a class="page-link" href="#">6</a></li>
        <li class="page-item"><a class="page-link" href="#">следећа</a></li>
      </ul>
    </nav>

Као што видимо, у *HTML* треба у ``<nav>`` блок поставити обичне ``<ul>`` листе и додати одговарајуће *CSS* класе као што су ``pagination``, ``page-item``, чиме се добија стилизована контрола за страничење резултата.

Картице
-------

Картице (енгл. *Cards*) су компоненте помоћу којих издвајамо независне целине у садржају. Често је главна функционалност картице да омогући везу ка другој веб страни. При томе, за разлику од обичног линка, картица може да садржи више елемената, као што су наслов, слика, краћи текст о страни на коју упућује, дугме које води ка тој страни итд.

.. image:: ../../_images/bootstrap/kartica.png
    :width: 160px
    :align: center

*HTML* кôд овакве компоненте је приказан у следећем примеру:

.. code-block:: html

    <div class="card" style="width: 12rem;">
      <img src="petlja_logo.png" class="card-img-top" alt="Текст за приказ уместо слике на врху картице">
      <div class="card-body">
        <h5 class="card-title">Наслов картице</h5>
        <p class="card-text">Текст који ће бити приказан у оквиру картице.</p>
        <a href="#" class="btn btn-primary">Дугме на дну картице</a>
      </div>
    </div>

Из датог примера видимо како можемо да направимо картицу: у један ``<div>`` блок постављамо *HTML* елементе за наслов (таг ``<h>``), пасус текста (таг ``<p>``) и линк (таг ``<а>``), уз одговарајуће *CSS* класе. У овом примеру, линк је помоћу класе ``btn btn-primary`` стилизован као дугме. Захваљујући *Twitter Bootstrap* класама, прегледач ће ову структуру приказати као стилизовану контролу приказану изнад.

Медијски објекат
----------------

Медијски објекат је сличан картици приказаној у претходном примеру, с тим да је овдде сличица обично мања и постављена у линији са текстом, као што је приказано на следећој слици:

.. image:: ../../_images/bootstrap/medijski_objekat.png
    :width: 600px
    :align: center

*HTML* кôд овакве компоненте приказан је у следећем примеру:

.. code-block:: html

    <div class="media">
      <img src="petlja_logo.png" class="mr-3" alt="Сличица која ће бити са леве стране">
      <div class="media-body">
        <h5 class="mt-0">Наслов изнад текста објекат</h5>
          Испод наслова се може ставити текст који ће бити приказан у оквиру објеката.
          Текст може бити толико дугачак да пређе висину слике, 
          а у овом примеру текст се не наставља испод слике, већ само десно од слике, 
          заузимајући свуда исту ширину.
      </div>
    </div>

Као што се може приметити, *HTML* кôд је веома сличан претходном. Кључна разлика је употреба другачијих *CSS* класа (``media``, ``media-body``), чиме се добија потпуно другачији приказ.

Дијалози
--------

Једна од најчешће коришћених компоненти у веб апликацијама је дијалог који приказује формулар или текст. Веб страна се обично дизајнира тако да се дијалог добија када се кликне на неко дугме у страни.

.. image:: ../../_images/bootstrap/dijalog_dugme.png
    :width: 600px
    :align: center

Након клика, дијалог се приказује преко осталих компоненти, док је остатак стране затамњен и неактиван.

.. image:: ../../_images/bootstrap/dijalog.png
    :width: 600px
    :align: center

Уз помоћ *Twitter Bootstrap* библиотеке се дијалог и дугме које га отвара лако имплементирају у *HTML* коду приказаном у следећем коду. Прво је потребно поставити дугме које треба притиснути како би се отворио дијалог. Довољно је додати једно дугме (*HTML* елемент ``button``) са атрибутом ``data-toggle`` и вредношћу ``modal``, које ће у атрибуту ``data-target`` имати идентификатор дијалога којег треба да отвори (у овом случају ``ПримерМодалногДијалога``). 

Потом је у наставку потребно додати *HTML* кôд којим се представља садржај дијалога који ће бити приказан када се притисне дугме. Овај елемент мора да има вредност идентификатора која се слаже са вредношћу из атрибута ``data-target`` дугмета које покреће дијалог.

.. code-block:: html

    <!-- Дугме које ће отворити модални диалог -->
    <button type="button" class="btn btn-primary" 
            data-toggle="modal" data-target="#ПримерМодалногДијалога">
      Прикажи модални прозор за дијалог
    </button>
    <p>Остали садржај стране</p>

    <!-- Структура модалног дијалога -->
    <div class="modal fade" id="ПримерМодалногДијалога" tabindex="-1" role="dialog" 
        aria-labelledby="ПримерОзнакеНаслова" aria-hidden="true">
      <div class="modal-dialog" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="ПримерОзнакеНаслова">Наслов дијалога</h5>
          </div>
          <div class="modal-body">
            Садржај дијалога
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-dismiss="modal">Затвори</button>
            <button type="button" class="btn btn-primary">Сачувај податке</button>
          </div>
        </div>
      </div>
    </div>


У ``<div>`` блок који представља садржај дијалога се могу додати различити елементи којима ће се направити бољи изглед дијалога. На пример, ако се дода ``<div>`` са класом ``modal-header``, садржај у њему ће се приказати као заглавље унутар дијалога. Садржај у  ``<div>`` блоку са класом ``modal-footer`` ће се приказати на дну дијалога. На овај начин се веома лако може направити изглед дијалога који вам је потребан.

Закључак
--------

У овој лекцији сте могли да видите неколико уграђених компоненти и кôд који треба да ставите у страну како би те компоненте биле приказане. Могућност да једноставно ископирате компоненте и слажете их у веб страну су једна од највећих олакшица у библиотеци *Twitter Bootstrap*. Компоненте приказане у овој секцији су само неке од оних које су на располагању као што су ``Alerts``, ``Badge``, ``Breadcrumb``, ``Buttons``, ``Button group``, ``Card``, ``Carousel``, ``Collapse``, ``Dropdowns``, ``Forms``, ``Input group``, ``Jumbotron``, ``List group``, ``Media object``, ``Modal``, ``Navs``, ``Navbar``, ``Pagination``, ``Popovers``, ``Progress``, ``Scrollspy``, ``Spinners``, ``Toasts`` и ``Tooltips``. Погледајте ове компоненте и пронађите неке занимљиве, пошто ће вам користити да знате да нека компонента постоји у случају да приметите да је потребна на веб страни.
