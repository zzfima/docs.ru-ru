---
title: Практическое руководство. Создание переменной, которая не изменяет значение
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: d5d8a6b066ae7e8795afd2f788b60823d8efdafa
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348635"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a>Практическое руководство. Создание переменной, которая не изменяет значение (Visual Basic)

Понятие переменной, которая не изменяет ее значение, может показаться противоречивым. Но бывают ситуации, когда константа нецелесообразна и полезно иметь переменную с фиксированным значением. В этом случае можно определить переменную-член с помощью ключевого слова [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) .

Нельзя использовать [оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md) для объявления и присваивания константного значения в следующих случаях.

- Оператор `Const` не принимает тип данных, который вы хотите использовать.

- Неизвестно значение во время компиляции

- Не удается вычислить постоянное значение во время компиляции

### <a name="to-create-a-variable-that-does-not-change-in-value"></a>Создание переменной, которая не изменяется в значении

1. На уровне модуля объявите переменную-член с помощью [оператора Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)и включите ключевое слово [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) .

    ```vb
    Dim ReadOnly timeStarted
    ```

    Можно указать `ReadOnly` только для переменной-члена. Это означает, что необходимо определить переменную на уровне модуля вне любой процедуры.

2. Если значение можно вычислить в одной инструкции во время компиляции, используйте предложение инициализации в операторе `Dim`. Используйте предложение [as](../../../../visual-basic/language-reference/statements/as-clause.md) со знаком равенства (`=`), за которым следует выражение. Убедитесь, что компилятор может вычислить это выражение до постоянного значения.

    ```vb
    Dim ReadOnly timeStarted As Date = Now
    ```

    Можно присвоить значение переменной `ReadOnly` только один раз. После этого код не сможет изменить его значение.

    Если значение неизвестно во время компиляции или не может быть вычислено во время компиляции в одной инструкции, вы все равно можете назначить его во время выполнения в конструкторе. Для этого необходимо объявить переменную `ReadOnly` на уровне класса или структуры. В конструкторе для этого класса или структуры следует вычислить фиксированное значение переменной и присвоить его переменной перед возвратом из конструктора.

## <a name="see-also"></a>См. также

- [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md)
