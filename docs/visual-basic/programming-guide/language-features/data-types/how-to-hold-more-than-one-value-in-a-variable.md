---
title: Практическое руководство. Хранение нескольких значений в переменной
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
ms.openlocfilehash: d452fbf35f9d200348234b38c40f8636f0ec4b4e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350020"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a>Практическое руководство. Хранение нескольких значений в переменной (Visual Basic)

Переменная содержит более одного значения, если объявить ее для *составного типа данных*.

[Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) включают структуры, массивы и классы. Переменная составного типа данных может содержать сочетание простейших типов данных и других составных типов. Структуры и классы могут содержать код и данные.

## <a name="to-hold-more-than-one-value-in-a-variable"></a>Хранение более одного значения в переменной

1. Определите составной тип данных, который будет использоваться для переменной.

2. Если составной тип данных еще не определен, определите его, чтобы переменная могла его использовать.

    - Определите структуру с помощью [оператора Structure](../../../../visual-basic/language-reference/statements/structure-statement.md).

    - Определите массив с помощью [оператора Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).

    - Определите класс с помощью [оператора класса](../../../../visual-basic/language-reference/statements/class-statement.md).

3. Объявите переменную с помощью оператора `Dim`.

4. Подпишите имя переменной с помощью предложения `As`.

5. Используйте ключевое слово `As` с именем соответствующего составного типа данных.

## <a name="see-also"></a>См. также

- [Типы данных](../../../../visual-basic/language-reference/data-types/index.md)
- [Знаки типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
