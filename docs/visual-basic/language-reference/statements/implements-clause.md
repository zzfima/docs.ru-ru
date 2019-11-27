---
title: Предложение Implements
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
ms.openlocfilehash: f114aee75356e59eafd9d3ba6af9c64402cb374f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345876"
---
# <a name="implements-clause-visual-basic"></a>Предложение Implements (Visual Basic)
Указывает, что член класса или структуры предоставляет реализацию для члена, определенного в интерфейсе.  
  
## <a name="remarks"></a>Примечания  
Ключевое слово `Implements` не совпадает с [оператором Implements](../../../visual-basic/language-reference/statements/implements-statement.md). Используйте оператор `Implements`, чтобы указать, что класс или структура реализует один или несколько интерфейсов, а затем для каждого элемента вы используете `Implements` ключевое слово, чтобы указать, какой интерфейс и какой член он реализует.

Если класс или структура реализует интерфейс, он должен включать инструкцию `Implements` сразу после оператора [Class](../../../visual-basic/language-reference/statements/class-statement.md) или [Structure](../../../visual-basic/language-reference/statements/structure-statement.md), и она должна реализовывать все члены, определенные интерфейсом.

## <a name="reimplementation"></a>Воссоздании  
В производном классе можно повторно реализовать член интерфейса, который уже реализован в базовом классе. Это отличается от переопределения члена базового класса в следующих отношениях.

- Член базового класса не обязательно должен быть [переопределяемым](../../../visual-basic/language-reference/modifiers/overridable.md) для повторной реализации.
- Элемент можно повторно реализовать с другим именем.

Ключевое слово `Implements` можно использовать в следующих контекстах:

- [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также

- [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
