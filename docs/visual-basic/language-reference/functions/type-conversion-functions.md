---
title: Функции преобразования типов (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CUShort
- vb.csng
- vb.CDate
- CByte
- CSng
- vb.CDec
- CBool
- CStr
- vb.CULng
- CDec
- CVErr
- CDbl
- CShort
- vb.CObj
- vb.CVErr
- CULng
- vb.cdbl
- vb.cbool
- CObj
- CDate
- CLng
- vb.cstr
- vb.cbyte
- vb.clng
- vb.CChar
- CUShort
- vb.CUInt
- vb.cint
- vb.CShort
- CInt
- CUInt
- CChar
helpviewer_keywords:
- CDate function
- CByte function
- Integer data type [Visual Basic], converting
- string conversion [Visual Basic], conversion functions
- fractions
- data types [Visual Basic], converting
- text, converting
- CDec function
- Char data type [Visual Basic], converting
- type conversion [Visual Basic], functions for
- Single data type [Visual Basic], converting
- numbers [Visual Basic], rounding
- rounding numbers [Visual Basic], type conversion
- CUShort function
- Long data type [Visual Basic], converting
- return values [Visual Basic], data types
- single-precision numbers [Visual Basic], converting
- data type conversion [Visual Basic], functions for
- CStr function
- times [Visual Basic], converting
- CSng function
- conversions [Visual Basic], type conversion functions
- CBool function
- CDbl function
- CUInt function
- Currency data type [Visual Basic], conversion functions
- numbers [Visual Basic], converting
- Double data type [Visual Basic], converting
- CLng function
- CSByte function
- double-precision numbers
- Decimal data type [Visual Basic], converting
- Boolean data type [Visual Basic], converting
- integers [Visual Basic], type conversion functions
- dates [Visual Basic], converting
- CULng function
- CInt function
- Date data type [Visual Basic], converting
- Byte data type [Visual Basic], converting
- String data type [Visual Basic], converting
- CChar function
- banker's rounding
- Short data type [Visual Basic], converting
- rounding numbers [Visual Basic], banker's rounding
- type conversion [Visual Basic], Visual Basic vs. .NET Framework
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
ms.openlocfilehash: c9222bdb31f4fd7c792d5a50c100067e29e9d537
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="type-conversion-functions-visual-basic"></a>Функции преобразования типов (Visual Basic)
Эти функции являются скомпилированных встроенный, это означает, что код преобразования является частью кода, вычисляет выражение. Иногда отсутствует вызов процедуры для выполнения преобразований, что улучшает производительность. Каждая функция преобразует выражение к определенному типу данных.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
## <a name="part"></a>Отделение  
 `expression`  
 Обязательно. Любое выражение исходного типа данных.  
  
## <a name="return-value-data-type"></a>Тип данных возвращаемого значения  
 Имя функции определяет тип данных значение, которое возвращается, как показано в следующей таблице.  
  
|Имя функции|Тип возвращаемых данных|Диапазон `expression` аргумент|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[Логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Любое допустимое `Char` или `String` или числовое выражение.|  
|`CByte`|[Тип данных Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)|от 0 до 255 (без знака); Дробная часть округляется. <sup>1</sup>|  
|`CChar`|[Тип данных Char](../../../visual-basic/language-reference/data-types/char-data-type.md)|Любое допустимое `Char` или `String` выражения; только первый символ `String` преобразуется; значение может быть от 0 до 65535 (без знака).|  
|`CDate`|[Тип данных Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|Любое допустимое представление даты и времени.|  
|`CDbl`|[Тип данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|-1, 79769313486231570E + 308 до - 4, 94065645841246544E-324 для отрицательных значений; 4.94065645841246544E-324 до 1, 79769313486231570E + 308 для положительных значений.|  
|`CDec`|[Тип данных Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|+/-79228162514264337593543950335 для целых чисел, то есть числа без десятичных разрядов. Для чисел с 28 десятичных разрядов диапазон — от +/-7,9228162514264337593543950335. Наименьшее возможное ненулевое число это 0.0000000000000000000000000001 (+/-1E-28).|  
|`CInt`|[Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)|от -2147483648 до 2 147 483 647; Дробная часть округляется. <sup>1</sup>|  
|`CLng`|[Тип данных Long](../../../visual-basic/language-reference/data-types/long-data-type.md)|-9223372036854775808 до 9223372036854775807; Дробная часть округляется. <sup>1</sup>|  
|`CObj`|[Тип данных Object](../../../visual-basic/language-reference/data-types/object-data-type.md)|Любое допустимое выражение.|  
|`CSByte`|[Тип данных SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|от -128 до 127; Дробная часть округляется. <sup>1</sup>|  
|`CShort`|[Тип данных Short](../../../visual-basic/language-reference/data-types/short-data-type.md)|-32 768 до 32 767; Дробная часть округляется. <sup>1</sup>|  
|`CSng`|[Тип данных Single](../../../visual-basic/language-reference/data-types/single-data-type.md)|-3, 402823E + 38 до - 1, 401298E-45 для отрицательных значений; 1, 401298E-45 до 3, 402823E + 38 для положительных значений.|  
|`CStr`|[Тип данных String](../../../visual-basic/language-reference/data-types/string-data-type.md)|Возвращает для `CStr` зависят от `expression` аргумент. В разделе [возвращаемые значения функции CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).|  
|`CUInt`|[Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|от 0 до 4 294 967 295 (без знака); Дробная часть округляется. <sup>1</sup>|  
|`CULng`|[Тип данных ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|от 0 до 18446744073709551615 (без знака); Дробная часть округляется. <sup>1</sup>|  
|`CUShort`|[Тип данных UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|от 0 до 65 535 (без знака); Дробная часть округляется. <sup>1</sup>|  
  
 <sup>1</sup> дробных частей может быть причиной специальный тип округления вызываемой *банковское округление*. Дополнительные сведения в разделе «Примечания».  
  
## <a name="remarks"></a>Примечания  
 Как правило, следует использовать функции преобразования типов Visual Basic предпочтительнее, чем методы платформы .NET Framework например `ToString()`, либо на <xref:System.Convert> класса или класса или структуры отдельного типа. Функции языка Visual Basic предназначены для оптимального взаимодействия с Visual Basic, и они позволят исходный код короче и удобнее для чтения. Кроме того, методы преобразования .NET Framework не всегда производят те же результаты, как функции Visual Basic, например, при преобразовании `Boolean` для `Integer`. Дополнительные сведения см. в разделе [Устранение неполадок типы данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="behavior"></a>Поведение  
  
-   **Приведение типа.** Как правило функции преобразования типов данных можно использовать для присвоения результат операции имеет определенный тип данных, а не тип данных по умолчанию. Например, использовать `CDec` для принудительного десятичному в случаях, где одиночной точности, двойной точности или целочисленные арифметические операции обычно происходящим.  
  
-   **Сбой преобразования.** Если `expression` передан функции находится вне диапазона типа данных, на который он преобразуется, <xref:System.OverflowException> происходит.  
  
-   **Дробная часть.** При преобразовании нецелочисленное значение целочисленного типа, функции преобразования целых чисел (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, и `CUShort`) Удаление Дробная часть и округляют значение до ближайшего целого числа.  
  
     Если дробная часть равна точно 0,5, функции преобразования целых чисел округления для ближайшего четного целого. Например 0,5 округляется до 0, а 1,5 и 2,5 округляются до 2. Это иногда называется *банковское округление*, и его целью является компенсация сдвигов, которые могут накапливаться при сложении многих таких чисел.  
  
     `CInt` и `CLng` отличаются от <xref:Microsoft.VisualBasic.Conversion.Int%2A> и <xref:Microsoft.VisualBasic.Conversion.Fix%2A> функций, которые усечение, а не округляют дробную часть числа. Кроме того `Fix` и `Int` всегда возвращают значение того же типа данных при передаче в.  
  
-   **Дата и время преобразования.** Используйте <xref:Microsoft.VisualBasic.Information.IsDate%2A> функцию, чтобы определить, если значение можно преобразовать в дату и время. `CDate` распознает литералы даты и времени, но не числовые значения. Для преобразования Visual Basic 6.0 `Date` значение `Date` в языке Visual Basic 2005 или более поздней версии, можно использовать <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> метода.  
  
-   **Нейтральные значения даты и времени.** [Тип данных Date](../../../visual-basic/language-reference/data-types/date-data-type.md) всегда содержит сведения о дате и времени. В целях преобразования типов Visual Basic рассматривает 1/1/0001 (1 января 1 года) быть *нейтральным значением* для даты и 00:00:00 (полночь) будет нейтральным значением времени. Если вы преобразуете `Date` значения в строку `CStr` включает нейтральные значения в результирующую строку. Например, если вы преобразуете `#January 1, 0001 9:30:00#` в строку, результат будет «9:30:00 AM»; дата отбрасывается. Тем не менее, сведения о дате по-прежнему присутствует в исходной коллекции `Date` значение и может быть восстановлен с помощью функции например <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> функции.  
  
-   **Восприимчивость языка и региональных параметров.** Функции преобразования типов, включающие строки преобразований на основе текущих параметров языка и региональных параметров для приложения. Например `CDate` распознает форматы даты согласно региональным параметрам системы. Необходимо указать день, месяц и год в правильном порядке для языка или дата может интерпретироваться неправильно. Длинный формат даты не распознается, если он содержит строки день недели, например «Среда».  
  
     Если требуется преобразовать в или из строкового представления значения в формате, отличном от того, задаваемого языка, нельзя использовать функции преобразования типов Visual Basic. Чтобы сделать это, используйте `ToString(IFormatProvider)` и `Parse(String, IFormatProvider)` методы типа этого значения. Например, использовать <xref:System.Double.Parse%2A?displayProperty=nameWithType> при преобразовании строки в `Double`и использовать <xref:System.Double.ToString%2A?displayProperty=nameWithType> при преобразовании значения типа `Double` в строку.  
  
## <a name="ctype-function"></a>CType Function  
 [Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md) получает в качестве второго аргумента `typename`и приводит `expression` для `typename`, где `typename` может быть любой тип данных, структуры, класса или интерфейса, для которого существует допустимое преобразование.  
  
 Сравнение `CType` с других ключевых слов преобразования типов, в разделе [оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) и [оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md).  
  
## <a name="cbool-example"></a>Пример использования функции CBool  
 В следующем примере используется `CBool` функцию для преобразования выражений для `Boolean` значения. Если результатом выражения является ненулевое значение `CBool` возвращает `True`; в противном случае возвращается значение `False`.  
  
 [!code-vb[VbVbalrFunctions#1](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_1.vb)]  
  
## <a name="cbyte-example"></a>Пример использования функции CByte  
 В следующем примере используется `CByte` функцию для преобразования выражения `Byte`.  
  
 [!code-vb[VbVbalrFunctions#2](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_2.vb)]  
  
## <a name="cchar-example"></a>Пример использования функции CChar  
 В следующем примере используется `CChar` функцию для преобразования первого символа `String` выражение `Char` типа.  
  
 [!code-vb[VbVbalrFunctions#3](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_3.vb)]  
  
 Входной аргумент для `CChar` должен иметь тип данных `Char` или `String`. Нельзя использовать `CChar` для преобразования числа в символ, поскольку `CChar` не может принимать числового типа данных. В следующем примере получается число, представляющее кодовую точку (код знака) и преобразует его в соответствующий символ. Она использует <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> функции для получения строки из цифр, `CInt` для преобразования строки в тип `Integer`, и `ChrW` для преобразования числа к типу `Char`.  
  
 [!code-vb[VbVbalrFunctions#4](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_4.vb)]  
  
## <a name="cdate-example"></a>Пример использования функции CDate  
 В следующем примере используется `CDate` функцию для преобразования строк для `Date` значения. В общем случае не рекомендуется жестко запрограммированные значения даты и время в виде строк (как показано в следующем примере). Используйте литералы даты и времени, например #Feb 12, 1969 # и # 4:45:23 PM #, вместо этого.  
  
 [!code-vb[VbVbalrFunctions#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_5.vb)]  
  
## <a name="cdbl-example"></a>Пример использования функции CDbl  
 [!code-vb[VbVbalrFunctions#6](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_6.vb)]  
  
## <a name="cdec-example"></a>Пример использования функции CDec  
 В следующем примере используется `CDec` функцию для преобразования числовых значений для `Decimal`.  
  
 [!code-vb[VbVbalrFunctions#7](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_7.vb)]  
  
## <a name="cint-example"></a>Пример использования функции CInt  
 В следующем примере используется `CInt` функции, чтобы преобразовать значение в `Integer`.  
  
 [!code-vb[VbVbalrFunctions#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_8.vb)]  
  
## <a name="clng-example"></a>Пример использования функции CLng  
 В следующем примере используется `CLng` функцию для преобразования значения `Long`.  
  
 [!code-vb[VbVbalrFunctions#9](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_9.vb)]  
  
## <a name="cobj-example"></a>Пример использования функции CObj  
 В следующем примере используется `CObj` функцию для преобразования числовых значений для `Object`. `Object` Переменная содержит только 4 байтовый указатель, указывающая на `Double` присвоенного значения.  
  
 [!code-vb[VbVbalrFunctions#10](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_10.vb)]  
  
## <a name="csbyte-example"></a>Пример использования функции CSByte  
 В следующем примере используется `CSByte` функцию для преобразования числовых значений для `SByte`.  
  
 [!code-vb[VbVbalrFunctions#11](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_11.vb)]  
  
## <a name="cshort-example"></a>Пример использования функции CShort  
 В следующем примере используется `CShort` функцию для преобразования числовых значений для `Short`.  
  
 [!code-vb[VbVbalrFunctions#12](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_12.vb)]  
  
## <a name="csng-example"></a>Пример использования функции CSng  
 В следующем примере используется `CSng` функцию для преобразования значения `Single`.  
  
 [!code-vb[VbVbalrFunctions#13](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_13.vb)]  
  
## <a name="cstr-example"></a>Пример использования функции CStr  
 В следующем примере используется `CStr` функцию для преобразования числовых значений для `String`.  
  
 [!code-vb[VbVbalrFunctions#14](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_14.vb)]  
  
 В следующем примере используется `CStr` функцию для преобразования `Date` значения `String` значения.  
  
 [!code-vb[VbVbalrFunctions#15](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_15.vb)]  
  
 `CStr` всегда выводит `Date` значение в стандартном кратком формате для текущего языкового стандарта, например, «6/15/2003 4:35:47 PM». Тем не менее `CStr` подавляет *нейтральные значения* из 1/1/0001 00:00:00, время и даты.  
  
 Дополнительные сведения по значениям, возвращаемым методом `CStr`, в разделе [возвращаемые значения функции CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).  
  
## <a name="cuint-example"></a>Пример использования функции CUInt  
 В следующем примере используется `CUInt` функцию для преобразования числовых значений для `UInteger`.  
  
 [!code-vb[VbVbalrFunctions#16](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_16.vb)]  
  
## <a name="culng-example"></a>Пример использования функции CULng  
 В следующем примере используется `CULng` функцию для преобразования числовых значений для `ULong`.  
  
 [!code-vb[VbVbalrFunctions#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_17.vb)]  
  
## <a name="cushort-example"></a>Пример CUShort  
 В следующем примере используется `CUShort` функцию для преобразования числовых значений для `UShort`.  
  
 [!code-vb[VbVbalrFunctions#18](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_18.vb)]  
  
## <a name="see-also"></a>См. также  
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
 [Преобразования типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
