---
title: "Составные типы данных (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types
- composite data types
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures, composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d81b2c08155cb16754e780fdfb341b596322302d
ms.lasthandoff: 03/13/2017

---
# <a name="composite-data-types-visual-basic"></a>Составные типы данных (Visual Basic)
Помимо простых типов данных [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] блоки, можно создавать из элементов различных типов для создания *составные типы данных* как структуры, массивы и классы. Можно создавать составные типы данных из простых типов или из других составных типов. Например можно определить массив элементов структуры или структуру с членами массива.  
  
## <a name="data-types"></a>Типы данных  
 Составной тип отличается от типа данных любого из его компонентов. Например, массив `Integer` элементы не `Integer` тип данных.  
  
 Тип данных массива обычно представляется с помощью типа элемента, скобок и запятых при необходимости. Например, одномерный массив `String` элементов представляется в виде `String()`, а двумерный массив `Boolean` элементов представляется в виде `Boolean(,)`.  
  
## <a name="structure-types"></a>Типы структур  
 Отсутствует тип данных single включающего в себя все структуры. Вместо этого каждое определение структуры представляет собой уникальный тип данных, даже если две структуры определяют идентичные элементы в том же порядке. Однако, если создать два или более экземпляров одной и той же структуры, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] рассматривает их как элементы одного типа данных.  
  
## <a name="array-types"></a>Типы массивов  
 Отсутствует тип данных single включающего в себя все массивы. Тип данных отдельного экземпляра массива определяется следующим образом:  
  
-   Факт существования массива  
  
-   Ранг (размерность) массива  
  
-   Тип элемента массива  
  
 В частности длина данного измерения не является частью типа данных экземпляра. Это показано в следующем примере.  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 В предыдущем примере массив переменных `arrayA` и `arrayB` считаются тот же тип данных — `Byte()` — даже если они инициализируются для различной длины. Переменные `arrayB` и `arrayC` не являются того же типа, так как типы их элементов различны. Переменные `arrayC` и `arrayD` не являются того же типа, так как их ранги различны. Переменные `arrayD` и `arrayE` имеют одинаковый тип — `Short(,)` , так как их ранги и типы элементов одинаковы, даже если `arrayD` еще не инициализирован.  
  
 Дополнительные сведения о массивах см. в разделе [массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="class-types"></a>Типы классов  
 Нет нет типа данных, включающего в себя все классы. Несмотря на то, что один класс может наследовать от другого класса, каждый является отдельным типом данных. Несколько экземпляров одного класса имеют одинаковый тип данных. Если назначить одну переменную экземпляра класса в другой, не только они имеют тот же тип данных, они указывают на один экземпляр класса в памяти.  
  
 Дополнительные сведения о классах см. в разделе [объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="see-also"></a>См. также  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Универсальные типы в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Устранение неполадок типы данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Практическое руководство. Хранение нескольких значений в переменной](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
