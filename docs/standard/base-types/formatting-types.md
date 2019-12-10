---
title: Типы форматирования в .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data formatting [.NET Framework]
- dates [.NET Framework], formatting
- date formatting [.NET Framework]
- number formatting [.NET Framework]
- ToString method
- custom cultural settings [.NET Framework]
- numbers [.NET Framework], formatting
- formatting strings [.NET Framework]
- time [.NET Framework], formatting
- currency [.NET Framework], formatting
- types [.NET Framework], formatting
- format specifiers [.NET Framework]
- times [.NET Framework], formatting
- culture [.NET Framework], formatting
- formatting [.NET Framework], types supported
- base types [.NET Framework], formatting
- custom formatting [.NET Framework]
- strings [.NET Framework], formatting
ms.assetid: 0d1364da-5b30-4d42-8e6b-03378343343f
ms.openlocfilehash: 20aa7ecd354ef1a8982ae75eda87275c80cdaaf6
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802470"
---
# <a name="format-types-in-net"></a>Форматирование типов в .NET

Форматирование — это процесс преобразования экземпляра класса, структуры или значения перечисления в строковое представление. Результирующая строка затем демонстрируется пользователям или десериализуется для последующего восстановления значения с исходным типом данных. Преобразование может быть связано с рядом проблем:

- Внутреннее представление значений необязательно соответствует тому виду, в котором они должны быть представлены пользователям. Например, номер телефона может храниться в форме 8009999999, которая не отличается удобством для пользователей. Вместо этого номер должен отображаться в следующем виде: 800-999-9999. См. в подразделе [Строки настраиваемого формата](#custom-format-strings) пример, в котором число форматируется таким образом.

- Иногда порядок преобразования объекта в строковое представление неочевиден. Например, неясно, как должно выглядеть строковое представление объекта класса Temperature, представляющего температурные значения, или класса Person, представляющего данные о людях. Пример, в котором объект Temperature форматируется различными способами, см. в подразделе [Строки стандартного формата](#standard-format-strings) .

- Для некоторых значений может потребоваться форматирование, учитывающее язык и региональные параметры. Например, в приложении, где числа используются для обозначения денежных сумм, числовые строки должны включать символ текущей валюты, разделители групп (в большинстве случаев они совпадают с разделителями тысяч) и символ-разделитель целой и дробной частей. Пример см. в разделе [Форматирование с учетом языка и региональных параметров с помощью поставщиков формата](#culture-sensitive-formatting-with-format-providers).

- Одно и то же значение может быть необходимо представить в приложении несколькими способами. Например, приложение может представлять элемент перечисления, отображая строковое представление его имени или его базовое значение. Пример, в котором член перечисления <xref:System.DayOfWeek> форматируется различными способами, см в подразделе [Строки стандартного формата](#standard-format-strings) .

> [!NOTE]
> Форматирование приводит к преобразованию значения определенного типа в его строковое представление. Обратной по отношению к форматированию операцией является анализ. В ходе анализа на основании строкового представления создается экземпляр некоторого типа данных. Дополнительные сведения о преобразовании строк в другие типы данных см. в разделе [Parsing Strings](../../../docs/standard/base-types/parsing-strings.md).

Платформа .NET обеспечивает обширную поддержку форматирования, позволяя разработчикам справиться с описанными проблемами.

## <a name="formatting-in-net"></a>Форматирование в .NET

Основной механизм форматирования — это используемая по умолчанию реализация метода <xref:System.Object.ToString%2A?displayProperty=nameWithType>, описанная ниже в подразделе [Форматирование по умолчанию с помощью метода ToString](#default-formatting-using-the-tostring-method). При этом платформа .NET предоставляет несколько способов изменения и расширения имеющихся по умолчанию возможностей форматирования. В число этих требований входят следующие:

- Переопределение метода <xref:System.Object.ToString%2A?displayProperty=nameWithType> , позволяющее определить настраиваемое строковое представление значения объекта. Дополнительные сведения см. ниже в разделе [Переопределение метода ToString](#override-the-tostring-method).

- Определение описателей формата, позволяющих использовать несколько видов строкового представления значения объекта. Например, описатель формата "X" в следующем операторе позволяет преобразовать целое число в шестнадцатеричное строковое представление.

     [!code-csharp[Conceptual.Formatting.Overview#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/specifier1.cs#3)]
     [!code-vb[Conceptual.Formatting.Overview#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/specifier1.vb#3)]

     Дополнительные сведения об описателях форматов см. в подразделе [Метод ToString и строки формата](#the-tostring-method-and-format-strings) .

- Использование поставщиков форматирования, позволяющих воспользоваться преимуществами соглашений о форматировании, присущих конкретному языку и региональным параметрам. Например, следующий оператор выводит значение валюты с использованием соглашений о форматировании языка и региональных параметров "en-US".

     [!code-csharp[Conceptual.Formatting.Overview#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/specifier1.cs#10)]
     [!code-vb[Conceptual.Formatting.Overview#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/specifier1.vb#10)]

     Дополнительные сведения о форматировании с помощью поставщиков форматирования см. в разделе [Поставщики форматирования](#culture-sensitive-formatting-with-format-providers).

- Реализация интерфейса <xref:System.IFormattable> , позволяющая преобразовывать строки с помощью класса <xref:System.Convert> и использовать составное форматирование. Дополнительные сведения см. в подразделе [Интерфейс IFormattable](#the-iformattable-interface) .

- Использование составного форматирования, позволяющее внедрить строковую презентацию в состав более крупной строки. Дополнительные сведения см. в подразделе [Составное форматирование](#composite-formatting) .

- Реализация интерфейсов <xref:System.ICustomFormatter> и <xref:System.IFormatProvider> , позволяющая создать полноценное настраиваемое решение для форматирования. Дополнительные сведения см. в подразделе [Настраиваемое форматирование с использованием интерфейса ICustomFormatter](#custom-formatting-with-icustomformatter) .

В следующих подразделах перечисленные методы преобразования объектов в их строковые представления рассматриваются более подробно.

## <a name="default-formatting-using-the-tostring-method"></a>Форматирование по умолчанию при помощи метода ToString

Любой производный от <xref:System.Object?displayProperty=nameWithType> тип автоматически наследует метод `ToString` без параметров, по умолчанию возвращающий имя типа. В следующем примере демонстрируется использование метода `ToString` по умолчанию. Здесь определен класс с именем `Automobile` , у которого нет реализации. При создании экземпляра этого класса и вызове его метода `ToString` отображается имя класса. Обратите внимание, что метод `ToString` не вызывается в примере явным образом. Метод <xref:System.Console.WriteLine%28System.Object%29?displayProperty=nameWithType> неявно вызывает метод `ToString` объекта, переданного ему в качестве аргумента.

[!code-csharp[Conceptual.Formatting.Overview#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/default1.cs#1)]
[!code-vb[Conceptual.Formatting.Overview#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/default1.vb#1)]

> [!WARNING]
> Начиная с Windows 8.1 среда выполнения Windows включает интерфейс <xref:Windows.Foundation.IStringable> с единственным методом [IStringable.ToString](xref:Windows.Foundation.IStringable.ToString%2A), который обеспечивает поддержку форматирования по умолчанию. Однако рекомендуется, чтобы управляемые типы не реализовывали интерфейс `IStringable` . Дополнительные сведения см. в подразделе "Среда выполнения Windows и интерфейс `IStringable`" справочных сведений о методе <xref:System.Object.ToString%2A?displayProperty=nameWithType>.

Поскольку производными от <xref:System.Object>являются все типы, кроме интерфейсов, данная функциональность автоматически присутствует в пользовательских классах и структурах. Тем не менее функциональные возможности, предлагаемые по умолчанию методом `ToString`, ограничены: хотя он определяет тип, он не предоставляет никакой информации о экземпляра типа. Для формирования строкового представления объекта, позволяющего получить сведения о конкретном объекте, следует переопределить метод `ToString` .

> [!NOTE]
> Структуры наследуют от типа <xref:System.ValueType>, который также является наследником <xref:System.Object>. Хотя в <xref:System.ValueType> метод <xref:System.Object.ToString%2A?displayProperty=nameWithType>переопределен, его реализация идентична базовой.

## <a name="override-the-tostring-method"></a>Переопределение метода ToString

Отображение имени типа зачастую малополезно и не позволяет пользователям типов отличить один экземпляр от другого. Однако метод `ToString` можно переопределить, чтобы он мог возвращать более функциональное представление значения объекта. В следующем примере определяется объект `Temperature` , метод `ToString` которого переопределен и отображает температуру в градусах Цельсия.

[!code-csharp[Conceptual.Formatting.Overview#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/overrides1.cs#2)]
[!code-vb[Conceptual.Formatting.Overview#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/overrides1.vb#2)]

В .NET метод `ToString` переопределен для всех типов-примитивов значений: вместо имени он отображает значение объекта. В следующей таблице показаны переопределения для всех типов-примитивов. Обратите внимание, что большинство переопределенных методов вызывают другую перегрузку метода `ToString` и передают ей описатель формата "G", который задает общий формат типа, и объект <xref:System.IFormatProvider> , представляющий текущий язык и региональные параметры.

|Тип|Переопределение ToString|
|----------|-----------------------|
|<xref:System.Boolean>|Возвращает <xref:System.Boolean.TrueString?displayProperty=nameWithType> или <xref:System.Boolean.FalseString?displayProperty=nameWithType>.|
|<xref:System.Byte>|Вызывает метод `Byte.ToString("G", NumberFormatInfo.CurrentInfo)` , чтобы отформатировать значение <xref:System.Byte> в соответствии с текущим языком и региональными параметрами.|
|<xref:System.Char>|Возвращает символ в виде строки.|
|<xref:System.DateTime>|Вызывает метод `DateTime.ToString("G", DatetimeFormatInfo.CurrentInfo)` , чтобы отформатировать значение даты и времени в соответствии с текущим языком и региональными параметрами.|
|<xref:System.Decimal>|Вызывает метод `Decimal.ToString("G", NumberFormatInfo.CurrentInfo)` , чтобы отформатировать значение <xref:System.Decimal> в соответствии с текущим языком и региональными параметрами.|
|<xref:System.Double>|Вызывает метод `Double.ToString("G", NumberFormatInfo.CurrentInfo)` , чтобы отформатировать значение <xref:System.Double> в соответствии с текущим языком и региональными параметрами.|
|<xref:System.Int16>|Вызывает метод `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` , чтобы отформатировать значение <xref:System.Int16> в соответствии с текущим языком и региональными параметрами.|
|<xref:System.Int32>|Вызывает метод `Int32.ToString("G", NumberFormatInfo.CurrentInfo)` , чтобы отформатировать значение <xref:System.Int32> в соответствии с текущим языком и региональными параметрами.|
|<xref:System.Int64>|Вызывает метод `Int64.ToString("G", NumberFormatInfo.CurrentInfo)` , чтобы отформатировать значение <xref:System.Int64> в соответствии с текущим языком и региональными параметрами.|
|<xref:System.SByte>|Вызывает метод `SByte.ToString("G", NumberFormatInfo.CurrentInfo)` , чтобы отформатировать значение <xref:System.SByte> в соответствии с текущим языком и региональными параметрами.|
|<xref:System.Single>|Вызывает метод `Single.ToString("G", NumberFormatInfo.CurrentInfo)` , чтобы отформатировать значение <xref:System.Single> в соответствии с текущим языком и региональными параметрами.|
|<xref:System.UInt16>|Вызывает метод `UInt16.ToString("G", NumberFormatInfo.CurrentInfo)` , чтобы отформатировать значение <xref:System.UInt16> в соответствии с текущим языком и региональными параметрами.|
|<xref:System.UInt32>|Вызывает метод `UInt32.ToString("G", NumberFormatInfo.CurrentInfo)` , чтобы отформатировать значение <xref:System.UInt32> в соответствии с текущим языком и региональными параметрами.|
|<xref:System.UInt64>|Вызывает метод `UInt64.ToString("G", NumberFormatInfo.CurrentInfo)` , чтобы отформатировать значение <xref:System.UInt64> в соответствии с текущим языком и региональными параметрами.|

## <a name="the-tostring-method-and-format-strings"></a>Метод ToString и строки формата

Использовать метод `ToString` по умолчанию или перегрузку `ToString` удобно, если у объекта имеется однозначное строковое представление. Тем не менее зачастую значение объекта может иметь несколько представлений. Например, температура может выражаться в градусах по шкале Фаренгейта, Цельсия или Кельвина. Аналогично, целое число 10 можно представить различными способами, включая 10, 10.0, 1.0e01 или $10.00.

Для реализации нескольких строковых представлений одного значения в платформе .NET используются строки формата. Строка формата содержит один или несколько предопределенных описателей формата, представляющих собой одиночные символы или группы символов, указывающие, как метод `ToString` должен форматировать вывод. Строка формата передается в качестве параметра методу `ToString` объекта и определяет, как должно выглядеть строковое представление его значения.

Все числовые типы, типы даты и времени, а также перечисления в составе платформы .NET поддерживают предопределенный набор описателей формата. Строки формата также можно использовать для определения разнообразных строковых представлений прикладных пользовательских типов данных.

### <a name="standard-format-strings"></a>Строки стандартного формата

Строка стандартного формата содержит один описатель формата. Это алфавитный символ, определяющий строковое представление объекта, к которому он применяется. Также строка формата может содержать необязательный описатель точности, определяющий, сколько цифр отображается в результирующей строке. Если описатель точности не указан или не поддерживается, описатель стандартного формата будет эквивалентен строке стандартного формата.

В платформе .NET определяется набор описателей стандартного формата для всех числовых типов, типов даты и времени, а также для всех типов перечислений. Например, все эти категории поддерживают описатель стандартного формата "G", который определяет общее строковое представление значения соответствующего типа.

Строки стандартного формата для типов перечислений напрямую определяют строковое представление значения. От строки формата, переданной в метод `ToString` значения перечисления, зависит, будет оно представлено своим строковым именем (описатели формата "G" и "F"), базовым целочисленным значением (описатель формата "D") или шестидесятеричным значением (описатель формата "X"). В следующем примере демонстрируется использование строк стандартного формата для форматирования значения перечисления <xref:System.DayOfWeek> .

[!code-csharp[Conceptual.Formatting.Overview#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/standard1.cs#4)]
[!code-vb[Conceptual.Formatting.Overview#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/standard1.vb#4)]

Сведения о строках форматов перечислений см. в разделе [Enumeration Format Strings](../../../docs/standard/base-types/enumeration-format-strings.md).

Строки стандартного формата для числовых типов обычно задают результирующую строку, точный вид которой зависит от значения одного или нескольких свойств. Например, описатель формата "C" форматирует число в виде значения валюты. При вызове метода `ToString` с описателем формата "C" в качестве единственного параметра для определения строкового представления числового значения используются следующие свойства объекта <xref:System.Globalization.NumberFormatInfo> для текущего языка и региональных параметров:

- Свойство <xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A> , определяющее символ валюты для текущего языка и региональных параметров.

- Свойство <xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern%2A> или <xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern%2A> , возвращающее целое число, от которого зависит следующее:

  - Положение символа валюты.

  - Обозначение отрицательных значений: отрицательный знак в начале, отрицательный знак в конце или круглые скобки.

  - Наличие пробела между числовым значением и символом валюты.

- Свойство <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits%2A> , определяющее число цифр дробной части в результирующей строке.

- Свойство <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A> , определяющее символ-разделитель целой и дробной частей в результирующей строке.

- Свойство <xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A> , определяющее символ-разделитель групп.

- Свойство <xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes%2A> , определяющее число цифр в каждой из групп слева от разделителя целой и дробной частей.

- Свойство <xref:System.Globalization.NumberFormatInfo.NegativeSign%2A> , задающее отрицательный знак, который используется в случаях, если скобки не применяются для обозначения отрицательных значений в результирующей строке.

Кроме того, строки числового формата могут содержать описатель точности. Смысл этого описателя зависит от строки формата, в которой он используется, но обычно он задает общее число цифр в результирующей строке или число цифр в дробной части. В следующем примере используется строка стандартного числового формата с описателем точности ("X4"), что позволяет сформировать строковое значение из четырех шестидесятеричных цифр.

[!code-csharp[Conceptual.Formatting.Overview#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/precisionspecifier1.cs#6)]
[!code-vb[Conceptual.Formatting.Overview#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/precisionspecifier1.vb#6)]

Дополнительные сведения о строках стандартных числовых форматов см. в разделе [Standard Numeric Format Strings](../../../docs/standard/base-types/standard-numeric-format-strings.md).

Строки стандартного формата для значений даты и времени — это псевдонимы строк настраиваемого формата, которые хранятся в конкретном свойстве <xref:System.Globalization.DateTimeFormatInfo> . Например, вызов метода `ToString` применительно к значению даты и времени с описателем формата "D" приведет к отображению даты и времени с помощью настраиваемой строки формата, хранящейся в свойстве <xref:System.Globalization.DateTimeFormatInfo.LongDatePattern%2A?displayProperty=nameWithType> для текущего языка и региональных параметров. (Дополнительные сведения о строках настраиваемого формата см. [в следующем разделе](#custom-format-strings).) Данная связь показана в следующем примере.

[!code-csharp[Conceptual.Formatting.Overview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/alias1.cs#5)]
[!code-vb[Conceptual.Formatting.Overview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/alias1.vb#5)]

Дополнительные сведения о строках стандартных форматов даты и времени см. в разделе [Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md).

Строки стандартного формата также можно использовать для определения строкового представления прикладного объекта, формируемого с помощью метода `ToString(String)` такого объекта. Можно определить конкретные описатели стандартного формата, поддерживаемые объектом, а также решить, будут ли они зависеть от регистра символов. Реализация метода `ToString(String)` должна отвечать следующим условиям:

- Должен поддерживаться описатель формата "G", отвечающий за представление обычного или общего формата объекта. Перегрузка метода `ToString` объекта, не имеющая параметров, должна вызывать его перегрузку `ToString(String)` , передавая ей строку стандартного формата "G".

- Должен поддерживаться описатель формата, равный пустой ссылке (`Nothing` в Visual Basic). Описатель формата, равный пустой ссылке, должен рассматриваться как эквивалент описателя формата "G".

Например, во внутреннем представлении класса `Temperature` температура может храниться в градусах Цельсия, а для представления значения объекта `Temperature` в градусах Цельсия, Фаренгейта или Кельвина могут использоваться различные описатели формата. Ниже приведен пример.

[!code-csharp[Conceptual.Formatting.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/appstandard1.cs#7)]
[!code-vb[Conceptual.Formatting.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/appstandard1.vb#7)]

### <a name="custom-format-strings"></a>Строки настраиваемого формата

Помимо строк стандартного формата, в платформе .NET для числовых значений и значений даты и времени определяются строки настраиваемого формата. Строка настраиваемого формата состоит из одного или нескольких описателей настраиваемого формата, описывающих строковое представление значения. Например, строка настраиваемого формата даты и времени, заданная как "yyyy/mm/dd hh:mm:ss.ffff t zzz", преобразует дату в строковое представления вида "2008/11/15 07:45:00.0000 P -08:00" для языка и региональных параметров "en-US". Аналогично строка настраиваемого формата "0000" приведет к преобразованию целочисленного значения 12 в строку "0012". Полный список строк настраиваемого формата см. в разделах [Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md) и [Custom Numeric Format Strings](../../../docs/standard/base-types/custom-numeric-format-strings.md).

Если строка формата состоит из одного описателя настраиваемого формата, то перед ним должен стоять символ процента (%), чтобы его можно было отличить от описателя стандартного формата. В следующем примере описатель настраиваемого формата "М" используется для вывода одно- или двухзначного числа месяца для определенной даты.

[!code-csharp[Conceptual.Formatting.Overview#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/singlecustom1.cs#8)]
[!code-vb[Conceptual.Formatting.Overview#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/singlecustom1.vb#8)]

Многие строки стандартного формата для значений даты и времени являются псевдонимами для строк настраиваемого формата, определяемых свойствами объекта <xref:System.Globalization.DateTimeFormatInfo> . Строки настраиваемого формата также позволяют добиться значительной гибкости в реализации прикладного форматирования числовых значений или значений даты и времени. Можно определить собственные настраиваемые результирующие строки для числовых значений и значений даты и времени, объединив несколько описателей настраиваемого формата в одной строке настраиваемого формата. В следующем примере определяется строка настраиваемого формата, отображающая день недели в скобках после названия месяца, числа и года.

[!code-csharp[Conceptual.Formatting.Overview#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/custom1.cs#9)]
[!code-vb[Conceptual.Formatting.Overview#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/custom1.vb#9)]

В следующем примере определяется строка настраиваемого формата, которая отображает значение <xref:System.Int64> как стандартный 7-значный американский номер телефона вместе с кодом города.

[!code-csharp[Conceptual.Formatting.Overview#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/telnumber1.cs#21)]
[!code-vb[Conceptual.Formatting.Overview#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/telnumber1.vb#21)]

Хотя строк стандартного формата обычно достаточно для выполнения большинства задач форматирования прикладных типов, для форматирования пользовательских типов также можно определять описатели настраиваемого формата.

### <a name="format-strings-and-net-types"></a>Строки форматов и типы .NET

Все числовые типы (то есть типы <xref:System.Byte>, <xref:System.Decimal>, <xref:System.Double>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.SByte>, <xref:System.Single>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64> и <xref:System.Numerics.BigInteger>), а также <xref:System.DateTime>, <xref:System.DateTimeOffset>, <xref:System.TimeSpan>, <xref:System.Guid> и все типы перечислений поддерживают форматирование с помощью строк форматов. Сведения о конкретных строках форматов, поддерживаемых каждым типом, см. в следующих разделах.

|Заголовок|Определение|
|-----------|----------------|
|[Standard Numeric Format Strings](../../../docs/standard/base-types/standard-numeric-format-strings.md)|Описание строк стандартного формата, позволяющих создавать общеупотребимые строковые представления числовых значений.|
|[Custom Numeric Format Strings](../../../docs/standard/base-types/custom-numeric-format-strings.md)|Описание строк настраиваемого формата, позволяющих создавать прикладные строковые представления числовых значений.|
|[Строки стандартных форматов даты и времени](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)|Описание строк стандартного формата, позволяющих создавать общеупотребимые строковые представления значений <xref:System.DateTime> и <xref:System.DateTimeOffset>.|
|[Строки настраиваемых форматов даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)|Описание строк настраиваемого формата, позволяющих создавать прикладные строковые представления значений <xref:System.DateTime> и <xref:System.DateTimeOffset>.|
|[Строки стандартного формата TimeSpan](../../../docs/standard/base-types/standard-timespan-format-strings.md)|Описание строк стандартного формата, позволяющих создавать общеупотребимые строковые представления интервалов времени.|
|[Строки настраиваемого формата TimeSpan](../../../docs/standard/base-types/custom-timespan-format-strings.md)|Описание строк настраиваемого формата, позволяющих создавать прикладные строковые представления интервалов времени.|
|[Enumeration Format Strings](../../../docs/standard/base-types/enumeration-format-strings.md)|Описание строк стандартного формата, используемых для создания строковых представлений значений перечислений.|
|<xref:System.Guid.ToString%28System.String%29?displayProperty=nameWithType>|Описание строк стандартного формата для значений <xref:System.Guid> .|

## <a name="culture-sensitive-formatting-with-format-providers"></a>Форматирование с учетом языка и региональных параметров с помощью поставщиков формата

Хотя описатели формата позволяют настраивать форматирование объектов, для формирования осмысленного строкового представления объектов зачастую требуется дополнительная информация, связанная с форматированием. Например, при форматировании числового значения в формате валюты с помощью строки стандартного формата "C" или строки настраиваемого формата "$ #,#.00" для включения в отформатированную строку должен быть известен нужный символ валюты, разделитель групп, а также разделитель целой и дробной частей. В .NET эти дополнительные сведения предоставляются с помощью интерфейса <xref:System.IFormatProvider>, который передается в качестве параметра одной или нескольким перегрузкам метода `ToString` для числовых типов и типов даты и времени. Реализации <xref:System.IFormatProvider> используются в .NET для поддержки форматирования с учетом языка и региональных параметров. В следующем примере показано, как меняется строковое представление объекта при его форматировании с использованием трех разных объектов <xref:System.IFormatProvider> .

[!code-csharp[Conceptual.Formatting.Overview#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/iformatprovider1.cs#11)]
[!code-vb[Conceptual.Formatting.Overview#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/iformatprovider1.vb#11)]

Интерфейс <xref:System.IFormatProvider> включает один метод, <xref:System.IFormatProvider.GetFormat%28System.Type%29>, имеющий один параметр, задающий тип объекта, предоставляющего сведения о форматировании. Если метод может предоставить объект указанного типа, то он его возвращает. В противном случае метод возвратит пустую ссылку (`Nothing` в Visual Basic).

Метод<xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> является методом обратного вызова. При вызове перегрузки метода `ToString` , имеющей параметр <xref:System.IFormatProvider> , вызывается метод <xref:System.IFormatProvider.GetFormat%2A> соответствующего объекта <xref:System.IFormatProvider> . Метод <xref:System.IFormatProvider.GetFormat%2A> должен вернуть в метод `formatType` объект, способный предоставить необходимые сведения о форматировании и соответствующий параметру `ToString` .

Многие методы форматирования и преобразования строк имеют параметр типа <xref:System.IFormatProvider>, но во многих случаях значение параметра игнорируется при вызове метода. В следующей таблице перечислены некоторые методы форматирования, использующие этот параметр. Для каждого метода также указывается тип объекта <xref:System.Type> , передаваемого в метод <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> .

|Метод|Тип параметра `formatType`|
|------------|------------------------------------|
|Метод`ToString` для числовых типов|<xref:System.Globalization.NumberFormatInfo?displayProperty=nameWithType>|
|Метод `ToString` для типов даты и времени|<xref:System.Globalization.DateTimeFormatInfo?displayProperty=nameWithType>|
|<xref:System.String.Format%2A?displayProperty=nameWithType>|<xref:System.ICustomFormatter?displayProperty=nameWithType>|
|<xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>|<xref:System.ICustomFormatter?displayProperty=nameWithType>|

> [!NOTE]
> Методы `ToString` у числовых типов и типов даты и времени перегружены; параметр <xref:System.IFormatProvider> имеется лишь у некоторых перегрузок. Если у метода нет параметра типа <xref:System.IFormatProvider>, то вместо этого передается объект, возвращаемый свойством <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> . Например, вызов метода <xref:System.Int32.ToString?displayProperty=nameWithType> по умолчанию в итоге приведет к подобному вызову метода: `Int32.ToString("G", System.Globalization.CultureInfo.CurrentCulture)`.

.NET предоставляет следующие три класса, реализующие интерфейс <xref:System.IFormatProvider>.

- <xref:System.Globalization.DateTimeFormatInfo>: класс, предоставляющий сведения о форматировании значений даты и времени для конкретного языка и региональных параметров. Реализация метода <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> в этом классе возвращает его экземпляр.

- <xref:System.Globalization.NumberFormatInfo>: класс, предоставляющий сведения о форматировании числовых значений для конкретного языка и региональных параметров. Реализация метода <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> в этом классе возвращает его экземпляр.

- <xref:System.Globalization.CultureInfo>. Реализация метода <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> в этом классе возвращает объект <xref:System.Globalization.NumberFormatInfo> , предоставляющий сведения о форматировании числовых значений, либо объект <xref:System.Globalization.DateTimeFormatInfo> , предоставляющий сведения о форматировании значений даты и времени.

Также можно реализовать пользовательский поставщик форматирования, позволяющий заменить любой из этих классов. При этом пользовательская реализация метода <xref:System.IFormatProvider.GetFormat%2A>, рассчитанная на предоставление сведений о форматировании для метода `ToString`, должна возвращать объект одного из типов, перечисленных в приведенной выше таблице.

### <a name="culture-sensitive-formatting-of-numeric-values"></a>Форматирование числовых значений, зависящее от языка и региональных параметров

По умолчанию форматирование числовых значений зависит от языка и региональных параметров. Если не указать язык и региональные параметры при вызове метода форматирования, используются соглашения о форматировании текущего языка и региональных параметров. Это продемонстрировано в следующем примере, который изменяет текущие язык и региональные параметры четыре раза, а затем вызывает метод <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType> . В каждом случае результирующая строка отражает соглашения о форматировании текущих языка и региональных параметров. Это происходит потому, что методы `ToString` и `ToString(String)` создают оболочки для вызовов метода `ToString(String, IFormatProvider)` каждого числового типа.

[!code-csharp[Conceptual.Formatting.Overview#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/culturespecific3.cs#19)]
[!code-vb[Conceptual.Formatting.Overview#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/culturespecific3.vb#19)]

Отформатировать числовое значение для определенных языка и региональных параметров также можно путем вызова перегрузки метода `ToString` , которая имеет параметр `provider` , и передачи ей одного из следующих объектов:

- объекта <xref:System.Globalization.CultureInfo> , представляющего язык и региональные параметры, соглашения о форматировании которых требуется использовать. Его метод <xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=nameWithType> возвращает значение свойства <xref:System.Globalization.CultureInfo.NumberFormat%2A?displayProperty=nameWithType> , которое является объектом <xref:System.Globalization.NumberFormatInfo> , предоставляющим сведения о форматировании в соответствии с языком и региональными параметрами для числовых значений;

- объекта <xref:System.Globalization.NumberFormatInfo> , определяющего соглашения о форматировании для используемых языка и региональных параметров. Метод <xref:System.Globalization.NumberFormatInfo.GetFormat%2A> этого класса возвращает экземпляр его самого.

В следующем примере объекты <xref:System.Globalization.NumberFormatInfo> , представляющие "Английский (США)" и "Английский (Соединенное Королевство)" язык и региональные параметры, а также "Французский" и "Русский" нейтральные языки и региональные параметры, используются для форматирования числа с плавающей запятой.

[!code-csharp[Conceptual.Formatting.Overview#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/culturespecific4.cs#20)]
[!code-vb[Conceptual.Formatting.Overview#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/culturespecific4.vb#20)]

### <a name="culture-sensitive-formatting-of-date-and-time-values"></a>Форматирование значений даты и времени, зависящее от языка и региональных параметров

По умолчанию форматирование значений даты и времени зависит от языка и региональных параметров. Если не указать язык и региональные параметры при вызове метода форматирования, используются соглашения о форматировании текущего языка и региональных параметров. Это продемонстрировано в следующем примере, который изменяет текущие язык и региональные параметры четыре раза, а затем вызывает метод <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> . В каждом случае результирующая строка отражает соглашения о форматировании текущих языка и региональных параметров. Это происходит потому, что методы <xref:System.DateTime.ToString?displayProperty=nameWithType>, <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ToString?displayProperty=nameWithType>и <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> создают оболочки для вызовов методов <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> и <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> .

[!code-csharp[Conceptual.Formatting.Overview#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/culturespecific1.cs#17)]
[!code-vb[Conceptual.Formatting.Overview#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/culturespecific1.vb#17)]

Форматировать значения даты и времени для определенных языка и региональных параметров также можно путем вызова перегрузки методов <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> или <xref:System.DateTimeOffset.ToString%2A?displayProperty=nameWithType> , которая имеет параметр `provider` , и передачи ей одного из следующих объектов:

- объекта <xref:System.Globalization.CultureInfo> , представляющего язык и региональные параметры, соглашения о форматировании которых требуется использовать. Его метод <xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=nameWithType> возвращает значение свойства <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> , которое является объектом <xref:System.Globalization.DateTimeFormatInfo> , предоставляющим сведения о форматировании в соответствии с языком и региональными параметрами для значений даты и времени;

- объекта <xref:System.Globalization.DateTimeFormatInfo> , определяющего соглашения о форматировании для используемых языка и региональных параметров. Метод <xref:System.Globalization.DateTimeFormatInfo.GetFormat%2A> этого класса возвращает экземпляр его самого.

В следующем примере объекты <xref:System.Globalization.DateTimeFormatInfo> , представляющие "Английский (США)" и "Английский (Соединенное Королевство)" язык и региональные параметры, а также "Французский" и "Русский" нейтральные языки и региональные параметры, используются для форматирования даты.

[!code-csharp[Conceptual.Formatting.Overview#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/culturespecific2.cs#18)]
[!code-vb[Conceptual.Formatting.Overview#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/culturespecific2.vb#18)]

## <a name="the-iformattable-interface"></a>Интерфейс IFormattable

Обычно типы, в которых имеется перегрузка метода `ToString` , использующая строку формата и параметр <xref:System.IFormatProvider> , также реализуют интерфейс <xref:System.IFormattable> . Единственный член этого интерфейса — метод <xref:System.IFormattable.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, параметрами которого являются строка формата и поставщик форматирования.

Реализация интерфейса <xref:System.IFormattable> в прикладных типах позволяет получить два преимущества:

- Поддержка строковых преобразований с помощью класса <xref:System.Convert> . При вызове методов <xref:System.Convert.ToString%28System.Object%29?displayProperty=nameWithType> и <xref:System.Convert.ToString%28System.Object%2CSystem.IFormatProvider%29?displayProperty=nameWithType> автоматически вызывается пользовательская реализация <xref:System.IFormattable> .

- Поддержка составного форматирования. Если для форматирования пользовательского типа используется элемент форматирования, включающий строку формата, то среда CLR автоматически вызывает пользовательскую реализацию <xref:System.IFormattable> , передавая ей строку формата. Дополнительные сведения о составном форматировании с помощью таких методов, как <xref:System.String.Format%2A?displayProperty=nameWithType> или <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, см. в подразделе [Составное форматирование](#composite-formatting) .

В следующем примере определяется класс `Temperature` , реализующий интерфейс <xref:System.IFormattable> . Он поддерживает описатели формата "C" и "G", позволяющие отобразить значение температуры в градусах Цельсия, описатель формата "F", позволяющий отобразить значение температуры в градусах Фаренгейта, и описатель формата "K", позволяющий отобразить значение температуры в градусах Кельвина.

[!code-csharp[Conceptual.Formatting.Overview#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/iformattable.cs#12)]
[!code-vb[Conceptual.Formatting.Overview#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/iformattable.vb#12)]

В следующем примере создается объект `Temperature`. Затем в нем вызывается метод <xref:System.Convert.ToString%2A> . Использование нескольких строк составного формата позволяет получить различные строковые представления объекта `Temperature` . В свою очередь каждый из этих вызовов метода вызывает реализацию <xref:System.IFormattable> класса `Temperature` .

[!code-csharp[Conceptual.Formatting.Overview#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/iformattable.cs#13)]
[!code-vb[Conceptual.Formatting.Overview#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/iformattable.vb#13)]

## <a name="composite-formatting"></a>Составное форматирование

Некоторые методы, например <xref:System.String.Format%2A?displayProperty=nameWithType> и <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>, поддерживают составное форматирование. Строка составного формата — это некий шаблон, возвращающий единую строку, включающую строковое представление нулевого, единичного или другого числа объектов. Каждый объект представляется в строке составного формата индексированным элементом форматирования. Индекс элемента форматирования соответствует положению представляющего его объекта в списке параметров метода. Индексы отсчитываются от нуля. Например, в вызове метода <xref:System.String.Format%2A?displayProperty=nameWithType> первый элемент форматирования, `{0:D}`, замещается строковым представлением `thatDate`; второй элемент форматирования, `{1}`, замещается строковым представлением `item1`; а третий элемент форматирования, `{2:C2}`, замещается строковым представлением `item1.Value`.

[!code-csharp[Conceptual.Formatting.Overview#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/composite1.cs#14)]
[!code-vb[Conceptual.Formatting.Overview#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/composite1.vb#14)]

Помимо замены элементов форматирования строковыми представлениями соответствующего объекта, элементы форматирования также позволяют управлять перечисленными ниже аспектами.

- Вы можете указать конкретный способ представления объекта в виде строки, если объект реализует интерфейс <xref:System.IFormattable> и поддерживает строки формата. Для этого после индекса элемента форматирования необходимо ввести `:` (двоеточие), а за ним — допустимую строку формата. В предыдущем примере для этого выполнялось форматирование значения даты с помощью строки формата "d" (шаблон короткого формата даты, например, `{0:d}`) и форматирование числового значения с помощью строки формата "C2" (например, `{2:C2}` для представления числа в виде значения валюты с двумя цифрами дробной части).

- Вы можете задать ширину поля, содержащего строковое представление объекта, и выравнивание строкового представления в этом поле. Для этого после индекса элемента форматирования необходимо ввести `,` (запятую), а за ней — значение ширины поля. Строка выравнивается по правому краю поля, если ширина поля — положительное значение, и по левому краю, если ширина поля — отрицательное значение. В примере ниже значения даты выравниваются по левому краю поля из 20 символов, а десятичные значения с одной цифрой дробной части — по правом краю поля из 11 символов.

     [!code-csharp[Conceptual.Formatting.Overview#22](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/composite2.cs#22)]
     [!code-vb[Conceptual.Formatting.Overview#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/composite2.vb#22)]

     Обратите внимание на то, что если присутствует и компонент выравнивания строки, и компонент строки формата, первый из них предшествует последнему (например, `{0,-20:g}`).

Дополнительные сведения о составном форматировании см. в разделе [Composite Formatting](../../../docs/standard/base-types/composite-formatting.md).

## <a name="custom-formatting-with-icustomformatter"></a>Настраиваемое форматирование с использованием интерфейса ICustomFormatter

У двух методов составного форматирования — <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> и <xref:System.Text.StringBuilder.AppendFormat%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>— также имеется параметр, задающий поставщик форматирования, поддерживающий настраиваемое форматирование. При вызове какого-либо из этих методов форматирования объект <xref:System.Type> , представляющий интерфейс <xref:System.ICustomFormatter> , передается методу <xref:System.IFormatProvider.GetFormat%2A> поставщика форматирования. Метод <xref:System.IFormatProvider.GetFormat%2A> должен вернуть реализацию <xref:System.ICustomFormatter> , поддерживающую настраиваемое форматирование.

Единственный метод интерфейса <xref:System.ICustomFormatter> , который называется <xref:System.ICustomFormatter.Format%28System.String%2CSystem.Object%2CSystem.IFormatProvider%29>, автоматически вызывается методом составного форматирования по одному разу для каждого элемента форматирования в строке составного формата. У метода <xref:System.ICustomFormatter.Format%28System.String%2CSystem.Object%2CSystem.IFormatProvider%29> есть три параметра: строка формата, представляющая аргумент `formatString` в элементе форматирования, сам форматируемый объект и объект <xref:System.IFormatProvider> , предоставляющий услуги форматирования. Обычно класс, реализующий интерфейс <xref:System.ICustomFormatter> , также реализует интерфейс <xref:System.IFormatProvider>, поэтому в таком случае последний параметр будет ссылкой на сам класс настраиваемого форматирования. Метод возвращает настраиваемое строковое представление объекта, который нужно было отформатировать. Если методу не удается отформатировать объект, он должен вернуть пустую ссылку (`Nothing` в Visual Basic).

В следующем примере приведена реализация <xref:System.ICustomFormatter> с именем `ByteByByteFormatter` , отображающая целочисленные значения в виде последовательности пар шестидесятеричных цифр, разделенных пробелами.

[!code-csharp[Conceptual.Formatting.Overview#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/icustomformatter1.cs#15)]
[!code-vb[Conceptual.Formatting.Overview#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/icustomformatter1.vb#15)]

В следующем примере класс `ByteByByteFormatter` используется для форматирования целочисленных значений. Обратите внимание, что метод <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> вызывается во втором вызове метода <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> несколько раз и что в третьем вызове метода используется поставщик <xref:System.Globalization.NumberFormatInfo> по умолчанию, поскольку метод`ByteByByteFormatter.Format` не распознает строку формата "N0" и возвращает пустую ссылку (`Nothing` в Visual Basic).

[!code-csharp[Conceptual.Formatting.Overview#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/icustomformatter1.cs#16)]
[!code-vb[Conceptual.Formatting.Overview#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/icustomformatter1.vb#16)]

## <a name="related-topics"></a>См. также

|Заголовок|Определение|
|-----------|----------------|
|[Standard Numeric Format Strings](../../../docs/standard/base-types/standard-numeric-format-strings.md)|Описание строк стандартного формата, позволяющих создавать общеупотребимые строковые представления числовых значений.|
|[Custom Numeric Format Strings](../../../docs/standard/base-types/custom-numeric-format-strings.md)|Описание строк настраиваемого формата, позволяющих создавать прикладные строковые представления числовых значений.|
|[Строки стандартных форматов даты и времени](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)|Описание строк стандартного формата, позволяющих создавать общеупотребимые строковые представления значений <xref:System.DateTime> .|
|[Строки настраиваемых форматов даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)|Описание строк настраиваемого формата, позволяющих создавать прикладные строковые представления значений <xref:System.DateTime> .|
|[Строки стандартного формата TimeSpan](../../../docs/standard/base-types/standard-timespan-format-strings.md)|Описание строк стандартного формата, позволяющих создавать общеупотребимые строковые представления интервалов времени.|
|[Строки настраиваемого формата TimeSpan](../../../docs/standard/base-types/custom-timespan-format-strings.md)|Описание строк настраиваемого формата, позволяющих создавать прикладные строковые представления интервалов времени.|
|[Enumeration Format Strings](../../../docs/standard/base-types/enumeration-format-strings.md)|Описание строк стандартного формата, используемых для создания строковых представлений значений перечислений.|
|[Составное форматирование](../../../docs/standard/base-types/composite-formatting.md)|Описание способа совмещения нескольких форматируемых значений в строке. Строка может быть последовательно отображена в консоли или выведена в поток.|
|[Выполнение операций форматирования](../../../docs/standard/base-types/performing-formatting-operations.md)|Перечень разделов, содержащих пошаговые инструкции для выполнения конкретных операций форматирования.|
|[Parsing Strings](../../../docs/standard/base-types/parsing-strings.md)|Описание способов инициализации объектов со значениями, описанными строковыми представлениями этих объектов. Разбор является операцией, обратной форматированию.|

## <a name="reference"></a>Ссылка

- <xref:System.IFormattable?displayProperty=nameWithType>
- <xref:System.IFormatProvider?displayProperty=nameWithType>
- <xref:System.ICustomFormatter?displayProperty=nameWithType>
