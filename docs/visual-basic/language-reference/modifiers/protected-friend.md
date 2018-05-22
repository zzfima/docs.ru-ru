---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: b72cbee0394043620e792d1c014bfe55121e175e
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/18/2018
---
# <a name="protected-friend-visual-basic"></a>Protected Friend (Visual Basic)

`Protected Friend` Сочетание ключевых слов — это модификатор доступа члена. Он предоставляет оба [Friend](friend.md) доступа и [Protected](protected.md) доступ на объявленные элементы, поэтому они доступны в любом месте той же сборки, из собственного класса и из производных классов. Можно указать `Protected Friend` только для членов классов; не удается применить `Protected Friend` к членам структуры, так как структуры не наследуется.

> [!NOTE]
> В Visual Studio, выбрав Справка F1 на `protected friend` предоставляет справку для любого [защищенных](protected.md) или [friend](friend.md). Интегрированная среда разработки выбирает один токен в курсор, а не составное слово.

## <a name="rules"></a>Правила

- **Контекст объявления.** Можно использовать `Protected Friend` только на уровне класса. Это означает, что контекст объявления для `Protected` элемент должен быть классом и не может быть исходный файл, пространство имен, интерфейса, модуля, структуры или процедуры. 


## <a name="see-also"></a>См. также

[Public](../../../visual-basic/language-reference/modifiers/public.md)  
[Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
[Friend](friend.md)   
[Закрытые](../../../visual-basic/language-reference/modifiers/private.md)  
[Protected Private](./private-protected.md)   
[Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
