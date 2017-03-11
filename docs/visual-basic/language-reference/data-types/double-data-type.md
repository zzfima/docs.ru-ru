---
title: "Тип данных Double (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Double"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "# - знак типа идентификатора"
  - "0 знаков, в конце"
  - "типы данных [Visual Basic], назначение"
  - "Double - тип данных"
  - "тип данных Double [Visual Basic]"
  - "числа двойной точности"
  - "числа с плавающей запятой, Double - тип данных"
  - "символы типа идентификатора, #"
  - "символы типа литерала, R"
  - "знак типа литерала R"
  - "действительные числа"
  - "знаки с 0 в конце"
  - "нули в конце"
  - "нули, в конце"
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# Тип данных Double (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Переменные типа Double хранятся как 64\-разрядные \(8\-байтные\) IEEE\-числа двойной точности с плавающей запятой и знаком, которые изменяются в диапазоне от \-1,79769313486231570E\+308 до \-4,94065645841246544E\-324 для отрицательных значений и от 4,94065645841246544E\-324 до 1,79769313486231570E\+308 для положительных.  Числа двойной точности сохраняют приближенные значения действительных чисел.  
  
## Заметки  
 Тип данных `Double` предоставляет наибольшую и наименьшую возможные величины для числа.  
  
 Значение по умолчанию для типа `Double` равно 0.  
  
## Советы по программированию  
  
-   **Точность**. Используя числа с плавающей запятой, следует учитывать, что они не всегда имеют точное представление в памяти.  Это может привести к непредвиденным результатам для определенных операций, таких как сравнение значений и `Mod`.  Дополнительные сведения см. в разделе [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
-   **Нули в конце строки**. Типы данных с плавающей запятой не имеют какого\-либо внутреннего представления нулевых байтов в конце строки.  Например, они не различают значения 4,2000 и 4,2.  Следовательно, нулевые символы в конце строки не появляются при отображении или печати значений с плавающей запятой.  
  
-   **Символы типов**. При добавлении знака `R` типа литерала к литералу происходит приведение литерала к типу данных `Double`.  Например, если после целочисленного значения находится знак `R`, то происходит приведение значения к типу `Double`.  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     При добавлении знака `#` типа идентификатора к какому\-либо идентификатору происходит приведение идентификатора к типу `Double`.  В следующем примере переменная `num` типизирована как `Double`:  
  
    ```  
    Dim num# = 3  
    ```  
  
-   **Тип Framework.**. В .NET Framework данный тип соответствует структуре <xref:System.Double?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Double?displayProperty=fullName>   
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Тип данных Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)   
 [Тип данных Single](../../../visual-basic/language-reference/data-types/single-data-type.md)   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Символы типов](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)