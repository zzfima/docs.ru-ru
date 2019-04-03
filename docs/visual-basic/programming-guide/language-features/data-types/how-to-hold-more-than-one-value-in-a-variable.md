---
title: Практическое руководство. Хранение нескольких значений в переменной (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
ms.openlocfilehash: f22888075184e0359daec1056af09132eaf772a5
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825161"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a>Практическое руководство. Хранение нескольких значений в переменной (Visual Basic)
Переменная содержит более одного значения, если при ее объявлении необходимо иметь *составной тип данных*.  
  
 [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) содержать структуры, массивы и классы. Переменная составные типы данных могут содержать как простые типы данных и других составных типов. Классы и структуры могут содержать код, а также данные.  
  
### <a name="to-hold-more-than-one-value-in-a-variable"></a>Для хранения более одного значения в переменной  
  
1.  Определите, какой тип составных данных, которые вы хотите использовать для переменной.  
  
2.  Если составной тип данных еще не определен, определите таким образом, чтобы его можно было использовать переменную.  
  
    -   Определить структуру с [оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md).  
  
    -   Определить массив с [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).  
  
    -   Определение класса с [оператор Class](../../../../visual-basic/language-reference/statements/class-statement.md).  
  
3.  Объявите переменную с `Dim` инструкции.  
  
4.  После имени переменной `As` предложение.  
  
5.  Выполните `As` ключевое слово с именем соответствующего составного типа.  
  
## <a name="see-also"></a>См. также

- [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)
- [Знаки типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
