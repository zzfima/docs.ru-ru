---
title: Protected
ms.date: 07/20/2015
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
ms.openlocfilehash: 740c998b8a6ccc6798bce37e9b08e408dac7c17d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351301"
---
# <a name="protected-visual-basic"></a>Protected (Visual Basic)

Модификатор доступа к члену, указывающий, что один или несколько объявленных программных элементов доступны только в своем собственном классе или производном классе.

## <a name="remarks"></a>Примечания

Иногда программный элемент, объявленный в классе, содержит конфиденциальные данные или ограниченный код и требуется ограничить доступ к элементу. Однако если класс является наследуемым и предполагается иерархия производных классов, то эти производные классы могут быть необходимы для доступа к данным или коду в этих производных классах. В этом случае необходимо, чтобы элемент был доступен как из базового класса, так и из всех производных классов. Чтобы ограничить доступ к элементу таким образом, его можно объявить с помощью `Protected`.

> [!NOTE]
> Модификатор доступа `Protected` можно сочетать с двумя другими модификаторами:
>
> - Модификатор [Protected Friend](protected-friend.md) делает член класса доступным из этого класса, из производных классов и из той же сборки, в которой определен класс.
> - Модификатор [Private protected](private-protected.md) делает член класса доступным для производных типов, но только внутри его содержащей сборки.

## <a name="rules"></a>Правила

**Контекст объявления.** `Protected` можно использовать только на уровне класса. Это означает, что контекст объявления для элемента `Protected` должен быть классом и не может быть исходным файлом, пространством имен, интерфейсом, модулем, структурой или процедурой.

## <a name="behavior"></a>Поведение

- **Уровень доступа.** Весь код в классе может обращаться к его элементам. Код в любом классе, производном от базового класса, имеет доступ ко всем `Protected`ным элементам базового класса. Это справедливо для всех поколений наследования. Это означает, что класс может получить доступ к `Protected` элементам базового класса базового класса и т. д.

     Защищенный доступ не является надмножеством или подмножеством дружественного доступа.

- **Модификаторы доступа.** Ключевые слова, определяющие уровень доступа, называются *модификаторами доступа*. Сравнение модификаторов доступа см. [в разделе уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

Модификатор `Protected` можно использовать в следующих контекстах:

- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)

- [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)

- [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)

- [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)

- [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)

- [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)

- [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)

- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)

- [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)

- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)

- [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)

- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>См. также

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
