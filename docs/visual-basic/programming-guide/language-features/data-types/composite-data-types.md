---
title: Составные типы данных (Visual Basic)
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
ms.openlocfilehash: 65ee23c59958eefb94c7ab0c6bef4a7e992a121c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64601183"
---
# <a name="composite-data-types-visual-basic"></a>Составные типы данных (Visual Basic)
В дополнение к простейших данных типов Visual Basic, можно создавать элементы различных типов для создания *составные типы данных* например структуры, массивы и классы. Можно создавать составные типы данных из простых типов или из других составных типов. Например можно определить массив элементов структуры или структуру с членами массива.  
  
## <a name="data-types"></a>Типы данных  
 Составной тип отличается от типа данных любого из его компонентов. Например, массив `Integer` элементов не относится к `Integer` тип данных.  
  
 Тип данных массива обычно представляется с помощью типа элемента, круглые скобки и запятые при необходимости. Например, одномерный массив `String` элементов представляется в виде `String()`и двухмерный массив `Boolean` элементов представляется в виде `Boolean(,)`.  
  
## <a name="structure-types"></a>Типы структуры  
 Нет единого типа данных, включающего в себя все структуры. Вместо этого каждое определение структуры представляет уникальный тип данных, даже если две структуры определяют идентичные элементы в том же порядке. Тем не менее при создании двух или более экземпляров той же структуры, Visual Basic рассматривает их как одного типа данных.  
  
## <a name="tuples"></a>Кортежи

Кортеж — это упрощенный структуру, содержащую два или несколько полей, типы которых являются предопределенными. Кортежи поддерживаются начиная с Visual Basic 2017. Кортежи наиболее часто используются для возврата нескольких значений из одного вызова метода без необходимости передавать аргументы по ссылке или упаковки возвращаемых полей в более всего спектра класса или структуры. См. в разделе [кортежей](tuples.md) приведены дополнительные сведения об кортежей.

## <a name="array-types"></a>Типы массивов  
 Нет единого типа данных, включающего в себя все массивы. Тип данных определенного экземпляра массива определяется следующее:  
  
- Факт существования массива  
  
- Ранг (число измерений) массива  
  
- Тип элемента массива  
  
 В частности длина данного измерения, не является частью типа данных экземпляра. Это показано в следующем примере.  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 В приведенном выше примере массив переменных `arrayA` и `arrayB` считаются одного типа данных — `Byte()` , несмотря на то, что они инициализируются для различной длины. Переменные `arrayB` и `arrayC` не являются того же типа, так как типы их элементов различаются. Переменные `arrayC` и `arrayD` не являются того же типа, так как их ранги различны. Переменные `arrayD` и `arrayE` имеют одинаковый тип — `Short(,)` , так как их ранги и типы элементов одинаковы, даже если `arrayD` еще не инициализирован.  
  
 Дополнительные сведения о массивах см. в разделе [массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="class-types"></a>Типы классов  
 Нет единого типа данных, включающего в себя все классы. Несмотря на то, что один класс может наследовать от другого класса, каждый является отдельным типом данных. Несколько экземпляров одного класса имеют одинаковый тип данных. Если назначить одну переменную экземпляра класса в другой, не только у них есть тот же тип данных, они указывают на один экземпляр класса в памяти.  
  
 Дополнительные сведения о классах см. в разделе [объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="see-also"></a>См. также

- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Практическое руководство. Хранение нескольких значений в переменной](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
