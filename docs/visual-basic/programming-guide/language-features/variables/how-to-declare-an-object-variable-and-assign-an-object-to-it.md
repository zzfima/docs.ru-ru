---
title: Практическое руководство. Объявите объектную переменную и присвойте ей объект в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: 71949d50b01d7f252a988e86ca259261086d3b3b
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630870"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a>Практическое руководство. Объявите объектную переменную и присвойте ей объект в Visual Basic

Переменная [типа данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) объявляется путем указания `As Object` в [операторе Dim](../../../../visual-basic/language-reference/statements/dim-statement.md). Вы назначаете объект такой переменной, помещая объект после знака равенства (`=`) в операторе присваивания или предложении инициализации.

## <a name="example"></a>Пример

В следующем примере объявляется `Object` переменная и назначается ей текущий экземпляр.

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

- Класс, структура или модуль, в котором будет размещена `Dim` инструкция.

- Процедура, в которой следует разместить оператор присваивания.

## <a name="see-also"></a>См. также

- [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Объявление объектной переменной](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
