---
title: Private Protected (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: fea43558ac0fe8181f2786b69f2621346d446b2e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376394"
---
# <a name="private-protected-visual-basic"></a>Private Protected (Visual Basic)

Комбинация ключевых слов `Private Protected` является модификатором доступа к члену. Объект `Private Protected` член доступны все элементы в содержащий его класс, так и по типам, производным от содержащего класса, но только в том случае, если они находятся в его соответствующая сборка.

Можно указать `Private Protected` только для членов классов; нельзя применить `Private Protected` к членам структуры, так как структуры не может быть унаследован.

`Private Protected` Модификатор доступа поддерживается в Visual Basic 15.5 и более поздних версий. Чтобы использовать его, можно добавить следующий элемент в проект Visual Basic (\*.vbproj) файла. На компьютере установлен столько времени, Visual Basic 15.5 или более поздней версии, можно воспользоваться преимуществами всех функций языка, поддерживаемые в последней версии компилятора Visual Basic:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Дополнительные сведения см. в разделе [параметр версии языка Visual Basic](../../language-reference/configure-language-version.md).

> [!NOTE]
> В Visual Studio, выбрав Справка F1 на `private protected` предоставляет справку для любого [частного](private.md) или [защищенные](protected.md). Интегрированная среда разработки выбирает один токен в курсор, а не составное слово.

## <a name="rules"></a>Правила

- **Контекст объявления.** Можно использовать `Private Protected` только на уровне класса. Это означает, что контекст объявления для `Protected` элемент должен быть классом и не может быть исходный файл, пространство имен, интерфейс, модуль, структуру или процедуры.

## <a name="behavior"></a>Поведение

- **Уровень доступа.** Весь код в классе можно получить доступ к его элементам. Код в любой класс, производный от базового класса, содержащийся в той же сборке может получить доступ ко всем `Private Protected` элементы базового класса. Тем не менее, код в любом классе, который является производным от базового класса и содержится в другой сборке не может получить доступ к базовым классом `Private Protected` элементов.

- **Модификаторы доступа.** Ключевые слова, указывающие уровень доступа, называются *модификаторы доступа*. Сравнение модификаторов доступа, см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

Модификатор `Private Protected` можно использовать в следующих контекстах:

- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md) вложенного класса

- [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)

- [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)

- [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) делегата, вложенные в классе

- [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)

- [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md) перечисления, вложенные в классе

- [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)

- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)

- [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md) интерфейса, вложенные в классе

- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)

- [Структура инструкции](../../../visual-basic/language-reference/statements/structure-statement.md) структуры, вложенные в классе

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
