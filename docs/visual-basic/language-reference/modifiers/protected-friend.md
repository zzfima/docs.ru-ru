---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: 331c63dc290d4096e8158f265ee869b47743a273
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053890"
---
# <a name="protected-friend-visual-basic"></a>Protected Friend (Visual Basic)

Комбинация ключевых слов `Protected Friend` является модификатором доступа к члену. Он предоставляет оба [Friend](friend.md) доступа и [Protected](protected.md) доступ к объявленным элементам, поэтому они доступны в любом месте той же сборки, из собственного класса, а также из производных классов. Можно указать `Protected Friend` только для членов классов; нельзя применить `Protected Friend` к членам структуры, так как структуры не может быть унаследован.

> [!NOTE]
> В Visual Studio, выбрав Справка F1 на `protected friend` предоставляет справку для любого [защищенные](protected.md) или [friend](friend.md). Интегрированная среда разработки выбирает один токен в курсор, а не составное слово.

## <a name="rules"></a>Правила

- **Контекст объявления.** Можно использовать `Protected Friend` только на уровне класса. Это означает, что контекст объявления для `Protected` элемент должен быть классом и не может быть исходный файл, пространство имен, интерфейс, модуль, структуру или процедуры. 

## <a name="see-also"></a>См. также

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](friend.md)
- [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](./private-protected.md)
- [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
