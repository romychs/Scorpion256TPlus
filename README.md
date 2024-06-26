# Scorpion ZS-256 Turbo+

## Российский клон компьютера ZX Spectrum с улучшениями.

Компьютер разрабатывался и выпускался, под руководством Сергея Зонова, санкт-петербургской фирмой Scorpion с 1996 по 1998г.
Данная версия схемы, отревершена по файлам molodcov_alex, а затем и по плате Павла Рябцова известной как "Black Edition".
Изначально это была схема, которая упоминается как схема Черного кота. В создании схемы, большую помощь оказали труды savelij из темы про скорпиона 1024.

## Особенности:
- Z80B CPU, режим Turbo 7MHz, данный вариант хорошо работает с КМОП процессорами Z84C0020PEC.
- 256k DRAM, хорошо работают только импортные микросхемы типа 41256.
- Теневой Сервис-Монитор
- Музыкальный сопроцессор AY-3-8912.
- 2 Слота расширения ZX Bus.
- Контроллер дисковода Floppy-дисков с ФАПЧ.
- Старые микросхемы 565РТ5 заменены более доступными GAL16V8, GAL22V10.
- PROF ROM.
- Интерфейс Centronics для принтера.
- Интерфейс RS-232, но никто не проверял, работает ли?

[Принципиальная схема](Export/Schematic_Scorpion-256-Turbo_v16.2.8.pdf)

[Монтажная схема](Export/PCB_SILK_TOP_v16.2.8.pdf)

Печатная плата и герберы, получены, как побочный продукт при реверсе схемы и отличаются и от платы molodcov_alex и от платы Павла. Многие уже собирали платы версий до v16.2.3. 
Некоторые трассы укорочены, уменьшено число изгибов проводников, уменьшено число проводников между ножками процессора с 3-х до 2-х.
На плате нет краевых разъемов.

[Тема на форуме, по данному варианту компьютера](https://zx-pk.ru/threads/9195-scorpion-zs-256-turbo-restored)

[Чат ZS Scorpion  в Telegram](https://t.me/zs_scorpion)

## Внимание!
- На платах v16.2.4 и v16.2.5 на шелкографии обнаружена ошибка. Все транзисторы КТ315 и КТ361, нужно запаивать эмиттером в отверстие с квадратным падом.

## Изменения
- В версии v16.2, исправлено подключение GAL ФАПЧ контроллера дисковода. Несоответствие было обнаружено при сборке платы пользователем форума tigr101274. Исправлена печатная плата в соответствии со схемой, на печатной плате значительно расширены проводники питания за счет полигонов.
- В версии v16.2.1 исправлена ошибка, замеченная azx987sa, с сигналом строба интерфейса принтера.
- В версии v16.2.2 добавлен резистор R76, как в Scorpion ZS 1024 Turbo+ от savelij, для лучшего качества звука с AY. Убраны лишние дорожки и переходные отверстия, замеченные пользователем ponchik.
- В версии v16.2.3 изменена схема формирования сигнала DSR, по варианту, предложенному Jeckas Nameless. Изменены футпринты для транзисторов КТ315/КТ361 и некоторых конденсаторов. Перенесен диод VD2 для более удобного монтажа.
- В версии v16.2.4 подвинуты некоторые элементы для удобства сборки, заменен футпринт AY (ponchik). На разъем XP3 выведен сигнал SYNC и добавлен разъем X16 - выход частоты 14МГц. Добавлены конденсаторы по питанию, в районе чипов памяти (ponchik). Перенумерованы диоды, для соответствия оригиналу, H4 заменен на H5 в формирователе SYNC (RomanRom2). Добавлены перемычки для возможности выбора выхода звука AY ABC или BCA (участники [чата в Telegram](https://t.me/zs_scorpion)). 
- В версии v16.2.5 добавлены SMD-резисторы на задней стороны платы  для защиты порта музыкального сопроцессора (Jeckas Nameless). AY немного сдвинут дальше от слотов.
- В версии v16.2.6 Исправлена шелкография под транзисторами. Добавлены наименования для ~~диодов~~ стабилитронов. Подписаны GAL-ки.
- В версии v16.2.7 На нижнем краю платы, возле слотов шины, добавлен (опциональный) разъем питания, как на дисководах 3,5". 
На верхнем краю платы, там где были отверстия для конденсатора, теперь, отверстия либо для подпайки проводов, либо для установки разъема с расстоянием между выводами 2,54мм для подвода питания +5В. 
Рядом с этими отверстиями, добавлен блокировочный конденсатор С28. Так же, добавлен блокировочный конденсатор C29 на +12В питания шины. 
+12В на шине - это опция, она нужна редко для редких устройств, без необходимости, подавать это напряжение не нужно. Для питания Скорпиона, по прежнему, нужны только +5В.
Системный разъем сдвинут ближе к краю платы для возможности использования разъемов типа DIN-41612 32x2pin. Исправлены попутанные цвета на видеовыходе.
- В версии v16.2.8 Учтены пожелания Mikka_A и коллег после сборки скорпа v16.2.7 на стриме. Добавлена кнопка Reset на краю платы. Добавлены перемычки для подачи питания +5В и +12В на контакты слота как в Nemo-Bus. Отверстия под эмиттеры транзисторов - квадратиком, базы помечены буквой Б на шелкографии. Добавлен разъем для подключения скандаблера RGB-VGA. Редкий AY-3-8912 заменен на более доступный AY-3-8910.