---
title: "Расширяющие и сужающие преобразования (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "изменение типов данных"
  - "преобразования, тип данных"
  - "преобразования, исключения при преобразовании"
  - "преобразования, сужение"
  - "преобразования, тип"
  - "преобразования, расширение"
  - "преобразование типов данных, исключения при преобразовании"
  - "преобразование типов данных, сужение"
  - "преобразование типов данных, расширение"
  - "типы данных [Visual Basic], изменение"
  - "сужающие преобразования"
  - "преобразование типов, исключения при преобразовании"
  - "преобразование типов, сужение"
  - "преобразование типов, расширение"
  - "переменные [Visual Basic], изменение типа данных"
  - "расширяющие преобразования"
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Расширяющие и сужающие преобразования (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Важной характеристикой при преобразовании типа является получение результата преобразования в пределах диапазона конечного типа данных.  
  
 A *расширяющее преобразование* изменяет значение на тип данных, который может допускать любое возможное значение исходных данных.  Расширяющие преобразования сохраняют исходное значение, но могут изменить его представление.  Это происходит при преобразовании из объединенного типа `Decimal`или  `Char` В  `String`.  
  
 *Сужающее преобразование* изменяет значение на тип данных, который не может содержать некоторые из возможных значений.  Например, частичное значение округляется, когда оно преобразуется к целочисленному типу, преобразованным в тип, и numeric `Boolean` уменьшает к этому  `True` OR  `False`.  
  
## Расширяющие преобразования  
 В приведенной ниже таблице показаны стандартные расширяющие преобразования.  
  
|||  
|-|-|  
|Тип данных|Расширяется до типов данных <sup>1</sup>|  
|[SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Short](../../../../visual-basic/language-reference/data-types/short-data-type.md)|`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double` <sup>2</sup>|  
|[Long](../../../../visual-basic/language-reference/data-types/long-data-type.md)|`Long`, `Decimal`, `Single`, `Double` <sup>2</sup>|  
|[ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|`ULong`, `Decimal`, `Single`, `Double` <sup>2</sup>|  
|[Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`, `Single`, `Double` <sup>2</sup>|  
|[Single](../../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`, `Double`|  
|[Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|Какой\-либо перечисляемый тип \([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)\)|Базовый тип и любые его целочисленный тип, в который расширяет базовый тип.|  
|[Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`Char`, `String`|  
|Массив `Char`|Массив `Char`, `String`|  
|Любой тип|[Объект.](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|Любой производный тип|Любой базовый тип, от которого он является производным <sup>3</sup>.|  
|Любой тип|Любой реализуемый интерфейс.|  
|[Nothing](../../../../visual-basic/language-reference/nothing.md)|Любой тип данных или тип объекта.|  
  
 <sup>1</sup> По определению каждый тип данных может быть расширен до самого себя.  
  
 <sup>2</sup> Преобразования из `Integer`, `UInteger`, `Long`, `ULong` или `Decimal` в `Single` или `Double` могут привести к потере точности, но никогда не приведут к потере величины.  В этом смысле такие преобразования не приводят к потере информации.  
  
 <sup>3</sup> Может показаться странным, что преобразование из производного типа в один из базовых типов является расширяющим.  Объясняется это тем, что производный тип содержит все члены базового типа, поэтому он определяется как экземпляр базового типа.  С другой стороны, базовый тип не содержит каких\-либо новых членов, определенных производным типом.  
  
 Расширяющие преобразования всегда успешны во время выполнения и никогда не приводят к потере данных.  Можно всегда выполнить их неявным образом, независимо от того, задан ли в [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) ключ проверки типа со значением `On` или `Off`.  
  
## Сужающие преобразования  
 Стандартные сужающие преобразования включают следующие:  
  
-   Обратные направления расширяющих преобразований в предшествующей таблице \(за исключением того, что каждый тип может быть расширен до самого себя\).  
  
-   Преобразования в любом направлении между типом [Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) и любым числовым типом.  
  
-   Преобразования любого числового типа в любой перечисляемый тип \(`Enum`\).  
  
-   Преобразования в любом направлении между типом [String](../../../../visual-basic/language-reference/data-types/string-data-type.md) и любым числовым типом, типом `Boolean` или [Date](../../../../visual-basic/language-reference/data-types/date-data-type.md).  
  
-   Преобразования типа данных или типа объекта в их производный тип.  
  
 Сужающие преобразования не всегда успешны во время выполнения и могут привести к ошибке или потере данных.  Ошибка появляется, если конечному типу данных не удается получить преобразованное значение.  Например, числовое преобразование может привести к переполнению.  Компилятор не позволяет выполнять сужающие преобразования неявным образом, если только в [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) не задается ключ проверки типа со значением `Off`.  
  
> [!NOTE]
>  Ошибка сужающего преобразования отбрасывается при преобразовании элементов коллекции `For Each…Next` в переменную цикла.  Дополнительные сведения и примеры см. в подразделе "Сужающие преобразования" [Оператор For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### Ситуации, в которых используются сужающие преобразования  
 Сужающее преобразование следует использовать, когда известно, что исходное значение может быть преобразовано в конечный тип данных без ошибки и потери данных.  Например, если имеется a `String` что известно, содержащий или "true" или "false", можно использовать  `CBool` ключевое слово, которое требуется преобразовать его в  `Boolean`.  
  
## Исключения при преобразовании  
 Поскольку расширяющие преобразования всегда выполняются успешно, они не вызывают исключений.  Неудачно выполненные сужающие преобразования часто создают следующие исключения:  
  
-   <xref:System.InvalidCastException> — если не определено преобразование между двумя типами.  
  
-   <xref:System.OverflowException> — \(только для целых типов\) если преобразованное значение слишком велико для конечного типа.  
  
 Если класс или структура определяет [Функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) в качестве оператора преобразования в структуру или класс либо из структуры или класса, где `CType` может вызвать какое\-либо исключение, то он рассматривается соответствующим образом.  Кроме того, `CType` может вызвать функции [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] или методы [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)], которые, в свою очередь, могут вызвать ряд исключений.  
  
## Изменения в процессе преобразования ссылочных типов  
 Преобразование *ссылочных типов* копирует только указатель на значение.  Само значение никогда не копируется и не изменяется.  Изменяется только тип данных переменной, содержащей указатель.  В следующем примере тип данных преобразуется из производного класса в его базовый класс, но объект, на который указывают обе переменные, не изменяется.  
  
```  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## См. также  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Преобразование значений между строковыми и другими типами](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [Практическое руководство. Преобразование объекта к другому типу в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)   
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)