---
title: Функции преобразования типов (Visual Basic)
ms.date: 10/24/2018
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
ms.openlocfilehash: 2b750f41343a4a68e29af6055815efd1e6470252
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816269"
---
# <a name="type-conversion-functions-visual-basic"></a>Функции преобразования типов (Visual Basic)
Эти функции являются компилируется путем подстановки, это означает, что код преобразования является частью кода, который вычисляет выражение. Иногда отсутствует вызов процедуры для выполнения преобразований, что улучшает производительность. Каждая функция преобразует выражение к определенному типу данных.  
  
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
 Обязательный. Любое выражение типа источника данных.  
  
## <a name="return-value-data-type"></a>Тип данных возвращаемого значения  
 Имя функции определяет тип данных значения, которое возвращается, как показано в следующей таблице.  
  
|Имя функции|Тип возвращаемых данных|Диапазон `expression` аргумент|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[Логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Любое допустимое `Char` или `String` или числовое выражение.|  
|`CByte`|[Тип данных Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte.MinValue?displayProperty=nameWithType> (0) через <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (без знака); дробная часть округляется.<sup> 1</sup><br/><br/>Начиная с 15.8 Visual Basic, Visual Basic оптимизирует производительность вычислений с плавающей запятой, для преобразования байтов с помощью `CByte` функции; см. в разделе ["Примечания"](#remarks) Дополнительные сведения. См. в разделе [пример CInt](#cint-example) приведен пример.|  
|`CChar`|[Тип данных Char](../../../visual-basic/language-reference/data-types/char-data-type.md)|Любое допустимое `Char` или `String` выражение; только первый символ `String` преобразуется; значение может быть от 0 до 65535 (без знака).|  
|`CDate`|[Тип данных Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|Любое допустимое представление даты и времени.|  
|`CDbl`|[Тип данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|-1, 79769313486231570E + 308 до - 4, 94065645841246544E-324 для отрицательных значений; 4.94065645841246544E-324 до 1, 79769313486231570E + 308 для положительных значений.|  
|`CDec`|[Тип данных Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|+/-79228162514264337593543950335 для целых чисел то есть числа без десятичных разрядов. Для чисел с 28 десятичных разрядов диапазон — от +/-7,9228162514264337593543950335. Наименьшее возможное число ненулевое значение — 0,0000000000000000000000000001 (+/-1E-28).|  
|`CInt`|[Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32.MinValue?displayProperty=nameWithType> (-2147483648) через <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2 147 483 647); дробная часть округляется.<sup> 1</sup> <br/><br/>Начиная с 15.8 Visual Basic, Visual Basic оптимизирует производительность вычислений с плавающей запятой в целое число, преобразование с `CInt` функции; см. в разделе ["Примечания"](#remarks) Дополнительные сведения. См. в разделе [пример CInt](#cint-example) приведен пример. |  
|`CLng`|[Тип данных Long](../../../visual-basic/language-reference/data-types/long-data-type.md)|<xref:System.Int64.MinValue?displayProperty=nameWithType> (-9223372036854775808) через <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9223372036854775807); дробная часть округляется.<sup> 1</sup><br/><br/>Начиная с 15.8 Visual Basic, Visual Basic оптимизирует производительность вычислений с плавающей запятой, для преобразования 64-разрядное целое число, с помощью `CLng` функции; см. в разделе ["Примечания"](#remarks) Дополнительные сведения. См. в разделе [пример CInt](#cint-example) приведен пример.|  
|`CObj`|[Тип данных Object](../../../visual-basic/language-reference/data-types/object-data-type.md)|Любое допустимое выражение.|  
|`CSByte`|[Тип данных SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte.MinValue?displayProperty=nameWithType> (от -128) через <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); дробная часть округляется.<sup> 1</sup><br/><br/>Начиная с 15.8 Visual Basic, Visual Basic оптимизирует производительность вычислений с плавающей запятой, для преобразования байт со знаком с `CSByte` функции; см. в разделе ["Примечания"](#remarks) Дополнительные сведения. См. в разделе [пример CInt](#cint-example) приведен пример.|  
|`CShort`|[Тип данных Short](../../../visual-basic/language-reference/data-types/short-data-type.md)|<xref:System.Int16.MinValue?displayProperty=nameWithType> (-32 768) до <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32 767); дробная часть округляется.<sup> 1</sup><br/><br/>Начиная с 15.8 Visual Basic, Visual Basic оптимизирует производительность вычислений с плавающей запятой, для преобразования 16-разрядное целое число, с помощью `CShort` функции; см. в разделе ["Примечания"](#remarks) Дополнительные сведения. См. в разделе [пример CInt](#cint-example) приведен пример.|  
|`CSng`|[Тип данных Single](../../../visual-basic/language-reference/data-types/single-data-type.md)|-3, 402823E + 38 до - 1, 401298E-45 для отрицательных значений; 1, 401298E-45 до 3, 402823E + 38 для положительных значений.|  
|`CStr`|[Тип данных String](../../../visual-basic/language-reference/data-types/string-data-type.md)|Возвращает для `CStr` зависят от `expression` аргумент. См. в разделе [возвращаемые значения функции CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).|  
|`CUInt`|[Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) через <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4 294 967 295) (без знака); дробная часть округляется.<sup> 1</sup><br/><br/>Начиная с 15.8 Visual Basic, Visual Basic оптимизирует производительность вычислений с плавающей запятой в целое число без знака преобразования с помощью `CUInt` функции; см. в разделе ["Примечания"](#remarks) Дополнительные сведения. См. в разделе [пример CInt](#cint-example) приведен пример.|  
|`CULng`|[Тип данных ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) через <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18446744073709551615) (без знака); дробная часть округляется.<sup> 1</sup><br/><br/>Начиная с 15.8 Visual Basic, Visual Basic оптимизирует производительность вычислений с плавающей запятой в длинное целое без знака преобразования с помощью `CULng` функции; см. в разделе ["Примечания"](#remarks) Дополнительные сведения. См. в разделе [пример CInt](#cint-example) приведен пример.|  
|`CUShort`|[Тип данных UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) через <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65 535) (без знака); дробная часть округляется.<sup> 1</sup><br/><br/>Начиная с 15.8 Visual Basic, Visual Basic оптимизирует производительность вычислений с плавающей запятой, для преобразования 16-разрядных целых беззнаковых с `CUShort` функции; см. в разделе ["Примечания"](#remarks) Дополнительные сведения. См. в разделе [пример CInt](#cint-example) приведен пример.|  
  
 <sup>1</sup> дробных частей может быть причиной специальный тип округления вызываемой *банковское округление*. Дополнительные сведения см. в подразделе «Примечания».  
  
## <a name="remarks"></a>Примечания  
 Как правило, следует использовать функции преобразования типов Visual Basic предпочтительнее, чем методы платформы .NET Framework например `ToString()`, либо на <xref:System.Convert> класса или для отдельного типа структуры или класса. Функции языка Visual Basic предназначены для оптимального взаимодействия с кодом Visual Basic, и они смогут исходный код короче и удобнее для чтения. Кроме того, методы преобразования платформы .NET Framework не всегда производят те же результаты, что функции языка Visual Basic, например, при преобразовании `Boolean` для `Integer`. Дополнительные сведения см. в разделе [Устранение неполадок типы данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  


Начиная с Visual Basic 15.8, производительность плавающей-запятой в целочисленные преобразования оптимизирован при передаче <xref:System.Single> или <xref:System.Double> значение, возвращаемое следующими методами для одной из функций преобразования целого числа (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

Эта оптимизация позволяет коду, который выполняет большое количество преобразования целых чисел будет выполняться в два раза быстрее. В следующем примере показано эти оптимизированного плавающей-запятой в целочисленные преобразования:

```vb
Dim s As Single = 173.7619
Dim d As Double = s 

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a>Поведение  
  
-   **Приведение типа.** Как правило функции преобразования типов данных можно использовать для присвоения результат операции для определенного типа данных, а не тип данных по умолчанию. Например, использовать `CDec` для принудительного десятичному в случаях, где одиночной точности, двойной точности или целочисленные арифметические операции обычно занимает место.  
  
-   **Сбой преобразования.** Если `expression` , передаваемое функции находится вне диапазона типа данных, на которое он будет преобразован, <xref:System.OverflowException> происходит.  
  
-   **Дробные части.** При преобразовании нецелочисленное значение в целочисленный тип, функции преобразования целых чисел (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, и `CUShort`) Удаление Дробная часть и округляет значение до ближайшего целого.  
  
     Если дробная часть равна точно 0,5, функции преобразования целых чисел округляет его для ближайшего четного целого. Например 0,5 округляется до 0, а 1,5 и 2,5 округляются до 2. Это иногда называется *банковское округление*, и предназначен для компенсации сдвигов, которые могут накапливаться при объединении таких чисел.  
  
     `CInt` и `CLng` отличаются от <xref:Microsoft.VisualBasic.Conversion.Int%2A> и <xref:Microsoft.VisualBasic.Conversion.Fix%2A> функций, которые усечение, а не округление, дробная часть числа. Кроме того `Fix` и `Int` всегда возвращает значение одного типа данных при передаче в.  
  
-   **Преобразования даты и времени.** Используйте <xref:Microsoft.VisualBasic.Information.IsDate%2A> функцию, чтобы определить, если значение можно преобразовать в дату и время. `CDate` распознает литералы даты и времени, но не числовые значения. Для преобразования в Visual Basic 6.0 `Date` значение `Date` значение в Visual Basic 2005 или более поздних версий, можно использовать <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> метод.  
  
-   **Нейтральный значений даты и времени.** [Тип данных Date](../../../visual-basic/language-reference/data-types/date-data-type.md) всегда содержит сведения о дате и времени. В целях преобразования типов Visual Basic рассматривает 1/1/0001 (1 января 1 года) быть *нейтральным значением* для даты и 00:00:00 (полночь) могла быть нейтральным значением времени. При преобразовании `Date` значение в строку `CStr` не включает нейтральные значения в результирующую строку. Например, при преобразовании `#January 1, 0001 9:30:00#` в строку, результат равен «9:30:00 AM»; дата отбрасывается. Тем не менее, сведения о дате по-прежнему присутствует в исходном `Date` значение и могут быть извлечены с помощью функции например <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> функции.  
  
-   **Учет языка и региональных параметров.** Функции преобразования типов, нежели строки выполняют преобразование, на основе текущих настроек языка и региональных параметров для приложения. Например `CDate` распознает форматы даты в соответствии с настройкой языкового стандарта системы. Необходимо указать день, месяц и год в правильном порядке для языка, или дата может интерпретироваться неправильно. Длинный формат даты не распознается, если он содержит строку day of week, такие как «Среда».  
  
     Если вам нужно преобразовать в или из строкового представления значения в формате, отличном от, указанного параметром языкового стандарта, нельзя использовать функции преобразования типов Visual Basic. Чтобы сделать это, используйте `ToString(IFormatProvider)` и `Parse(String, IFormatProvider)` методы типа это значение. Например, использовать <xref:System.Double.Parse%2A?displayProperty=nameWithType> при преобразовании строки в `Double`и использовать <xref:System.Double.ToString%2A?displayProperty=nameWithType> при преобразовании значения типа `Double` в строку.  
  
## <a name="ctype-function"></a>CType Function  
 [Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md) принимает второй аргумент — `typename`и приводит это `expression` для `typename`, где `typename` может быть любой тип данных, структуры, класса или интерфейса, для которого существует допустимое преобразование.  
  
 Сравнение `CType` с других ключевых слов преобразования типов, см. в разделе [оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) и [оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md).  
  
## <a name="cbool-example"></a>Пример использования функции CBool  
 В следующем примере используется `CBool` функцию для преобразования выражений для `Boolean` значения. Если выражение имеет ненулевое значение, `CBool` возвращает `True`; в противном случае он возвращает `False`.  
  
 [!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]  
  
## <a name="cbyte-example"></a>Пример использования функции CByte  
 В следующем примере используется `CByte` функцию для преобразования выражения `Byte`.  
  
 [!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]  
  
## <a name="cchar-example"></a>Пример использования функции CChar  
 В следующем примере используется `CChar` функцию для преобразования первый символ `String` выражение `Char` типа.  
  
 [!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]  
  
 Входной аргумент для `CChar` должен иметь тип данных `Char` или `String`. Нельзя использовать `CChar` для преобразования числа в символ, так как `CChar` не может принимать числового типа данных. В следующем примере получается число, представляющее кодовую точку (код символа) и преобразует его в соответствующий символ. Она использует <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> функции для получения строки из цифр, `CInt` для преобразования строки в тип `Integer`, и `ChrW` для преобразования числа к типу `Char`.  
  
 [!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]  
  
## <a name="cdate-example"></a>Пример CDate  
 В следующем примере используется `CDate` функции преобразования строк для `Date` значения. В общем случае не рекомендуется жестко запрограммированного значения даты и времени, как строки (как показано в этом примере). Используйте литералы даты и времени, например #Feb 12, 1969 # и # 4:45:23 PM #, вместо этого.  
  
 [!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]  
  
## <a name="cdbl-example"></a>Пример использования функции CDbl  
 [!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]  
  
## <a name="cdec-example"></a>Пример CDec  
 В следующем примере используется `CDec` функция для преобразования числовых значений для `Decimal`.  
  
 [!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]  
  
## <a name="cint-example"></a>Пример CInt  
 В следующем примере используется `CInt` функция для преобразования значения `Integer`.  
  
 [!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]  

## <a name="clng-example"></a>Пример использования функции CLng
 В следующем примере используется `CLng` функцию для преобразования значения `Long`.  
  
 [!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]  
  
## <a name="cobj-example"></a>Пример CObj  
 В следующем примере используется `CObj` функция для преобразования числовых значений для `Object`. `Object` Переменная содержит только указатель размером 4 байта, которое указывает `Double` присвоено значение.  
  
 [!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]  
  
## <a name="csbyte-example"></a>Пример использования функции CSByte  
 В следующем примере используется `CSByte` функция для преобразования числовых значений для `SByte`.  
  
 [!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]  
  
## <a name="cshort-example"></a>Пример использования функции CShort  
 В следующем примере используется `CShort` функция для преобразования числовых значений для `Short`.  
  
 [!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]  
  
## <a name="csng-example"></a>Пример использования функции CSng  
 В следующем примере используется `CSng` функцию для преобразования значения `Single`.  
  
 [!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]  
  
## <a name="cstr-example"></a>Пример использования функции CStr  
 В следующем примере используется `CStr` функция для преобразования числовых значений для `String`.  
  
 [!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]  
  
 В следующем примере используется `CStr` функцию для преобразования `Date` значения `String` значения.  
  
 [!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]  
  
 `CStr` всегда выводит `Date` значение в стандартном кратком формате для текущего языкового стандарта, например, «6/15/2003 4:35:47 PM». Тем не менее `CStr` подавляет *нейтральные значения* из 1/1/0001 для даты и 00:00:00 для времени.  
  
 Дополнительные сведения о значениях, возвращаемых `CStr`, см. в разделе [возвращаемые значения функции CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).  
  
## <a name="cuint-example"></a>Пример использования функции CUInt  
 В следующем примере используется `CUInt` функция для преобразования числовых значений для `UInteger`.  
  
 [!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]  
  
## <a name="culng-example"></a>Пример использования функции CULng  
 В следующем примере используется `CULng` функция для преобразования числовых значений для `ULong`.  
  
 [!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]  
  
## <a name="cushort-example"></a>Пример использования функции CShort  
 В следующем примере используется `CUShort` функция для преобразования числовых значений для `UShort`.  
  
 [!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- <xref:Microsoft.VisualBasic.Strings.Format%2A>
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:Microsoft.VisualBasic.Conversion.Oct%2A>
- <xref:Microsoft.VisualBasic.Conversion.Str%2A>
- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [Функции преобразования](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [Преобразование типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
