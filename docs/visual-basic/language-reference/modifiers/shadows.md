---
title: Shadows
ms.date: 07/20/2015
f1_keywords:
- vb.Shadows
- shadows
helpviewer_keywords:
- shadowing
- duplicate names [Visual Basic]
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic]
- names [Visual Basic], shadowing
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
ms.openlocfilehash: e9a423fa69ad1dcd8c1d4a5b7085e5b5da548f93
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351266"
---
# <a name="shadows-visual-basic"></a>Shadows (Visual Basic)

Указывает, что объявленный программный элемент повторно объявляет и скрывает элемент с идентичным именем или набор перегруженных элементов в базовом классе.

## <a name="remarks"></a>Заметки

Основное назначение теневого копирования (которое также называется *скрытием по имени*) — сохранение определения членов класса. Базовый класс может быть подвергнут изменениям, создающим элемент с тем же именем, что и у уже определенного. В этом случае модификатор `Shadows` заставляет ссылки через класс разрешаться в определенный член, а не в новый элемент базового класса.

Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия. Дополнительные сведения см. [в разделе теневая поддержка в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).

## <a name="rules"></a>Правила

- **Контекст объявления.** `Shadows` можно использовать только на уровне класса. Это означает, что контекст объявления для элемента `Shadows` должен быть классом и не может быть исходным файлом, пространством имен, интерфейсом, модулем, структурой или процедурой.

  В одном операторе объявления можно объявить только один элемент с тенью.

- **Комбинированные модификаторы.** В одном объявлении нельзя указать `Shadows` вместе с `Overloads`, `Overrides`или `Static`.

- **Типы элементов.** Можно скрыть любой тип объявленного элемента, используя любой другой тип. При скрытии свойства или процедуры с другим свойством или процедурой параметры и тип возвращаемого значения не должны совпадать с параметрами в свойстве или процедуре базового класса.

- **Данному.** Затененный элемент в базовом классе обычно недоступен в производном классе, который его затеняет. Однако применимы следующие рекомендации.

  - Если элемент теневого копирования недоступен из кода, ссылающегося на него, ссылка разрешается в затененный элемент. Например, если элемент `Private` затеняет элемент базового класса, код, который не имеет разрешения на доступ к элементу `Private`, вместо этого обращается к элементу базового класса.

  - При скрытии элемента доступ к затененному элементу по-прежнему можно получить через объект, объявленный с типом базового класса. Вы также можете получить доступ к нему с помощью `MyBase`.

Модификатор `Shadows` можно использовать в следующих контекстах:

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

- [Общие](../../../visual-basic/language-reference/modifiers/shared.md)
- [Статические](../../../visual-basic/language-reference/modifiers/static.md)
- [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)
- [Me, My, MyBase и MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)
- [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Переопределения](../../../visual-basic/language-reference/modifiers/overrides.md)
- [Затенение в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
