---
title: Переменные структуры
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 16b6cdc5a849b50f6caa8b7963dac5c12d63cf3e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346294"
---
# <a name="structure-variables-visual-basic"></a>Переменные структуры (Visual Basic)

После создания структуры можно объявить переменные уровня процедуры и модуля в качестве этого типа. Например, можно создать структуру, которая записывает сведения о компьютерной системе. В следующем примере это показано.

```vb
Public Structure systemInfo
    Public cPU As String
    Public memory As Long
    Public purchaseDate As Date
End Structure
```

Теперь можно объявлять переменные этого типа. Это показано в следующем объявлении.

```vb
Dim mySystem, yourSystem As systemInfo
```

> [!NOTE]
> В классах и модулях структуры, объявленные с помощью [инструкции Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) , по умолчанию имеют открытый доступ. Если структура должна быть закрытой, убедитесь, что она объявлена с помощью ключевого слова [Private](../../../../visual-basic/language-reference/modifiers/private.md) .

## <a name="access-to-structure-values"></a>Доступ к значениям структуры

Для присвоения и извлечения значений из элементов переменной структуры используется тот же синтаксис, что и при использовании для задания и получения свойств объекта. Оператор доступа к членам (`.`) размещается между именем переменной структуры и именем элемента. В следующем примере осуществляется доступ к элементам переменных, ранее объявленных как тип `systemInfo`.

```vb
mySystem.cPU = "486"
Dim tooOld As Boolean
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True
```

## <a name="assigning-structure-variables"></a>Присваивание переменных структуры

Можно также присвоить одну переменную другой, если оба имеют один и тот же тип структуры. Все элементы одной структуры копируются в соответствующие элементы в другом. Это показано в следующем объявлении.

```vb
yourSystem = mySystem
```

Если элемент структуры является ссылочным типом, например `String`, `Object`или массивом, то копируется указатель на данные. В предыдущем примере, если `systemInfo` включала объектная переменная, то в предыдущем примере был скопирован указатель из `mySystem` в `yourSystem`, а изменение данных объекта через одну структуру вступит в действие при доступе через другую структуру.

## <a name="see-also"></a>См. также

- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Практическое руководство. Объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Структуры и другие элементы программирования](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [Структуры и классы](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
