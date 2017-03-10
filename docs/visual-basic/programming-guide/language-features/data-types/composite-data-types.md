---
title: "Составные типы данных (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "массивы [Visual Basic], составные типы данных"
  - "классы [Visual Basic], составные типы данных"
  - "классы [Visual Basic], составные типы"
  - "составные типы данных"
  - "составные типы"
  - "типы данных [Visual Basic], составной"
  - "структуры, составные типы данных"
  - "типы [Visual Basic], составной"
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Составные типы данных (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В дополнение к простейшим типам данных, имеющимся в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], можно создавать из элементов различных типов *составных типов данных*, например структуры, массивы и классы.  Можно создавать составные типы данных из простых типов или из других составных типов.  Например можно определить массив элементов структуры или структуру с членами массива.  
  
## Типы данных  
 Составной тип отличается от типов данных, входящих в его состав.  Например массив элементов `Integer` не принадлежит к типу данных `Integer`.  
  
 Тип данных массива обычно представляется с помощью типа элемента, скобок и запятых по мере необходимости.  Например, одномерный массив элементов `String` обозначается `String()`, а двумерный массив элементов `Boolean` обозначается `Boolean(,)`.  
  
## Типы структур  
 Не существует единственного типа данных, включающего в себя все структуры.  Вместо этого каждое определение структуры представляется уникальным типом данных, даже если две структуры определяют идентичные элементы в том же порядке.  Однако, если создается два или более экземпляров одной и той же структуры, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] рассматривает их как элементы одного типа данных.  
  
## Типы массивов  
 Не существует единого типа данных, включающего в себя все массивы.  Тип данных отдельного экземпляра массива определяется следующими параметрами:  
  
-   факт существования массива;  
  
-   ранг \(число измерений\) массива;  
  
-   тип элементов массива.  
  
 В частности, длина указанного измерения не является частью типа данных экземпляра.  Это показано в приведенном ниже примере.  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 В предыдущем примере массив переменных `arrayA` и `arrayB` считаются одним типом данных — `Byte()` — даже если они инициализируются для различной длины.  Переменные `arrayB` и `arrayC` разных типов, так как типы их элементов различны.  Переменные `arrayC` и `arrayD` разных типов, так как их ранги различны.  Переменные `arrayD` и `arrayE` имеют одинаковый тип — `Short(,)` потому, что их ранги и типы элементов одинаковы, даже если `arrayD` еще не инициализирован.  
  
 Дополнительные сведения о массивах см. в разделе [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## Типы классов  
 Не существует единого типа данных, включающего в себя все классы.  Хотя один класс может наследоваться от другого класса, каждый является отдельным типом данных.  Несколько экземпляров одного класса имеют один тип данных.  Если присвоить одну переменную экземпляра класса другой, они не только будут иметь одинаковый тип данных, но они также будут указывать на один и тот же экземпляр класса в памяти.  
  
 Дополнительные сведения о классах см. в разделе [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## См. также  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Универсальные типы в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Практическое руководство. Хранение нескольких значений в переменной](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)