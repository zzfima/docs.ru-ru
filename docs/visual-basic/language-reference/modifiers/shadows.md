---
title: Shadows (Visual Basic)
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
ms.openlocfilehash: e879819d945f3e7256edd34e87b9cae4a04c0829
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512740"
---
# <a name="shadows-visual-basic"></a>Shadows (Visual Basic)
Указывает, что объявленный программный элемент повторно объявляет и скрывает одинаково названные элементы или набор перегруженных элементов в базовом классе.  
  
## <a name="remarks"></a>Примечания  
 Основная цель затенение (который также называется *скрытие по имени*) — Сохранение определения членов класса. Базовый класс может претерпеть изменения, создается элемент с тем же именем, как один, которые вы уже определили. В этом случае `Shadows` применении модификатора ссылается в классе быть член определенный, а не к новому элементу базового класса.  
  
 Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия. Дополнительные сведения см. в разделе [сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## <a name="rules"></a>Правила  
  
-   **Контекст объявления.** Можно использовать `Shadows` только на уровне класса. Это означает, что контекст объявления для `Shadows` элемент должен быть классом и не может быть исходный файл, пространство имен, интерфейс, модуль, структуру или процедуры.  
  
     Можно объявить только один затененный элемент в одном операторе объявления.  
  
-   **Комбинированные модификаторы.** Нельзя указать `Shadows` вместе с `Overloads`, `Overrides`, или `Static` в одном объявлении.  
  
-   **Типы элементов.** Можно скрыть любой тип объявленного элемента, используя любой другой тип. При скрытии свойства или процедуры с другое свойство или процедура, параметры и тип возвращаемого значения имеют для получения соответствия строкам в процедуру или свойство базового класса.  
  
-   **Доступ к.** Затененный элемент в базовом классе обычно недоступен из производного класса, который его скрывает. Тем не менее следующие соображения.  
  
    -   Если скрывающий элемент недоступен из кода, обращения к нему, ссылка разрешается переопределяемый элемент. Например если `Private` элемент скрывает элемент базового класса, код, который не имеет разрешения на доступ к `Private` элемент обращается к элементу базового класса.  
  
    -   При скрытии элемент скрыт элемент можно получить доступ через объект объявлен с типом базового класса. Также доступен через `MyBase`.  
  
 Модификатор `Shadows` можно использовать в следующих контекстах:  
  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также
- [Общие](../../../visual-basic/language-reference/modifiers/shared.md)
- [Статические](../../../visual-basic/language-reference/modifiers/static.md)
- [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)
- [Me, My, MyBase и MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Перегрузки](../../../visual-basic/language-reference/modifiers/overloads.md)
- [Переопределяемые](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Переопределения](../../../visual-basic/language-reference/modifiers/overrides.md)
- [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
