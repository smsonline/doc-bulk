Примеры работы с системой рассылок
============


Примеры взаимодействия с API (на Perl и PHP) вы можете найти на github.com:  https://github.com/smsonline/samples/tree/master/Bulk

Пример GET-запроса:

.. code-block:: none

    https://bulk.sms-online.com/?user=hitfm&from=HitFM&phone=79031234567&txt=%D0%A1%D1%8A%D0%B5%D1%88%D1%8C%20%D0%B5%D1%89%D0%B5%20%D1%8D%D1%82%D0%B8%D1%85%20%D1%84%D1%80%D0%B0%D0%BD%D1%86%D1%83%D0%B7%D1%81%D0%BA%D0%B8%D1%85%20%D0%B1%D1%83%D0%BB%D0%BE%D0%BA&sign=29def94e0f987855bbf4407e93b088d7

При передаче параметра «txt», содержащего спецсимволы (в том числе, пробел), его нужно закодировать URI при помощи функции rawurlencode() или аналогичной. 

В вышеприведённом примере параметр «txt» содержит строку «Съешь еще этих французских булок».

Если запрос соответствует протоколу, то ответ скрипта будет таким:

.. code-block:: xml

    <?xml version="1.0" encoding="utf-8"?>
    <response>
      <code>0</code>
      <tech_message>OK</tech_message>
    </response>

Если произошла ошибка, то параметр «code» будет меньше нуля (см. п. 7.1). В этом случае поле «tech_message» содержит текстовое описание ошибки. Пример:

.. code-block:: xml

    <?xml version="1.0" encoding="utf-8"?>
    <response>
      <code>-1</code>
      <tech_message>PARAM ERROR (phone)</tech_message>
    </response>

По умолчанию установлено ограничение для SMS рассылок: 10 SMS/секунду. Если требуется более высокая скорость – сообщите об этом вашему менеджеру.