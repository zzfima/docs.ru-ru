---
title: "Функции преобразования типов (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.CUShort"
  - "vb.csng"
  - "vb.CDate"
  - "CByte"
  - "CSng"
  - "vb.CDec"
  - "CBool"
  - "CStr"
  - "vb.CULng"
  - "CDec"
  - "CVErr"
  - "CDbl"
  - "CShort"
  - "vb.CObj"
  - "vb.CVErr"
  - "CULng"
  - "vb.cdbl"
  - "vb.cbool"
  - "CObj"
  - "CDate"
  - "CLng"
  - "vb.cstr"
  - "vb.cbyte"
  - "vb.clng"
  - "vb.CChar"
  - "CUShort"
  - "vb.CUInt"
  - "vb.cint"
  - "vb.CShort"
  - "CInt"
  - "CUInt"
  - "CChar"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "банковское округление"
  - "boolean - тип данных, преобразование"
  - "Byte - тип данных, преобразование"
  - "CBool - функция"
  - "CByte - функция"
  - "CChar - функция"
  - "CDate - функция"
  - "CDbl - функция"
  - "CDec - функция"
  - "Char - тип данных, преобразование"
  - "CInt - функция"
  - "CLng - функция"
  - "преобразования, функции преобразования типов"
  - "CSByte - функция"
  - "CSng - функция"
  - "CStr - функция"
  - "CUInt - функция"
  - "CULng - функция"
  - "Currency - тип данных, функции преобразования"
  - "CUShort - функция"
  - "преобразование типов данных, функции для"
  - "типы данных [Visual Basic], преобразование"
  - "Date - тип данных, преобразование"
  - "даты, преобразование"
  - "Decimal - тип данных, преобразование"
  - "Double - тип данных, преобразование"
  - "числа двойной точности"
  - "дроби"
  - "Integer - тип данных, преобразование"
  - "целые числа, функции преобразования типов"
  - "Long - тип данных, преобразование"
  - "числа, преобразование"
  - "числа, округление"
  - "возвращаемые значения, типы данных"
  - "округление чисел, банковское округление"
  - "округление чисел, преобразование типов"
  - "Short - тип данных, преобразование"
  - "Single - тип данных, преобразование"
  - "числа одинарной точности, преобразование"
  - "преобразование строк, функции преобразования"
  - "String - тип данных, преобразование"
  - "текст, преобразование"
  - "значения времени, преобразование"
  - "преобразование типов, функции для"
  - "преобразование типов, Visual Basic в сравнении с .NET Framework"
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Функции преобразования типов (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Эти функции компилируются путем подстановки кода, т. е. код преобразования является частью кода, вычисляющего выражение.  В некоторых случаях отсутствует вызов процедуры для выполнения преобразований, что повышает производительность.  Каждая функция приводит выражение к определенному типу данных.  
  
## Синтаксис  
  
```  
CBool(expression)  
CByte(expression)  
CChar(expression)  
CDate(expression)  
CDbl(expression)  
CDec(expression)  
CInt(expression)  
CLng(expression)  
CObj(expression)  
CSByte(expression)  
CShort(expression)  
CSng(expression)  
CStr(expression)  
CUInt(expression)  
CULng(expression)  
CUShort(expression)  
```  
  
## Часть  
 `expression`  
 Обязательный.  Любое выражение исходного типа данных.  
  
## Тип данных возвращаемого значения.  
 Имя функции определяет возвращаемый тип, как показано в следующей таблице.  
  
|Имя функции|Возвращаемый тип данных.|Диапазон для аргумента `expression`|  
|-----------------|------------------------------|-----------------------------------------|  
|`CBool`|[Тип данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Любое допустимое `Char`, `String` или числовое выражение.|  
|`CByte`|[Тип данных Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)|от 0 до 255 \(без знака\); дробная часть округляется.<sup>1</sup>|  
|`CChar`|[Тип данных Char](../../../visual-basic/language-reference/data-types/char-data-type.md)|Любое допустимое `Char` или `String` выражение; преобразуется только первый знак `String`; значение может быть от 0 до 65535 \(без знака\).|  
|`CDate`|[Тип данных Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|Любое допустимое представление даты и времени.|  
|`CDbl`|[Тип данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|от \-1.79769313486231570E\+308 до \-4.94065645841246544E\-324 для отрицательных значений; от 4.94065645841246544E\-324 до 1.79769313486231570E\+308 для положительных значений.|  
|`CDec`|[Тип данных Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|\+\/\-79228162514264337593543950335 для целых чисел, т.е. чисел без знаков после запятой.  Для чисел с 28 десятичными разрядами диапазоном является \+\/\-7.9228162514264337593543950335.  Наименьшее возможное ненулевое число это 0.0000000000000000000000000001 \(\+\/\-1E\-28\).|  
|`CInt`|[Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)|от \-2147483648 до 2147483647; дробная часть округляется.<sup>1</sup>|  
|`CLng`|[Тип данных Long](../../../visual-basic/language-reference/data-types/long-data-type.md)|от \-9,223,372,036,854,775,808 до 9,223,372,036,854,775,807; дробная часть округляется.<sup>1</sup>|  
|`CObj`|[Тип данных Object](../../../visual-basic/language-reference/data-types/object-data-type.md)|Любое допустимое выражение.|  
|`CSByte`|[Тип данных SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|от \-128 до 127; дробная часть округляется.<sup>1</sup>|  
|`CShort`|[Тип данных Short](../../../visual-basic/language-reference/data-types/short-data-type.md)|от \-32768 до 32767; дробная часть округляется.<sup>1</sup>|  
|`CSng`|[Тип данных Single](../../../visual-basic/language-reference/data-types/single-data-type.md)|\(От \-3,402823E\+38 до \-1,401298E\-45 для отрицательных значений; от 1,401298E\-45 до 3,402823E\+38 для положительных значений.|  
|`CStr`|[Тип данных String](../../../visual-basic/language-reference/data-types/string-data-type.md)|Возвращаемые значения функции `CStr` зависят от аргумента `expression`.  Дополнительные сведения см. в разделе [Возвращаемые значения функции CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).|  
|`CUInt`|[Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|от 0 до 4,294,967,295 \(без знака\); дробная часть округляется.<sup>1</sup>|  
|`CULng`|[Тип данных ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|от 0 до 18446744073709551615 \(без знака\); дробная часть округляется.<sup>1</sup>|  
|`CUShort`|[Тип данных UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|от 0 до 65535 \(без знака\); дробная часть округляется.<sup>1</sup>|  
  
 <sup>1</sup> Дробные части могут быть подчиняться специальному типу округления под названием *банковское округление*.  См. примечания для дополнительных сведений.  
  
## Заметки  
 Как правило предпочтительнее использовать функции преобразования типа Visual Basic, чем методы .NET Framework, например `ToString()` в классе <xref:System.Convert> или в отдельном типе структуры или класса.  Функции языка Visual Basic предназначены для оптимального взаимодействия с Visual Basic, и они также сделают исходный код короче и облегчат его чтение.  Кроме того методы преобразования .NET Framework не всегда получают тот же результат, что функции Visual Basic, например при преобразовании `Boolean` к `Integer`.  Дополнительные сведения см. в разделе [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## Поведение  
  
-   **Приведение типа данных.** В общем случае, функции преобразования типов данных можно использовать для приведения результата некоторой операции к определенному типу данных вместо типа данных, получаемого по умолчанию.  Например, функция `CDec` используется для принудительного приведения результатов операций к десятичному типу в тех случаях, когда получаемые значения относятся к типу данных с одинарной точностью, двойной точностью или к целочисленному типу.  
  
-   **Сбой преобразования.** Если параметр `expression`, передаваемый в функцию, находится вне диапазона значений типа данных, в который преобразуется expression, возникает ошибка <xref:System.OverflowException>.  
  
-   **Дробная часть.** При преобразовании нецелого значения к целочисленному типу функции преобразования целых чисел \(`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng` и `CUShort`\) удаляют дробную часть и округляют значение до ближайшего целого числа.  
  
     Если дробная часть равна точно 0,5, то функции преобразования целых чисел округлят его до ближайшего четного целого числа.  Например, 0,5 округляется до 0, а 1,5 и 2,5 округляются до 2.  Это иногда называется *банковским округлением*, и его целью является компенсация сдвигов, которые могут накапливаться при сложении многих таких чисел.  
  
     `CInt` и `CLng` отличаются от функций <xref:Microsoft.VisualBasic.Conversion.Int%2A> и <xref:Microsoft.VisualBasic.Conversion.Fix%2A>, которые вместо округления отсекают дробную часть числа.  Кроме того `Fix` и `Int` всегда возвращают значение того же типа данных, что и переданное значение.  
  
-   **Преобразования даты\/времени.** Функция <xref:Microsoft.VisualBasic.Information.IsDate%2A> используется для определения возможности преобразования значения в дату и время.  `CDate` распознает литералы даты и литералы времени, но не числовые значения.  Чтобы преобразовать значение `Date` Visual Basic 6.0 к  `Date` Visual Basic 2005 или более поздних версий, можно использовать метод <xref:System.DateTime.FromOADate%2A?displayProperty=fullName>.  
  
-   **Нейтральные значения даты\/времени.** [Тип данных Date](../../../visual-basic/language-reference/data-types/date-data-type.md) всегда содержит и дату, и время.  При преобразовании типов в Visual Basic *нейтральным значением* даты считается 1\/1\/1 \(1 января 1 года\), а нейтральным значением времени — 00:00:00 \(полночь\).  Если значение с типом `Date` преобразуется в строку, функция `CStr` не включает нейтральные значения в конечную строку.  Например, при преобразовании значения `#January 1, 0001 9:30:00#` в строку, будет возвращен результат "9:30:00"; дата отбрасывается.  При этом сведения о дате останутся в исходном значении `Date` и могут быть извлечены с помощью таких функций, как <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.  
  
-   **Учет языковых и региональных параметров.** Функции преобразования типов, включающие строки, выполняют преобразования на основе текущих языковых и региональных параметров для приложения.  Функция `CDate` распознает форматы даты согласно региональным параметрам системы.  Необходимо предоставить день, месяц и год в правильном порядке для имеющихся региональных настроек, в противном случае дата может интерпретироваться неправильно.  Полный формат даты не распознается, если он содержит строковое значение дня недели, например "Wednesday".  
  
     Если требуется преобразовать в или из строкового представление значения в формате, отличном от задаваемого языка, то невозможно использовать функции преобразования типа Visual Basic.  Чтобы сделать это, используйте методы `ToString(IFormatProvider)` и `Parse(String, IFormatProvider)` для этих типов значений.  Например, используйте <xref:System.Double.Parse%2A?displayProperty=fullName> при преобразовании строки к `Double` и используйте <xref:System.Double.ToString%2A?displayProperty=fullName> при преобразовании значения из типа `Double` в строку.  
  
## Функция CType  
 [Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md) принимает второй аргумент `typename` и приводит `expression` к `typename`, где `typename` может быть любым типом данных, структурой, классом или интерфейсом, для которого существует допустимое преобразование.  
  
 Для сравнения `CType` с другими зарезервированными словами преобразования типов см. [Оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) и [Оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md).  
  
## Пример использования функции CBool  
 В следующем примере для преобразования к `Boolean` используется функция `CBool`.  Если результатом вычисления выражения является ненулевое значение, то `CBool` возвращает `True`; в противном случае она возвращает `False`.  
  
 [!code-vb[VbVbalrFunctions#1](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/type-conversion-functions_1.vb)]  
  
## Пример использования функции CByte  
 В следующем примере для преобразования к `Byte` используется функция `CByte`.  
  
 [!code-vb[VbVbalrFunctions#2](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/type-conversion-functions_2.vb)]  
  
## Пример использования функции CChar  
 В следующем примере для преобразования первого символа выражения `String` к типу `Char` используется функция `CChar`.  
  
 [!code-vb[VbVbalrFunctions#3](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/type-conversion-functions_3.vb)]  
  
 Входным аргументом `CChar` должен быть тип данных `Char` или `String`.  Невозможно использовать функцию `CChar` для преобразования числа в символ, поскольку функция `CChar` не может принимать данные числовых типов.  В этом примере получается число, представляющее кодовую позицию \(код символа\), которое преобразуется в соответствующий символ.  Использует функцию <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> для получения строки цифр, `CInt` для преобразования строки к типу `Integer`, а `ChrW` для преобразования строки к типу `Char`.  
  
 [!code-vb[VbVbalrFunctions#4](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/type-conversion-functions_4.vb)]  
  
## Пример использования функции CDate  
 В следующем примере для преобразования строк к `Date` используется функция `CDate`.  Как правило, не рекомендуется жестко кодировать дату и время в виде строк \(как показано в этом примере\).  Вместо этого используйте литералы даты и времени, например \#Feb 12, 1969\# и \#4:45:23 PM\#.  
  
 [!code-vb[VbVbalrFunctions#5](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/type-conversion-functions_5.vb)]  
  
## Пример использования алгоритма CDbl  
 [!code-vb[VbVbalrFunctions#6](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/type-conversion-functions_6.vb)]  
  
## Пример использования функции CDec  
 В следующем примере для преобразования числа к `Decimal` используется функция `CDec`.  
  
 [!code-vb[VbVbalrFunctions#7](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/type-conversion-functions_7.vb)]  
  
## Пример использования функции CInt  
 В следующем примере для преобразования значения к `Integer` используется функция `CInt`.  
  
 [!code-vb[VbVbalrFunctions#8](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/type-conversion-functions_8.vb)]  
  
## Пример использования алгоритма CLng  
 В следующем примере для преобразования значения к `Long` используется функция `CLng`.  
  
 [!code-vb[VbVbalrFunctions#9](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/type-conversion-functions_9.vb)]  
  
## Пример использования функции CObj  
 В следующем примере для преобразования числа к `Object` используется функция `CObj`.  Переменная `Object` содержит только 4\-байтовый указатель, указывающий на значение типа `Double`.  
  
 [!code-vb[VbVbalrFunctions#10](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/type-conversion-functions_10.vb)]  
  
## Пример использования функции CSByte  
 В следующем примере для преобразования числа к `SByte` используется функция `CSByte`.  
  
 [!code-vb[VbVbalrFunctions#11](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/type-conversion-functions_11.vb)]  
  
## Пример использования функции CShort  
 В следующем примере для преобразования числа к `Short` используется функция `CShort`.  
  
 [!code-vb[VbVbalrFunctions#12](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/type-conversion-functions_12.vb)]  
  
## Пример использования алгоритма CSng  
 В следующем примере для преобразования значения к `Single` используется функция `CSng`.  
  
 [!code-vb[VbVbalrFunctions#13](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/type-conversion-functions_13.vb)]  
  
## Пример использования алгоритма CStr  
 В следующем примере для преобразования числа к `String` используется функция `CStr`.  
  
 [!code-vb[VbVbalrFunctions#14](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/type-conversion-functions_14.vb)]  
  
 В следующем примере для преобразования `Date` к `String` используется функция `CStr`.  
  
 [!code-vb[VbVbalrFunctions#15](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/type-conversion-functions_15.vb)]  
  
 Функция `CStr` всегда предоставляет значение с типом `Date` в стандартном кратком формате для текущих региональных параметров, например 6\/15\/2003 4:35:47 PM.  Однако `CStr` подавляет *нейтральные значения* 1\/1\/0001 для даты и 00:00:00 для времени.  
  
 Более подробно сведения о значениях, возвращаемых `CStr`, содержатся в разделе [Возвращаемые значения функции CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).  
  
## Пример использования функции CUInt  
 В следующем примере для преобразования числа к `UInteger` используется функция `CUInt`.  
  
 [!code-vb[VbVbalrFunctions#16](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/type-conversion-functions_16.vb)]  
  
## Пример использования функции CULng  
 В следующем примере для преобразования числа к `ULong` используется функция `CULng`.  
  
 [!code-vb[VbVbalrFunctions#17](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/type-conversion-functions_17.vb)]  
  
## Пример использования функции CShort  
 В следующем примере для преобразования числа к `UShort` используется функция `CUShort`.  
  
 [!code-vb[VbVbalrFunctions#18](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/type-conversion-functions_18.vb)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>   
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>   
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>   
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>   
 <xref:Microsoft.VisualBasic.Strings.Format%2A>   
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>   
 <xref:Microsoft.VisualBasic.Conversion.Oct%2A>   
 <xref:Microsoft.VisualBasic.Conversion.Str%2A>   
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>   
 [Функции преобразования](../../../visual-basic/language-reference/functions/conversion-functions.md)   
 [Преобразование типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)