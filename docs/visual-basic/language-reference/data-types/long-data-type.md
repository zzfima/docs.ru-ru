---
title: "Тип данных Long (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Long"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "& - знак типа идентификатора"
  - "типы данных [Visual Basic], назначение"
  - "типы данных [Visual Basic], интеграл"
  - "символы типа идентификатора, &"
  - "целые числа"
  - "целые числа, типы данных"
  - "целые числа, типы"
  - "целочисленные типы данных"
  - "знак типа литерала L"
  - "символы типа литерала, L"
  - "Long - тип данных"
  - "Long - ключевое слово"
  - "числа, целочисленный"
  - "числа, целый"
  - "целое число"
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Тип данных Long (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Содержит 64\-разрядные \(8\-байтные\) знаковые целые числа в диапазоне от \-9,223,372,036,854,775,808 до 9,223,372,036,854,775,807 \(9.2...E\+18\).  
  
## Заметки  
 Используйте тип данных `Long` для хранения целых чисел, слишком больших для типа данных `Integer`.  
  
 Значение по умолчанию для типа `Long` равно 0.  
  
## Советы по программированию  
  
-   **Вопросы взаимодействия**. Если выполняется взаимодействие с компонентами, которые написаны для платформы .NET Framework, такие как автоматизация или COM\-объекты, необходимо помнить, что ширина данных `Long` отличается в других средах \(16 бит\).  При передаче 32\-разрядного аргумента такому компоненту, следует объявить его как `Integer`, а не `Long` в новом коде Visual Basic.  
  
     Кроме того, модель автоматизации не поддерживает 64\-разрядные целые числа в Windows 95, в Windows 98, в Windows ME и в Windows 2000.  Компоненту автоматизации в этих операционных системах нельзя передавать аргумент Visual Basic `Long`.  
  
-   **Расширение**. Тип данных `Long` расширяется до `Decimal`, `Single`, или `Double`.  Это означает, что можно преобразовать `Long` в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Символы типов**. При добавлении знака `L` типа литерала к литералу происходит приведение литерала к типу данных `Long`.  При добавлении знака `&` типа идентификатора к какому\-либо идентификатору происходит приведение идентификатора к типу `Long`.  
  
-   **Тип Framework.**. В .NET Framework данный тип соответствует структуре <xref:System.Int64?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Int64>   
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [Тип данных Short](../../../visual-basic/language-reference/data-types/short-data-type.md)   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)