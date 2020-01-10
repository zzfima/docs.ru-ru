---
title: Контроль ведения журнала .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events, logging
ms.assetid: ce13088e-3095-4f0e-9f6b-fad30bbd3d41
ms.openlocfilehash: 180cce516a1209711430429a46cb5b718b29f1d9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716109"
---
# <a name="controlling-net-framework-logging"></a>Контроль ведения журнала .NET Framework

Трассировку событий для Windows (ETW) можно использовать для записи событий среды CLR. Для создания и просмотра трассировки можно использовать следующие инструменты.

- Программы командной строки [Logman](/windows-server/administration/windows-commands/logman) и [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1), входящие в состав операционной системы Windows.

- Программы [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) в составе [набора средств для оценки производительности Windows](/windows-hardware/test/wpt/). Дополнительные сведения о программе Xperf см. в [блоге, посвященном производительности Windows](https://blogs.msdn.microsoft.com/pigscanfly/tag/xperf/).

Для регистрации событий среды CLR на компьютере должен быть установлен поставщик среды CLR. Чтобы проверить, установлен ли этот поставщик, введите в командной строке `logman query providers`. Откроется список поставщиков. В этом списке должна находиться следующая запись для поставщика среды CLR.

```output
Provider                                 GUID
-------------------------------------------------------------------------------
.NET Common Language Runtime    {E13C0D23-CCBC-4E12-931B-D9CC2EEE27E4}.
```

Если поставщик среды CLR не указан, его можно установить в Windows Vista и операционных системах более поздних версий с помощью программы командной строки Windows [Wevtutil](/windows-server/administration/windows-commands/wevtutil). Откройте окно командной строки от имени учетной записи администратора. Измените каталог подсказки на папку .NET Framework 4 (%WINDIR%\Microsoft.NET\Framework [64] \v4.\<.NET version > \). Эта папка содержит файл CLR-ETW.man. Чтобы установить поставщик среды CLR, в командной строке введите следующую команду:

`wevtutil im CLR-ETW.man`

## <a name="capturing-clr-etw-events"></a>Регистрация событий ETW в среде CLR

Программы командной строки [Logman](/windows-server/administration/windows-commands/logman) и [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) можно использовать для захвата событий трассировки событий Windows, а программы [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) и [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) — для расшифровки событий трассировки.

Чтобы включить ведение журнала, пользователь должен указать следующее.

- Поставщика, с которым следует обмениваться информацией.

- 64-разрядное число, представляющее набор ключевых слов. Каждое ключевое слово представляет набор событий, которые может включить поставщик. Число представляет комбинированный набор ключевых слов, которые необходимо включить.

- Небольшое число, представляющее уровень (детализации) ведения журнала. Уровень 1 является наименее детальным, а уровень 5 — наиболее детальным. Уровень 0 является значением по умолчанию, его назначение зависит от поставщика.

### <a name="to-capture-clr-etw-events-using-logman"></a>Регистрация событий ETW среды CLR с помощью программы Logman

1. В командной строке введите следующее:

     `logman start clrevents -p {e13c0d23-ccbc-4e12-931b-d9cc2eee27e4} 0x1CCBD 0x5 -ets -ct perf`

     Здесь:

    - Параметр `-p` задает GUID поставщика.

    - `0x1CCBD` задает категории создаваемых событий.

    - `0x5` задает уровень регистрации (в данном случае подробный (5)).

    - Параметр `-ets` указывает программе Logman отправлять команды сеансам трассировки событий.

    - Параметр `-ct perf`, определяет, что для записи отметки времени каждого события будет использоваться функция `QueryPerformanceCounter`.

2. Чтобы остановить регистрацию событий, введите:

     `logman stop clrevents -ets`

     Эта команда создает двоичный файл трассировки clrevents.etl.

### <a name="to-capture-clr-etw-events-using-xperf"></a>Регистрация событий ETW среды CLR с помощью программы Xperf

1. В командной строке введите следующее:

     `xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:5 -f clrevents.etl`

     где GUID — это GUID поставщика ETW среды CLR, а `0x1CCBD:5` выполняет трассировку всех событий на уровне 5 (детальный) и ниже.

2. Чтобы остановить трассировку, введите:

     `Xperf -stop clr`

     Эта команда создает файл трассировки clrevents.etl.

## <a name="viewing-clr-etw-events"></a>Просмотр событий ETW среды CLR

Перечисленные ниже команды используются для просмотра событий ETW среды CLR. Описание событий см. в разделе [События трассировки событий Windows в среде CLR](clr-etw-events.md).

### <a name="to-view-clr-etw-events-using-tracerpt"></a>Просмотр событий ETW среды CLR с помощью программы Tracerpt

- В командной строке введите следующее:

     `tracerpt clrevents.etl`

     Эта команда создает два файла: dumpfile.xml и summary.txt. Файл dumpfile.xml содержит список всех событий, а файл summary.txt содержит сводку событий.

### <a name="to-view-clr-etw-events-using-xperf"></a>Просмотр событий ETW среды CLR с помощью программы Xperf

- В командной строке введите следующее:

     `xperf clrevents.etl`

     Эта команда открывает программу Xperf просмотра ETL-файлов. В этом средстве просмотра события CLR показаны в представлении **Универсальные события**. Чтобы отобразить таблицу данных событий, распределенных по типу, в этом представлении выберите часовой пояс, щелкните правой кнопкой мыши и выберите **Сводка**.

### <a name="to-convert-the-etl-file-to-a-comma-separated-value-file"></a>Преобразование ETL-файла в файл данных с разделителями-запятыми

- В командной строке введите следующее:

     `xperf -i clrevents.etl -f clrevents.csv`

     Эта команда XPerf помещает события в дамп в виде файла с разделителями-запятыми (CSV-файл), который впоследствии можно просмотреть. Поскольку у разных событий поля разные, этот CSV-файл содержит несколько строк заголовков, расположенных перед данными. Первое поле каждой строки является типом события с указанием заголовка, который должен использоваться для определения остальных полей.

## <a name="see-also"></a>См. также:

- [Windows Performance Toolkit](/windows-hardware/test/wpt/)
- [События в среде CLR (трассировка событий Windows)](etw-events-in-the-common-language-runtime.md)
