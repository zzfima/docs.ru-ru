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
ms.openlocfilehash: dcd20f21a989c327dcfcf27d5638d500b6e4b6da
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929319"
---
# <a name="implements-clause-visual-basic"></a>Предложение Implements (Visual Basic)
Указывает, что член класса или структуры предоставляет реализацию для члена, определенного в интерфейсе.  
  
## <a name="remarks"></a>Примечания  
Ключевое слово не совпадает с [оператором Implements.](../../../visual-basic/language-reference/statements/implements-statement.md) `Implements` `Implements` Инструкция используется для указания того, что класс или структура реализует один или несколько интерфейсов, а затем для каждого элемента `Implements` используется ключевое слово для указания интерфейса и члена, который он реализует.

Если класс или структура реализует интерфейс, он должен включать `Implements` инструкцию сразу после оператора [Class](../../../visual-basic/language-reference/statements/class-statement.md) или [Structure](../../../visual-basic/language-reference/statements/structure-statement.md), и она должна реализовывать все члены, определенные интерфейсом.

## <a name="reimplementation"></a>Воссоздании  
В производном классе можно повторно реализовать член интерфейса, который уже реализован в базовом классе. Это отличается от переопределения члена базового класса в следующих отношениях.

- Член базового класса не обязательно должен быть [переопределяемым](../../../visual-basic/language-reference/modifiers/overridable.md) для повторной реализации.
- Элемент можно повторно реализовать с другим именем.

`Implements` Ключевое слово можно использовать в следующих контекстах:

- [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также

- [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
