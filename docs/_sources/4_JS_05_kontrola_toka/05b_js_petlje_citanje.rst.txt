Петље
=====

Петље су наредбе које омогућавају понављање других наредби. То значи да су петље сложене наредбе, које у себи могу да садрже друге наредбе. Свако понављање тих наредби садржаних у петљи називамо итерацијом. Уместо речи петља често се користи и реч циклус (у програмирању су овде речи синоними). 

У језику *JavaScript* постоји више врста петљи, а сада ћемо упознати неке од њих.

While петља
-----------

Општи облик *while* наредбе је:

.. code-block:: javascript

    while (услов) {
        тело
    }

Ова наредба дословно значи: "док је испуњен услов, извршавај тело". Овде *услов* представља било какав израз логичког типа, дакле нешто што је тачно или нетачно (има вредност *true* или *false*), а *тело* представља једну или више било којих наредби језика *JavaScript*. Ако је у телу петље само једна наредба, витичасте заграде могу да се изоставе, али је уобичајена пракса да се не изостављају. 

.. image:: ../../_images/js/while_naredba.png
    :width: 400px
    :align: center

Наредба понављања *while* је веома слична наредби *if*. Разлика је у томе што у наредби *while* понављамо наредбе док је услов испуњен, а у *if* наредби извршимо те наредбе само једном ако је услов испуњен.

.. questionnote::

    **Пример - збир непарних двоцифрених бројева**
    
    Написати програм који прихвата цео број и израчунава збир свих непарних бројева до задатог броја. 
    
Ево како задатак можемо да решимо помоћи петље *while*:

.. activecode:: zbir_dvocifrenih_neparnih_while_js
    :language: javascript
    :nocodelens:

    let broj = 11;
    let zbir = 0;
    let granica = parseInt(prompt(`Унесите границу`));
    granica = Math.min(granica, 99);
    while (broj <= granica) {
        zbir += broj;
        broj += 2;
    }
    alert (`Збир двоцифрених непарних бројева до ${granica} је ${zbir}`);

Прво смо поставили почетне вредности за први непаран двоцифрени број (11) и збир (на почетку је нула). Пошто се унесе број који представља границу, у *while* петљи се пре сваког додавања броја на збир проверава да ли је непарнан број и даље мањи од границе. Ако јесте, настављамо да извршавамо наредбе између витичастих заграда - тренутни непаран број се додаје на збир, а сам број повећавамо за два.

For петља
---------

Општи облик петље `for` је:

.. code-block:: javascript

    for (иницијализација; услов; корак) {
        тело
    }

Овако написана *for* наредба ради исто што и

.. code-block:: javascript

    иницијализација
    while(услов)
    {
        тело
        корак
    }

Значи, прво се извршава наредба коју смо овде назвали *иницијализација*, затим се проверава услов и док год је он испуњен, понављају се тело петље и наредба коју смо назвали *корак*. Према томе, претходни задатак можемо да решимо и овако:

.. activecode:: zbir_dvocifrenih_neparnih_for_js
    :language: javascript
    :nocodelens:

    let zbir = 0;
    let granica = parseInt(prompt(`Унесите границу`));
    granica = Math.min(granica, 99);
    for (let broj = 11; broj <= granica; broj = broj + 2) {
        zbir = zbir + broj;
    }
    alert (`Збир двоцифрених непарних бројева до ${granica} је ${zbir}`);

Овај облик петље *for* је постоји и у програмским језицима *C*, *C++*, *C#*, *Java* и другим. У језику *JavaScript* се не користи много, јер за извршавање одређених наредби над сваким елементом сложене променљиве постоје посебни облици петље *for*, које ћемо упознати када будемо говорили о сложеним променљивим.

.. comment

    https://www.w3schools.com/js/js_loop_for.asp
    
    - while - loops through a block of code while a specified condition is true
        while (i < 10) {
            text += "The number is " + i;
            i++;
        }
        
        do {
            text += "The number is " + i;
            i++;
        }
        while (i < 10);
    
    - do/while - also loops through a block of code while a specified condition is true
    
    - for - loops through a block of code a number of times
        for (i = 0; i < 5; i++) { 
            text += "The number is " + i + "<br>"; 
        }


        for (i = 0, len = cars.length, text = ""; i < len; i++) { 
            text += cars[i] + "<br>"; 
        }
    
    - for/in - loops through the properties of an object
        var person = {fname: "John", lname: "Doe", age: 25};
        var text = "";
        var x;
        for (x in person) {
            text += person[x]; 
        }
    
    - for/of - loops through the values of an iterable object
        var cars = ['BMW', 'Volvo', 'Mini'];
        var x;
        for (x of cars) {
            document.write(x + "<br>");
        }
        

        var txt = 'JavaScript';
        var x;        
        for (x of txt) {
            document.write(x + "<br >");
        }