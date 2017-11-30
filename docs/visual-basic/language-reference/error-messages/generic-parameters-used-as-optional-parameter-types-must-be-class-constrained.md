---
title: "Универсальные параметры, используемые как типы необязательных параметров, должны быть ограничены классом"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords: BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a13ea66f12e54db4e585577e20e1f5396669f1a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
