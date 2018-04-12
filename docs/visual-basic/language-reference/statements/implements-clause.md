---
title: Предложение Implements (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ImplementsClause
helpviewer_keywords:
- interface implementation [Visual Basic], reimplementation
- interface members [Visual Basic], reimplementation
- interface members [Visual Basic], Implements keyword
- interface members
- members [Visual Basic], reimplementation
- interface implementation [Visual Basic], Implements keyword
- interface members [Visual Basic], implementing
- Implements keyword [Visual Basic]
- Implements statement [Visual Basic], about Implements
- members [Visual Basic], implementing
- members [Visual Basic], Implements keyword
- reimplementation
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 73f66eda29e37fda15b4c838da5a0458684131da
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="implements-clause-visual-basic"></a>Предложение Implements (Visual Basic)
Указывает, что член класса или структуры предоставляет реализацию для члена, определенного в интерфейсе.  
  
## <a name="remarks"></a>Примечания  
`Implements` Ключевое слово не совпадает с [оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md). Вы используете `Implements` инструкцию, чтобы указать, что класс или структура реализует один или несколько интерфейсов, и затем для каждого элемента используется `Implements` ключевое слово, чтобы указать, какой интерфейс и какой элемент, он реализует.

Если класс или структура реализует интерфейс, она должна включать `Implements` инструкции сразу после [оператор Class](../../../visual-basic/language-reference/statements/class-statement.md) или [оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md), и он должен реализовывать все члены определяется интерфейсом.

## <a name="reimplementation"></a>Повторная реализация  
Производный класс может повторно реализовать член интерфейса, который уже реализован базовым классом. Это отличается от переопределения члена базового класса в следующих аспектах:

- Член базового класса не требуется быть [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) для быть воссозданы.
- Можно реализовать элемент под другим именем.

`Implements` Ключевое слово может использоваться в следующих контекстах:
- [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также  
 [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
