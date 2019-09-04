---
title: Сопоставление методов CLR с каноническими функциями
ms.date: 03/30/2017
ms.assetid: e3363261-2cb8-4b54-9555-2870be99b929
ms.openlocfilehash: 6f14ad8d9e8f919fe820447cc991b102319b38d5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251227"
---
# <a name="clr-method-to-canonical-function-mapping"></a>Сопоставление методов CLR с каноническими функциями

Платформа Entity Framework предоставляет набор канонических функций, которые реализуют операции над строками, математические функции и другую общую функциональность для многих систем баз данных. Это позволяет разработчикам работать с широким кругом систем баз данных. При вызове из технологии запросов (например, из LINQ to Entities) канонические функции преобразуются в соответствующую функцию хранилища для используемого поставщика. Это позволяет для различных источников данных выражать вызовы функций в общей форме, обеспечивая согласованность при применении запросов. Битовые операторы AND, OR, NOT и XOR также сопоставляются с каноническими функциями, если операнд имеет числовой тип. Для операндов логического типа битовые операторы AND, OR, NOT и XOR выполняют логические операции «И», «ИЛИ», «НЕ» и «Исключающее ИЛИ». Дополнительные сведения см. в разделе [канонические функции](canonical-functions.md).

Для сценариев LINQ запросы к платформе Entity Framework включают сопоставление определенных методов CLR с методами базового источника данных через канонические функции. Любой вызов метода в запросе LINQ to Entities, который явно не сопоставлен с канонической функцией, приведет к активизации исключения времени выполнения <xref:System.NotSupportedException>.

## <a name="systemstring-method-static-mapping"></a>Сопоставление метода System.String (статический)

|Метод System.String (статический)|Каноническая функция|
|-------------------------------------|------------------------|
|System.String Concat(String `str0`, String `str1`)|Concat(`str0`, `str1`)|
|System.String Concat(String `str0`, String `str1`, String `str2`)|Concat(Concat(`str0`, `str1`), `str2`)|
|System.String Concat(String `str0`, String `str1`, String `str2`, String `str03`)|Concat(Concat(Concat(`str0`, `str1`), `str2`), `str3`)|
|Boolean Equals(String `a`, String `b`)|= - оператор|
|Boolean IsNullOrEmpty(String `value`)|(IsNull(`value`)) OR Length(`value`) = 0|
|Boolean op_Equality(String `a`, String `b`)|= - оператор|
|Boolean op_Inequality(String `a` , String `b`)|!= - оператор|
|Microsoft.VisualBasic.Strings.Trim(String `str`)|Trim(`str`)|
|Microsoft.VisualBasic.Strings.LTrim(String `str`)|Ltrim(`str`)|
|Microsoft.VisualBasic.Strings.RTrim(String `str`)|Rtrim(`str`)|
|Microsoft.VisualBasic.Strings.Len(String `expression`)|Length(`expression`)|
|Microsoft.VisualBasic.Strings.Left(String `str`, Int32 `Length`)|Left(`str`, `Length`)|
|Microsoft.VisualBasic.Strings.Mid(String `str`, Int32 `Start`, Int32 `Length`)|Substring(`str`, `Start`, `Length`)|
|Microsoft.VisualBasic.Strings.Right(String `str`, Int32 `Length`)|Right(`str`, `Length`)|
|Microsoft.VisualBasic.Strings.UCase(String `Value`)|ToUpper(`Value`)|
|Microsoft.VisualBasic.Strings.LCase(String Value)|ToLower(`Value`)|

## <a name="systemstring-method-instance-mapping"></a>Сопоставление метода System.String (экземпляр)

|Метод System.String (экземпляр)|Каноническая функция|Примечания|
|---------------------------------------|------------------------|-----------|
|Boolean Contains(String `value`)|`this` LIKE '%`value`%'|Если `value` не является константой, то этот объект сопоставляется с`this`IndexOf `value`(,) > 0|
|Boolean EndsWith(String `value`)|`this`LIKE `'` '% `value`|Если `value` не является константой, от он сопоставляется с Right(`this`, length(`value`)) = `value`.|
|Boolean StartsWith(String `value`)|`this` LIKE '`value`%'|Если `value` не является константой, от он сопоставляется с IndexOf(`this`, `value`) = 1.|
|Длина|Length(`this`)||
|Int32 IndexOf(String `value`)|IndexOf(`this`, `value`) - 1||
|System.String Insert(Int32 `startIndex`, String `value`)|Concat(Concat(Substring(`this`, 1, `startIndex`), `value`), Substring(`this`, `startIndex`+1, Length(`this`) - `startIndex`))||
|System.String Remove(Int32 `startIndex`)|Substring(`this`, 1, `startIndex`)||
|System.String Remove(Int32 `startIndex`, Int32 `count`)|Concat (`this`substring (, 1, `startIndex`), substring (`this`,`this` + `count``startIndex` `count` `startIndex`  +  + 1, Length ()-()))|Remove(`startIndex`, `count`) поддерживается, только если `count` - это неотрицательное целое число.|
|System.String Replace(String `oldValue`, String `newValue`)|Replace(`this`, `oldValue`, `newValue`)||
|System.String Substring(Int32 `startIndex`)|Substring(`this`, `startIndex` +1, Length(`this`) - `startIndex`)||
|System.String Substring(Int32 `startIndex`, Int32 `length`)|Подстрока`this`( `startIndex` , + 1 `length`,)||
|System.String ToLower()|ToLower(`this`)||
|System.String ToUpper()|ToUpper(`this`)||
|System.String Trim()|Trim(`this`)||
|System.String TrimEnd(Char[] `trimChars`)|RTrim(`this`)||
|System.String TrimStart(Char[]`trimChars`)|LTrim(`this`)||
|Boolean Equals(String `value`)|= - оператор||

## <a name="systemdatetime-method-static-mapping"></a>Сопоставление метода System.DateTime (статический)

|Метод System.DateTime (статический)|Каноническая функция|Примечания|
|---------------------------------------|------------------------|-----------|
|Boolean Equals(DateTime `t1`, DateTime `t2`)|= - оператор||
|System.DateTime.Now|CurrentDateTime()||
|System.DateTime.UtcNow|CurrentUtcDateTime()||
|Boolean op_Equality(DateTime `d1`, DateTime `d2`)|= - оператор||
|Boolean op_GreaterThan(DateTime `t1`, DateTime `t2`)|Оператор >||
|Boolean op_GreaterThanOrEqual(DateTime `t1`, DateTime `t2`)|Оператор > =||
|Boolean op_Inequality(DateTime `t1`, DateTime `t2`)|!= - оператор||
|Boolean op_LessThan (DateTime `t1`, DateTime `t2`)|Оператор <||
|Boolean op_LessThanOrEqual(DateTime `t1`, DateTime `t2`)|Оператор < =||
|Microsoft.VisualBasic.DateAndTime.DatePart( _<br /><br /> ByVal `Interval` как DateInterval;\_<br /><br /> ByVal `DateValue` как DateTime,\_<br /><br /> Необязательное значение ByVal `FirstDayOfWeekValue` как FirstDayOfWeek = вбсундай,\_<br /><br /> Необязательное значение ByVal `FirstWeekOfYearValue` как первая_неделя_года = VbFirstJan1\_<br /><br /> ) As Integer||Дополнительные сведения см. в разделе «Функция DatePart».|
|Microsoft.VisualBasic.DateAndTime.Now|CurrentDateTime()||
|Microsoft.VisualBasic.DateAndTime.Year(DateTime `TimeValue`)|Year()||
|Microsoft.VisualBasic.DateAndTime.Month(DateTime `TimeValue`)|Month()||
|Microsoft.VisualBasic.DateAndTime.Day(DateTime `TimeValue`)|Day()||
|Microsoft.VisualBasic.DateAndTime.Hour(DateTime `TimeValue`)|Hour()||
|Microsoft.VisualBasic.DateAndTime.Minute(DateTime `TimeValue`)|Minute()||
|Microsoft.VisualBasic.DateAndTime.Second(DateTime `TimeValue`)|Second()||

## <a name="systemdatetime-method-instance-mapping"></a>Сопоставление метода System.DateTime (экземпляр)

|Метод System.DateTime (экземпляр)|Каноническая функция|
|-----------------------------------------|------------------------|
|Boolean Equals(DateTime `value`)|= - оператор|
|День|Day(`this`)|
|Час|Hour(`this`)|
|Millisecond|Millisecond(`this`)|
|Минута|Minute(`this`)|
|Месяц|Month(`this`)|
|Вторая|Second(`this`)|
|Год|Year(`this`)|

## <a name="systemdatetimeoffset-method-instance-mapping"></a>Сопоставление метода System.DateTimeOffset (экземпляр)

Сопоставление, выводимое для методов `get` с указанными свойствами.

|Метода System.DateTimeOffset (экземпляр)|Каноническая функция|Примечания|
|-----------------------------------------------|------------------------|-----------|
|День|Day(`this`)|Не поддерживается для SQL Server 2005.|
|Час|Hour(`this`)|Не поддерживается для SQL Server 2005.|
|Millisecond|Millisecond(`this`)|Не поддерживается для SQL Server 2005.|
|Минута|Minute(`this`)|Не поддерживается для SQL Server 2005.|
|Месяц|Month(`this`)|Не поддерживается для SQL Server 2005.|
|Вторая|Second(`this`)|Не поддерживается для SQL Server 2005.|
|Год|Year(`this`)|Не поддерживается для SQL Server 2005.|

> [!NOTE]
> Метод <xref:System.DateTimeOffset.Equals%2A> возвращает значение `true`, если сравниваемые объекты <xref:System.DateTimeOffset> равны, и значение `false` в противном случае. Метод <xref:System.DateTimeOffset.CompareTo%2A> возвращает значение 0, 1 или -1 в зависимости от состояния объекта <xref:System.DateTimeOffset> (соответственно равен, больше или меньше).

## <a name="systemdatetimeoffset-method-static-mapping"></a>Сопоставление метода System.DateTimeOffset (статический)

Сопоставление, выводимое для методов `get` с указанными свойствами.

|Метод System.DateTimeOffset (статический)|Каноническая функция|Примечания|
|---------------------------------------------|------------------------|-----------|
|System.DateTimeOffset.Now()|CurrentDateTimeOffset()|Не поддерживается для SQL Server 2005.|

## <a name="systemtimespan-method-instance-mapping"></a>Сопоставление метода System.TimeSpan (экземпляр)

Сопоставление, выводимое для методов `get` с указанными свойствами.

|Метод System.TimeSpan (экземпляр)|Каноническая функция|Примечания|
|-----------------------------------------|------------------------|-----------|
|Часы.|Hour(`this`)|Не поддерживается для SQL Server 2005.|
|Milliseconds|Millisecond(`this`)|Не поддерживается для SQL Server 2005.|
|Минуты|Minute(`this`)|Не поддерживается для SQL Server 2005.|
|Seconds|Second(`this`)|Не поддерживается для SQL Server 2005.|

> [!NOTE]
> Метод <xref:System.TimeSpan.Equals%2A> возвращает значение `true`, если сравниваемые объекты <xref:System.TimeSpan> равны, и значение `false` в противном случае. Метод <xref:System.TimeSpan.CompareTo%2A> возвращает значение 0, 1 или -1 в зависимости от состояния объекта <xref:System.TimeSpan> (соответственно равен, больше или меньше).

### <a name="datepart-function"></a>Функция DatePart

Функция `DatePart` сопоставляется с одной или несколькими каноническими функциями в зависимости от значения `Interval`. В следующей таблице приведено сопоставление канонических функций для поддерживаемых значений `Interval`.

|Значение интервала|Каноническая функция|
|--------------------|------------------------|
|DateInterval.Year|Year()|
|DateInterval.Month|Month()|
|DateInterval.Day|Day()|
|DateInterval.Hour|Hour()|
|DateInterval.Minute|Minute()|
|DateInterval.Second|Second()|

## <a name="mathematical-function-mapping"></a>Сопоставление математических функций

|Метод CLR|Каноническая функция|
|----------------|------------------------|
|System.Decimal.Ceiling(Decimal `d`)|Ceiling(`d`)|
|System.Decimal.Floor(Decimal `d`)|Floor(`d`)|
|System.Decimal.Round(Decimal `d`)|Round(`d`)|
|System.Math.Ceiling(Decimal `d`)|Ceiling(`d`)|
|System.Math.Floor(Decimal `d`)|Floor(`d`)|
|System.Math.Round(Decimal `d`)|Round(`d`)|
|System.Math.Ceiling(Double `a`)|Ceiling(`a`)|
|System.Math.Floor(Double `a`)|Floor(`a`)|
|System.Math.Round(Double `a`)|Round(`a`)|
|System.Math.Round(значение Double, количество знаков Int16)|Round(значение, количество знаков)|
|System.Math.Round(значение Double, количество знаков Int32)|Round(значение, количество знаков)|
|System.Math.Round(значение Decimal, количество знаков Int16)|Round(значение, количество знаков)|
|System.Math.Round(значение Decimal, количество знаков Int32)|Round(значение, количество знаков)|
|System.Math.Abs(значение Int16)|Abs(значение)|
|System.Math.Abs(значение Int32)|Abs(значение)|
|System.Math.Abs(значение Int64)|Abs(значение)|
|System.Math.Abs(значение Byte)|Abs(значение)|
|System.Math.Abs(значение Single)|Abs(значение)|
|System.Math.Abs(значение Double)|Abs(значение)|
|System.Math.Abs(значение Decimal)|Abs(значение)|
|System.Math.Truncate(значение Double, количество знаков Int16)|Truncate(значение, количество знаков)|
|System.Math.Truncate(значение Double, количество знаков Int32)|Truncate(значение, количество знаков)|
|System.Math.Truncate(значение Decimal, количество знаков Int16)|Truncate(значение, количество знаков)|
|System.Math.Truncate(значение Decimal, количество знаков Int32)|Truncate(значение, количество знаков)|
|System.Math.Power(значение Int32, показатель степени Int64)|Power(значение, показатель степени)|
|System.Math.Power(значение Int32, показатель степени Double)|Power(значение, показатель степени)|
|System.Math.Power(значение Int32, показатель степени Decimal)|Power(значение, показатель степени)|
|System.Math.Power(значение Int64, показатель степени Int64)|Power(значение, показатель степени)|
|System.Math.Power(значение Int64, показатель степени Double)|Power(значение, показатель степени)|
|System.Math.Power(значение Int64, показатель степени Decimal)|Power(значение, показатель степени)|
|System.Math.Power(значение Double, показатель степени Int64)|Power(значение, показатель степени)|
|System.Math.Power(значение Double, показатель степени Double)|Power(значение, показатель степени)|
|System.Math.Power(значение Double, показатель степени Decimal)|Power(значение, показатель степени)|
|System.Math.Power(значение Decimal, показатель степени Int64)|Power(значение, показатель степени)|
|System.Math.Power(значение Decimal, показатель степени Double)|Power(значение, показатель степени)|
|System.Math.Power(значение Decimal, показатель степени Decimal)|Power(значение, показатель степени)|

## <a name="bitwise-operator-mapping"></a>Сопоставление побитовых операторов

|Побитовый оператор|Канонические функции для нелогических операндов|Канонические функции для логических операндов|
|----------------------|--------------------------------------------------|---------------------------------------------|
|Побитовый оператор AND|BitWiseAnd|op1 AND op2|
|Побитовый оператор OR|BitWiseOr|op1 OR op2|
|Побитовый оператор NOT|BitWiseNot|NOT(op)|
|Побитовый оператор XOR|BitWiseXor|((op1 AND NOT(op2)) OR (NOT(op1) AND op2))|

## <a name="other-mapping"></a>Другое сопоставление

|Метод|Каноническая функция|
|------------|------------------------|
|Guid.NewGuid()|NewGuid()|

## <a name="see-also"></a>См. также

- [LINQ to Entities](linq-to-entities.md)
