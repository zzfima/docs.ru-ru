---
title: Универсальные параметры, используемые как типы необязательных параметров, должны быть ограничены классом
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 9b0293472f5eda74c2bf8fb215e15ae5cf8d8b98
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813903"
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a>Универсальные параметры, используемые как типы необязательных параметров, должны быть ограничены классом
Процедура объявлена с необязательным параметром, который использует параметр типа, который не должен быть ссылочным типом.  
  
 Должно всегда предоставляться значение по умолчанию для каждого необязательного параметра. Если параметр имеет ссылочный тип, дополнительное значение должно быть `Nothing`, который является допустимое значение для любого ссылочного типа. Тем не менее если параметр имеет тип значения, этот тип должен быть простой тип данных, ранее определенных Visual Basic. Это обусловлено составные типы значения, такие как определяемая пользователем структура имеет нет допустимых значений по умолчанию.  
  
 При использовании с параметром типа для необязательного параметра, необходимо гарантировать, что это ссылочного типа во избежание возможного типа значения не имеет значения по умолчанию. Это означает, что необходимо ограничить параметр типа с помощью `Class` ключевое слово или имя определенного класса.  
  
 **Идентификатор ошибки:** BC32124  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Ограничить параметр типа для приема только ссылочным типом или не используйте его для необязательного параметра.  
  
## <a name="see-also"></a>См. также

- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Список типов](../../../visual-basic/language-reference/statements/type-list.md)
- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Nothing](../../../visual-basic/language-reference/nothing.md)
