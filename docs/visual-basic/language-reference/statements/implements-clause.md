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
ms.openlocfilehash: 1e34245ac528e9e2463afbfd07dff91bf693830b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603409"
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
