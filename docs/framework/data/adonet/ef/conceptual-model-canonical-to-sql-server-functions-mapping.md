---
title: Сопоставление канонических функций концептуальной модели с функциями SQL Server
ms.date: 03/30/2017
ms.assetid: 1a2631bc-a426-4c0a-ba8d-26d9c80d39e2
ms.openlocfilehash: f997fbf39f3dee07cc0d58a39fca779f55236606
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251677"
---
# <a name="conceptual-model-canonical-to-sql-server-functions-mapping"></a>Сопоставление канонических функций концептуальной модели с функциями SQL Server
В этом разделе описано, как канонические функции концептуальной модели сопоставляются соответствующим функциям SQL Server.  
  
## <a name="date-and-time-functions"></a>Функции даты и времени  
 В следующей таблице описано сопоставление функций даты и времени.  
  
|Канонические функции|Функции SQL Server|  
|-------------------------|--------------------------|  
|[AddDays (выражение)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(day, number, date)`|  
|[AddHours (выражение)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(hour, number, date)`|  
|[Аддмикросекондс (выражение)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(microsecond, number, date)`|  
|[AddMilliseconds(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(millisecond, number, date)`|  
|[Аддминутес (выражение)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(minute, number, date)`|  
|[AddMonths(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(month, number, date)`|  
|[Адднаносекондс (выражение)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(nanosecond, number, date)`|  
|[Аддсекондс (выражение)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(second, number, date)`|  
|[Аддеарс (выражение)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(year, number, date)`|  
|[Креатедатетиме (год, месяц, день, час, минута, секунда)](./language-reference/date-and-time-canonical-functions.md)|В SQL Server 2000 и SQL Server 2005 на сервере создается форматированное значение `datetime`. В SQL Server 2008 и более поздних версиях на сервере создается значение `datetime2`.|  
|[Креатедатетимеоффсет (год, месяц, день, час, минута, секунда, TZoffset)](./language-reference/date-and-time-canonical-functions.md)|На сервере создается форматированное значение `datetimeoffset`.<br /><br /> Не поддерживается в SQL Server 2000 и SQL Server 2005.|  
|[Креатетиме (час, минута, секунда)](./language-reference/date-and-time-canonical-functions.md)|На сервере создается форматированное значение `time`.<br /><br /> Не поддерживается в SQL Server 2000 и SQL Server 2005.|  
|[Куррентдатетиме ()](./language-reference/date-and-time-canonical-functions.md)|`SysDateTime()` в SQLServer 2008.<br /><br /> `GetDate()` в SQLServer 2000 и SQLServer 2005.|  
|[CurrentDateTimeOffset()](./language-reference/date-and-time-canonical-functions.md)|`SysDateTimeOffset()` в SQL Server 2008.<br /><br /> Не поддерживается в SQL Server 2000 и SQL Server 2005.|  
|[CurrentUtcDateTime ()](./language-reference/date-and-time-canonical-functions.md)|`SysUtcDateTime()` в SQLServer 2008. `GetUtcDate()` в SQL Server 2000 и SQL Server 2005.|  
|[DayOfYear (выражение)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(dayofyear, expression)`|  
|[Day(expression)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(day, expression)`|  
|[Диффдайс (Стартекспрессион, Ендекспрессион)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(day, startdate, enddate)`|  
|[Диффхаурс (Стартекспрессион, Ендекспрессион)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(hour, startdate, enddate)`|  
|[Диффмикросекондс (Стартекспрессион, Ендекспрессион)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(microsecond, startdate, enddate)`|  
|[Диффмиллисекондс (Стартекспрессион, Ендекспрессион)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(millisecond, startdate, enddate)`|  
|[Диффминутес (Стартекспрессион, Ендекспрессион)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(minute, startdate, enddate)`|  
|[Диффнаносекондс (Стартекспрессион, Ендекспрессион)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(nanosecond, startdate, enddate)`|  
|[Диффсекондс (Стартекспрессион, Ендекспрессион)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(second, startdate, enddate)`|  
|[Диффеарс (Стартекспрессион, Ендекспрессион)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(year, startdate, enddate)`|  
|[Жеттоталоффсетминутес (DateTimeOffset)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(tzoffset, expression)`|  
|[Hour (выражение)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(hour, expression)`|  
|[Миллисекунда (выражение)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(millisecond, expression)`|  
|[Minute (выражение)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(minute, expression)`|  
|[Month (выражение)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(month, expression)`|  
|[Второе (выражение)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(second, expression)`|  
|[Truncate (выражение)](./language-reference/date-and-time-canonical-functions.md)|Для SQL Server 2000 и SQL Server 2005 на сервере создается усеченное `datetime` отформатированное значение. Для SQL Server 2008 и более поздних версий на сервере `datetime2` создается `datetimeoffset` усеченное значение или.|  
|[Year (выражение)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(YEAR, expression)`|  
  
## <a name="aggregate-functions"></a>Статистические функции  
 В следующей таблице описано сопоставление агрегатных функций.  
  
|Канонические функции|Функции SQL Server|  
|-------------------------|--------------------------|  
|[AVG (выражение)](./language-reference/aggregate-canonical-functions.md)|`AVG(expression)`|  
|[BigCount(expression)](./language-reference/aggregate-canonical-functions.md)|`BIGCOUNT(expression)`|  
|[Count (выражение)](./language-reference/aggregate-canonical-functions.md)|`COUNT(expression)`|  
|[Min (выражение)](./language-reference/aggregate-canonical-functions.md)|`MIN(expression)`|  
|[Max (выражение)](./language-reference/aggregate-canonical-functions.md)|`MAX(expression)`|  
|[StDev (выражение)](./language-reference/aggregate-canonical-functions.md)|`STDEV(expression)`|  
|[StDevP (выражение)](./language-reference/aggregate-canonical-functions.md)|`STDEVP(expression)`|  
|[Sum (выражение)](./language-reference/aggregate-canonical-functions.md)|`SUM(expression)`|  
|[Var (выражение)](./language-reference/aggregate-canonical-functions.md)|`VAR(expression)`|  
|[VarP (выражение)](./language-reference/aggregate-canonical-functions.md)|`VARP(expression)`|  
  
## <a name="math-functions"></a>Математические функции  
 В следующей таблице описано сопоставление математических функций.  
  
|Канонические функции|Функции SQL Server|  
|-------------------------|--------------------------|  
|[ABS (значение)](./language-reference/math-canonical-functions.md)|`ABS(value)`|  
|[CEILING (значение)](./language-reference/math-canonical-functions.md)|`CEILING(value)`|  
|[Floor (значение)](./language-reference/math-canonical-functions.md)|`FLOOR(value)`|  
|[Мощность (значение)](./language-reference/math-canonical-functions.md)|`POWER(value, exponent)`|  
|[Round (значение)](./language-reference/math-canonical-functions.md)|`ROUND(value, digits, 0)`|  
|[TRUNCATE](./language-reference/math-canonical-functions.md)|`ROUND(value , digits, 1)`|  
  
## <a name="string-functions"></a>Строковые функции  
 В следующей таблице описано сопоставление строковых функций.  
  
|Канонические функции|Функции SQL Server|  
|-------------------------|--------------------------|  
|[Contains (строка, целевой объект)](./language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Concat (строка1, строка2)](./language-reference/string-canonical-functions.md)|string1 + string2|  
|[EndsWith (строка, целевой объект)](./language-reference/string-canonical-functions.md)|`CHARINDEX(REVERSE(target), REVERSE(string)) = 1`<br /><br /> **Примечание** . Функция возвращает `false` , если объект `string` хранится в строковом столбце фиксированной длины и `target` является константой. `CHARINDEX` В данном случае производится поиск по всей строке, включая конечные пробелы заполнения в строке. Данную проблему можно обойти, усекая данные из строки с фиксированной длиной перед передачей их функции `EndsWith`, как это показано в следующем примере: `EndsWith(TRIM(string), target)`|  
|[IndexOf (цель, строка2)](./language-reference/string-canonical-functions.md)|`CHARINDEX(target, string2)`|  
|[Left (строка1, Length)](./language-reference/string-canonical-functions.md)|`LEFT(string1, length)`|  
|[Length (строка)](./language-reference/string-canonical-functions.md)|`LEN(string)`|  
|[LTrim (строка)](./language-reference/string-canonical-functions.md)|`LTRIM(string)`|  
|[Справа (строка1, Length)](./language-reference/string-canonical-functions.md)|`RIGHT (string1, length)`|  
|[Trim (строка)](./language-reference/string-canonical-functions.md)|`LTRIM(RTRIM(string))`|  
|[Replace (строка1, строка2, string3)](./language-reference/string-canonical-functions.md)|`REPLACE(string1, string2, string3)`|  
|[Reverse (строка)](./language-reference/string-canonical-functions.md)|`REVERSE (string)`|  
|[RTrim (строка)](./language-reference/string-canonical-functions.md)|`RTRIM(string)`|  
|[StartsWith (строка, цель)](./language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Substring (строка, начало, длина)](./language-reference/string-canonical-functions.md)|`SUBSTRING(string, start, length)`|  
|[ToLower (строка)](./language-reference/string-canonical-functions.md)|`LOWER(string)`|  
|[ToUpper (строка)](./language-reference/string-canonical-functions.md)|`UPPER(string)`|  
  
## <a name="bitwise-functions"></a>Битовые функции  
 В следующей таблице описано сопоставление битовых функций.  
  
|Канонические функции|Функции SQL Server|  
|-------------------------|--------------------------|  
|[BitWiseAnd (значение1, значение2)](./language-reference/bitwise-canonical-functions.md)|Значение1 & value2|  
|[Битвисенот (значение)](./language-reference/bitwise-canonical-functions.md)|~value|  
|[Побитовая (значение1, значение2)](./language-reference/bitwise-canonical-functions.md)|значение1 &#124; значение2|  
|[Битвисексор (значение1, значение2)](./language-reference/bitwise-canonical-functions.md)|value1 ^ value2|
