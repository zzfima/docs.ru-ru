---
title: Переменные структуры (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: a86a60def9ac1b8140194ecb6f5e784c62a0e101
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630966"
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

Для присвоения и извлечения значений из элементов переменной структуры используется тот же синтаксис, что и при использовании для задания и получения свойств объекта. Оператор доступа к членам (`.`) размещается между именем переменной структуры и именем элемента. В следующем примере осуществляется доступ к элементам переменных, ранее объявленных как `systemInfo`тип.

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

Если элемент структуры является ссылочным типом, таким как `String` `Object`массив типа, или, то копируется указатель на данные. В предыдущем примере, если `systemInfo` был добавлен объектная переменная, в предыдущем примере был скопирован указатель из `mySystem` в `yourSystem`, а изменение данных объекта через одну структуру вступит в действие при обращении к через другую структуру.

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
