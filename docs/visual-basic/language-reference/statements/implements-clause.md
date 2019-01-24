---
title: Предложение Implements (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: cb0ea5ce52effad4df541e6a9196b1faf279262e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522518"
---
# <a name="implements-clause-visual-basic"></a>Предложение Implements (Visual Basic)
Указывает, что член класса или структуры предоставляет реализацию для члена, определенного в интерфейсе.  
  
## <a name="remarks"></a>Примечания  
`Implements` Ключевое слово не может так же, как [оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md). Использовании `Implements` инструкцию, чтобы указать, что класс или структура реализует один или несколько интерфейсов, а затем для каждого члена можно использовать `Implements` ключевое слово, чтобы указать, какой интерфейс и какой элемент он реализует.

Если класс или структура реализует интерфейс, она должна включать `Implements` инструкции сразу после [оператор Class](../../../visual-basic/language-reference/statements/class-statement.md) или [оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md), и он должен реализовывать все члены определенные в интерфейсе.

## <a name="reimplementation"></a>Повторная реализация  
В производном классе может повторно реализовать член интерфейса, который уже реализован базовым классом. Это отличается от переопределения члена базового класса в следующих аспектах:

- Член базового класса не требуется быть [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) чтобы быть воссозданы.
- Можно реализовать элемент с другим именем.

`Implements` Слово может использоваться в следующих контекстах:
- [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также
- [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
