---
title: Универсальные параметры, используемые как типы необязательных параметров, должны быть ограничены классом
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 7e2b59f758ef236717a912694576b514e2ae8a60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590043"
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a>Универсальные параметры, используемые как типы необязательных параметров, должны быть ограничены классом
Процедура объявлена с необязательным параметром, который использует параметр типа, который не обязательно должен быть ссылочным типом.  
  
 Всегда необходимо указывать значение по умолчанию для каждого необязательного параметра. Если параметр имеет ссылочный тип, дополнительное значение должно быть `Nothing`, которое является допустимым для любого ссылочного типа. Тем не менее если параметр имеет тип значения, этот тип должен быть простой тип данных, ранее определенных Visual Basic. Это объясняется значение составного типа, например пользовательской структуры имеет значения по умолчанию.  
  
 При использовании параметра типа для необязательного параметра, необходимо гарантировать, что это ссылочного типа во избежание типа значения и не имеет значения по умолчанию. Это означает, что необходимо ограничить параметр типа с помощью `Class` ключевое слово или имя определенного класса.  
  
 **Идентификатор ошибки:** BC32124  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Ограничить параметр типа гарантированно принимает ссылочный тип или не используйте его для необязательного параметра.  
  
## <a name="see-also"></a>См. также  
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Список типов](../../../visual-basic/language-reference/statements/type-list.md)  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Nothing](../../../visual-basic/language-reference/nothing.md)
