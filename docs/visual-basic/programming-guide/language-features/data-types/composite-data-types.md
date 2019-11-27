---
title: Составные типы данных
ms.date: 04/25/2017
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
ms.openlocfilehash: 1c099c5082f1c4173a50c70998c99135c94821e6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346378"
---
# <a name="composite-data-types-visual-basic"></a>Составные типы данных (Visual Basic)
Помимо простейших типов данных Visual Basic предоставляет также возможность собирать элементы различных типов для создания *составных типов данных* , таких как структуры, массивы и классы. Составные типы данных можно создавать из простейших типов и из других составных типов. Например, можно определить массив элементов структуры или структуру с элементами массива.  
  
## <a name="data-types"></a>Типы данных  
 Составной тип отличается от типа данных любого из его компонентов. Например, массив `Integer` элементов не относится к типу данных `Integer`.  
  
 Тип данных массива обычно представляется при необходимости с использованием типа элемента, круглых скобок и запятых. Например, одномерный массив `String` элементов представлен как `String()`, а двумерный массив элементов `Boolean` представляется как `Boolean(,)`.  
  
## <a name="structure-types"></a>Типы структур  
 Не существует одного типа данных, включающего в себя все структуры. Вместо этого каждое определение структуры представляет собой уникальный тип данных, даже если две структуры определяют идентичные элементы в том же порядке. Однако при создании двух или более экземпляров одной и той же структуры Visual Basic рассматривает их как один и тот же тип данных.  
  
## <a name="tuples"></a>Кортежи

Кортеж — это упрощенная структура, которая содержит два или более полей, типы которых являются предопределенными. Кортежи поддерживаются начиная с Visual Basic 2017. Кортежи чаще всего используются для возвращения нескольких значений из одного вызова метода без необходимости передачи аргументов по ссылке или упаковки возвращаемых полей в более тяжелом классе или структуре. Дополнительные сведения о кортежах см. в разделе [кортежи](tuples.md) .

## <a name="array-types"></a>Типы массивов  
 Не существует одного типа данных, включающего в себя все массивы. Тип данных конкретного экземпляра массива определяется следующим образом:  
  
- Факт является массивом  
  
- Ранг (число измерений) массива  
  
- Тип элемента массива  
  
 В частности, длина данного измерения не является частью типа данных экземпляра. Это показано в следующем примере.  
  
```vb  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 В предыдущем примере переменные массива `arrayA` и `arrayB` считаются одним и тем же типом данных — `Byte()`, несмотря на то, что они инициализируются с разной длиной. Переменные `arrayB` и `arrayC` относятся к разным типам, так как их типы элементов различаются. Переменные `arrayC` и `arrayD` имеют разные типы, так как их ранги различаются. Переменные `arrayD` и `arrayE` имеют одинаковый тип — `Short(,)` — так как их ранги и типы элементов одинаковы, даже если `arrayD` еще не инициализирован.  
  
 Дополнительные сведения о массивах см. в разделе [массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="class-types"></a>Типы классов  
 Не существует одного типа данных, включающего в себя все классы. Хотя один класс может наследовать от другого класса, каждый из них является отдельным типом данных. Несколько экземпляров одного и того же класса имеют один и тот же тип данных. Если присвоить одну переменную экземпляра класса другой, не только те, которые имеют один и тот же тип данных, они указывают на один и тот же экземпляр класса в памяти.  
  
 Дополнительные сведения о классах см. в разделе [объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="see-also"></a>См. также

- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Практическое руководство. Хранение нескольких значений в переменной](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
