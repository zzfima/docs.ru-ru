---
title: Инструкции. Объявление объектной переменной и назначение ей объекта
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: eaaeda2a986584e6e1a2e0d2cda3890fb6187598
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344235"
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

## <a name="compile-the-code"></a>Компиляция кода

Для этого примера требуются:

- ссылка на пространство имен <xref:System>.

- Класс, структура или модуль, в котором будет размещена инструкция `Dim`.

- Процедура, в которой следует разместить оператор присваивания.

## <a name="see-also"></a>См. также:

- [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Объявление объектной переменной](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
