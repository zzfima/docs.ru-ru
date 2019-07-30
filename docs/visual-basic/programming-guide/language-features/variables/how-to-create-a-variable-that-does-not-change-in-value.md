---
title: Практическое руководство. Создание переменной, которая не изменяется в значении (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: d201e95463dd0431825fee03ebfd340ac80cc552
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630882"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a>Практическое руководство. Создание переменной, которая не изменяется в значении (Visual Basic)

Понятие переменной, которая не изменяет ее значение, может показаться противоречивым. Но бывают ситуации, когда константа нецелесообразна и полезно иметь переменную с фиксированным значением. В этом случае можно определить переменную-член с помощью ключевого слова [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) .

Нельзя использовать [оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md) для объявления и присваивания константного значения в следующих случаях.

- `Const` Инструкция не принимает тип данных, который вы хотите использовать.

- Неизвестно значение во время компиляции

- Не удается вычислить постоянное значение во время компиляции

### <a name="to-create-a-variable-that-does-not-change-in-value"></a>Создание переменной, которая не изменяется в значении

1. На уровне модуля объявите переменную-член с помощью [оператора Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)и включите ключевое слово [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) .

    ```vb
    Dim ReadOnly timeStarted
    ```

    Можно указать `ReadOnly` только для переменной-члена. Это означает, что необходимо определить переменную на уровне модуля вне любой процедуры.

2. Если значение можно вычислить в одной инструкции во время компиляции, используйте предложение инициализации в `Dim` инструкции. Используйте предложение [as](../../../../visual-basic/language-reference/statements/as-clause.md) со знаком равенства (`=`), за которым следует выражение. Убедитесь, что компилятор может вычислить это выражение до постоянного значения.

    ```vb
    Dim ReadOnly timeStarted As Date = Now
    ```

    Значение `ReadOnly` переменной можно присвоить только один раз. После этого код не сможет изменить его значение.

    Если значение неизвестно во время компиляции или не может быть вычислено во время компиляции в одной инструкции, вы все равно можете назначить его во время выполнения в конструкторе. Для этого необходимо объявить `ReadOnly` переменную на уровне класса или структуры. В конструкторе для этого класса или структуры следует вычислить фиксированное значение переменной и присвоить его переменной перед возвратом из конструктора.

## <a name="see-also"></a>См. также

- [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md)
