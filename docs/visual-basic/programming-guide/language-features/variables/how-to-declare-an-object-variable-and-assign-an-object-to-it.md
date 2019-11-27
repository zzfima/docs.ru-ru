---
title: Инструкции. Объявление объектной переменной и назначение ей объекта
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: 4cfad1d820b584d4610d24c392b14ac3958471b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352908"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a>Практическое руководство. Объявление объектной переменной в Visual Basic и присвоение ей объекта

Переменная [типа данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) объявляется путем указания `As Object` в [операторе Dim](../../../../visual-basic/language-reference/statements/dim-statement.md). Вы назначаете объект такой переменной, помещая объект после знака равенства (`=`) в операторе присваивания или в предложении инициализации.

## <a name="example"></a>Пример

В следующем примере объявляется переменная `Object` и ей присваивается текущий экземпляр.

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

Объявление и присваивание можно объединить, инициализируя переменную как часть ее объявления. Следующий пример эквивалентен предыдущему примеру.

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- ссылка на пространство имен <xref:System>.

- Класс, структура или модуль, в котором будет размещена инструкция `Dim`.

- Процедура, в которой следует разместить оператор присваивания.

## <a name="see-also"></a>См. также

- [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Объявление объектной переменной](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
