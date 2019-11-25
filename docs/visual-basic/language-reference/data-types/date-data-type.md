---
title: Тип данных Date
ms.date: 07/20/2015
f1_keywords:
- vb.Date
helpviewer_keywords:
- Date data type
- dates [Visual Basic], Visual Basic data types
- times [Visual Basic], Date data type
- Date literals [Visual Basic]
- data values [Visual Basic]
- times [Visual Basic], Visual Basic data types
- dates [Visual Basic], Date data type
- data types [Visual Basic], assigning
- literals [Visual Basic], Date
- '# specifier for Date literals'
ms.assetid: d9edf5b0-e85e-438b-a1cf-1f321e7c831b
ms.openlocfilehash: 972df72874753a0f1213f3a4942468c59e3913ce
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344024"
---
# <a name="date-data-type-visual-basic"></a>Тип данных Date (Visual Basic)

Содержит 64-разрядные (8-байтные) значения IEEE, представляющие даты в диапазоне от 1 января 0001 года до 31 декабря 9999 года и время от 00:00:00 (полночь) до 23:59:9999999. Каждое приращение представляет 100 наносекунд затраченного времени с начала 1 января 1 года по григорианскому календарю. Максимальное значение представляет 100 наносекунд перед началом 1 января 10 000 года.

## <a name="remarks"></a>Заметки

Используйте тип данных `Date`, содержащий значения даты, времени или даты и времени.

Значение по умолчанию `Date`: 0:00:00 (полночь) 1 января 0001 года.

Текущие дату и время можно получить из класса <xref:Microsoft.VisualBasic.DateAndTime>.

## <a name="format-requirements"></a>Требования к формату

Необходимо заключить литерал `Date` в символы решетки (`# #`). Необходимо указать значение даты в формате М/д/гггг, например `#5/31/1993#`, или гггг-ММ-дд, например `#1993-5-31#`. При указании года сначала можно использовать символы косой черты.  Это требование не зависит от языкового стандарта и настроек формата времени и даты компьютера.

Причина этого ограничения связана с тем, что значение кода никогда не должно изменяться в зависимости от языкового стандарта, который использует приложение. Предположим, что литерал `Date` жестко закодирован как `#3/4/1998#`, что это означает 4 марта 1998 года. В языковом стандарте, использующем формат дд/мм/гггг, 3/4/1998 компилируется, как предполагается. But suppose you deploy your application in many countries/regions. В языковом стандарте, использующем формат мм/дд/гггг, ваш жестко закодированный литерал будет компилироваться как 3 апреля 1998 года. В языковом стандарте, использующем формат гггг/мм/дд, литерал будет недопустимым (апрель 1998, 0003) и вызовет ошибку компилятора.

## <a name="workarounds"></a>Методы обхода проблемы

Для преобразования литерала `Date` в формат языкового стандарта или пользовательский формат, передайте литерал функции <xref:Microsoft.VisualBasic.Strings.Format%2A>, указав стандартный или пользовательский формат даты. В следующем примере это показано.

```vb
MsgBox("The formatted date is " & Format(#5/31/1993#, "dddd, d MMM yyyy"))
```

Кроме того, для формирования значения даты и времени можно использовать один из перегруженных конструкторов структуры <xref:System.DateTime>. В следующем примере создается значение для представления даты и времени 12:14 31 мая, 1993 г.

```vb
Dim dateInMay As New System.DateTime(1993, 5, 31, 12, 14, 0)
```

## <a name="hour-format"></a>Часовой формат

Значение времени можно указать в 12- или 24-часовом формате, например `#1:15:30 PM#` или `#13:15:30#`. Однако если не указать значение минут или секунд, необходимо указать AM или PM.

## <a name="date-and-time-defaults"></a>Дата и время по умолчанию

Если не указать дату в литерале даты и времени, Visual Basic задает часть даты как 1 января 0001 года. Если в литерал даты и времени не включено время, Visual Basic задает часть значения времени как начало дня, то есть полночь (0:00:00).

## <a name="type-conversions"></a>Преобразования типов

При преобразовании значения `Date` типа `String` Visual Basic отображает дату в формате короткой даты, определяемом языковым стандартом времени выполнения. Время отображается в формате времени (12- или 24-часовом), определяемом языковым стандартом времени выполнения.

## <a name="programming-tips"></a>Советы по программированию

- **Interop Considerations.** При взаимодействие с компонентами, которые не написаны для платформы .NET Framework (например, автоматизация или COM-объекты), необходимо помнить, что в других средах типы даты и времени несовместимы с типом `Date` Visual Basic. Если вы передаете аргумент даты и времени такому компоненту, объявите его `Double`, а не как `Date` в новом коде Visual Basic и используйте методы преобразования <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> и <xref:System.DateTime.ToOADate%2A?displayProperty=nameWithType>.

- **Type Characters.** `Date` has no literal type character or identifier type character. Однако компилятор обрабатывает литералы, заключенные в решетки (`# #`), как `Date`.

- **Framework Type.** В .NET Framework данный тип соответствует структуре <xref:System.DateTime?displayProperty=nameWithType>.

## <a name="example"></a>Пример

Переменная или константа типа данных `Date` содержит дату и время. Это показано в следующем примере.

```vb
Dim someDateAndTime As Date = #8/13/2002 12:14 PM#
```

## <a name="see-also"></a>См. также

- <xref:System.DateTime?displayProperty=nameWithType>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Строки стандартных форматов даты и времени](../../../standard/base-types/standard-date-and-time-format-strings.md)
- [Строки настраиваемых форматов даты и времени](../../../standard/base-types/custom-date-and-time-format-strings.md)
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
