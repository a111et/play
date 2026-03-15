# Устройство: Poco F6 | Прошивка: Project Infinity X v3.7
--- 
## Мой гайд это просто что я сделал что я получил 3 ✅ (MEETS_DEVICE_INTEGRITY, MEETS_BASIC_INTEGRITY и MEETS_STRONG_INTEGRITY) на своём устройстве 
## Google pay карты легко добавляют и работает в норме с банками проблем нету у меня есть 2 украинских банка и 2 польских ничего не говорят всё в норме игры которые ругаются на рут и play Integrity не попадались 
--- 
1. Я выключил весь встроенные спуфинг Spoof Google Play, Spoof Netflix/Snapchat/Games и т.д если есть 
`Spoof Google Photos, я оставил ибо регулярно выгружаю фотографии в облако`
2. Установил *KernelSU Next spoofed* v 3.1.0 (через `init_boot.img` из моей прошивки) 
3. Установил Zygisk Next v1.3.2 и включил там 
`Use anonymous memory и Use Zygisk Next linker и Denylist Policy переключил на Disabled`
4. Установил *Play Integrity Fix* v35 модифицированную версию от t.me/keybox_xml 
5. Установил *TEESimulator* v3.2 от JingMatrix
6. Установил *Tricky Addon Enhanced* v4.8-auto от KOWX712 & Enginex0 
`Но выключил там SECURITY PATCH AUTO-UPDATE ибо как-то аномально нагревает телефон`

`Есть версия и новее но у меня с ней только 2✅ а с этой 3✅`
> **ЭТО КАК ДОПОЛНЕНИЕ ПО ЖЕЛАНИЮ Я ПОСТАВИЛ ПУСТЬ БУДУТ**
> 1. По желанию можно установить HMA-OSS Zygisk группе t.me/yuriiroot есть файлы ***ЭТО ПОКА ЧТО ТЕСТОВЫЕ ВЕРСИИ*** 
> 2. Если установил HMA-OSS то в чате yuriiroot есть config с шаблонами для HMA-OSS для скрытия рут программ и программ кастомных прошивок 
> 3.  После всех установленных модулей и перегрузки надо зайти в KernelSU Next и активировать Play Integrity Fix потом надо зайти в настройки -> приложения и найти там Google Play Services, Google Play Store, Google Wallet у всех этих программ надо очистить данные

> Вопрос: Рочему через модуль а не через LSposed?
> Ответ: хоть и HMA-OSS был изначально сделан под LSposed но это по-сути зависемость от ложной вещи которая может вызывать детекты и какие-то проблемы и я считаю лучше избавиться от LSposed но если вам удобнее с ним проблем нету это выбор каждого 
