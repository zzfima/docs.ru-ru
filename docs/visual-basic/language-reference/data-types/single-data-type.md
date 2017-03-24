---
title: "Тип данных Single (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Single"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "! знак типа идентификатора"
  - "0 знаков, в конце"
  - "типы данных [Visual Basic], назначение"
  - "знак типа литерала F"
  - "числа с плавающей запятой, Single - тип данных"
  - "символы типа идентификатора, !"
  - "символы типа литерала, F"
  - "числа, с плавающей запятой"
  - "числа, действительные"
  - "действительные числа"
  - "Single - тип данных"
  - "числа одинарной точности"
  - "знаки с 0 в конце"
  - "нули в конце"
  - "нули, в конце"
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Тип данных Single (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Содержит 32\-разрядное \(4\-байтное\) число формата IEEE одинарной точности с плавающей запятой и знаком, которое может изменяться в диапазоне от \-3,4028235E\+38 до \-1,401298E\-45 для отрицательных значений и от 1,401298E\-45 до 3,4028235E\+38 для положительных.  Числа одинарной точности сохраняют приближенные значения действительных чисел.  
  
## Заметки  
 Используйте тип данных `Single` для хранения значений с плавающей запятой, которые не требуют полного размера `Double`.  В некоторых случаях среда CLR может использовать возможность упаковки переменных `Single` для уменьшения потребления памяти.  
  
 Значение по умолчанию для типа `Single` равно 0.  
  
## Советы по программированию  
  
-   **Точность**. При работе с числами с плавающей запятой, имейте в виду, что они не всегда имеют точное представление в памяти.  Это может привести к непредвиденным результатам для определенных операций, таких как сравнение значений и `Mod`.  Дополнительные сведения см. в разделе [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
-   **Расширение**. Тип данных `Single` может быть расширен до `Double`.  Это означает, что можно выполнить преобразование из `Single` к `Double` без возникновения ошибки <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Нули в конце строки**. Типы данных с плавающей запятой не имеют какого\-либо внутреннего представления символов конечных нулей.  Например, они не различают значения 4,2000 и 4,2.  Следовательно, символы 0 в конце строки не появляются при отображении или печати значений с плавающей запятой.  
  
-   **Символы типов**. При добавлении знака `F` типа литерала к литералу происходит приведение литерала к типу данных `Single`.  При добавлении знака `!` типа идентификатора к какому\-либо идентификатору происходит приведение идентификатора к типу `Single`.  
  
-   **Тип Framework.**. В .NET Framework данный тип соответствует структуре <xref:System.Single?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Single?displayProperty=fullName>   
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Тип данных Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)   
 [Тип данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md)   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)