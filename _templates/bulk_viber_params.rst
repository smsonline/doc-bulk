<!-- Шаблон с базовыми параметрами для Viber -->
<!--
==================== ======================== ================================================================================
Параметр             Тип                      Описание
==================== ======================== ================================================================================
-->
user                 String                   Логин партнёра.
from                 String |nbsp| (11)       Альфа-имя отправителя сообщения – цифры или латинские символы
phone[1..n]          Number                   Номер телефона получателя в международном формате: только цифры, без знака «плюс»,
                                              код страны, код оператора, телефон. Если необходимо отправить сообщение на
                                              несколько номеров, то требуется передавать несколько полей «phone» 
sign                 String                   `Цифровая подпись`_
sending_method       String                   Должно быть значение: viber

**Опциональные параметры**
------------------------------------------------------------------------------------------------------------------------------
p_transaction_id     String                   Идентификатор транзакции в системе партнёра. Используется для сверок статистики и
                                              передаётся партнёру при передаче уведомлений о доставке
charset              String                   Кодировка параметра txt:

                                              * UTF8 или UTF-8 (по умолчанию) – явное указание кодировки Unicode UTF-8
                                              * UTF-16BE или UCS-2 – кодировка Unicode UTF-16 Big Endian
                                              * CP1251 – явное указание кодировки Windows-1251
delay                Number                   Отложить отправку сообщения абоненту на указанное количество минут.

                                              Максимальное значение – 10080 (неделя).
dlr                  Number                   Отчёт о доставке сообщения:

                                              * 0 (по умолчанию) – без отчета о доставке сообщения
                                              * 1 – запросить отчет о доставке сообщения (см. п. 5)
dlr_timeout          Number                   Время в секундах, в течение которого интересует доставка сообщения.

                                              Минимальное значение – 60 (одна минута).

                                              Максимальное значение – 86400 (24 часа). 

                                              Значение dlr_timeout округляется до минут, в меньшую сторону.

                                              В случае, если не указано, считается, что dlr_timeout равен 14 дням.
                                              
                                              Этот параметр используется для того, чтобы оперативно отправлять сообщения по
                                              каналу, отличному от Viber (SMS, USSD или подобное)
expiry_txt           String                   Текст, который показывается пользователю по истечении dlr_timeout.

                                              Показывается только пользователям с iOS.

                                              По умолчанию: значение параметра txt (если передан) или 
                                              "This message has expired" (если txt не передан).
<!--
==================== ======================== ================================================================================
-->