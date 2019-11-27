---
title: Частный защищенный
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 265141f77f4a61a61414a07214830feaa8a1ab05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351346"
---
# <a name="private-protected-visual-basic"></a>Частный защищенный (Visual Basic)

Комбинация ключевых слов `Private Protected` является модификатором доступа к члену. Элемент `Private Protected` доступен для всех элементов в содержащем его классе, а также по типам, производным от содержащего класса, но только в том случае, если они находятся в содержащей его сборке.

Можно указать `Private Protected` только для членов классов; к членам структуры нельзя применять `Private Protected`, поскольку структуры не могут наследоваться.

Модификатор доступа `Private Protected` поддерживается Visual Basic 15,5 и более поздних версий. Чтобы использовать его, можно добавить следующий элемент в файл проекта Visual Basic (\*. vbproj). Если в системе установлен Visual Basic 15,5 или более поздней версии, он позволяет воспользоваться всеми возможностями языка, поддерживаемыми последней версией компилятора Visual Basic.

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Дополнительные сведения см. [в разделе Задание языковой версии Visual Basic](../../language-reference/configure-language-version.md).

> [!NOTE]
> В Visual Studio выбор справки F1 в `private protected` предоставляет справку как для [частных](private.md) , так и для [защищенных](protected.md). Интегрированная среда разработки выбирает один маркер под курсором, а не составное слово.

## <a name="rules"></a>Правила

- **Контекст объявления.** `Private Protected` можно использовать только на уровне класса. Это означает, что контекст объявления для элемента `Protected` должен быть классом и не может быть исходным файлом, пространством имен, интерфейсом, модулем, структурой или процедурой.

## <a name="behavior"></a>Поведение

- **Уровень доступа.** Весь код в классе может обращаться к его элементам. Код в любом классе, производном от базового класса и содержащийся в той же сборке, имеет доступ ко всем `Private Protected`ным элементам базового класса. Однако код в любом классе, производном от базового класса и содержащийся в другой сборке, не может получить доступ к базовому классу `Private Protected` элементов.

- **Модификаторы доступа.** Ключевые слова, определяющие уровень доступа, называются *модификаторами доступа*. Сравнение модификаторов доступа см. [в разделе уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

Модификатор `Private Protected` можно использовать в следующих контекстах:

- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md) вложенного класса

- [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)

- [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)

- [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) делегата, вложенного в класс

- [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)

- [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md) перечисления, вложенного в класс

- [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)

- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)

- [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md) интерфейса, вложенного в класс

- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)

- [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md) структуры, вложенной в класс

- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>См. также

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](friend.md)
- [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)
- [Protected Friend](./protected-friend.md)
- [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
