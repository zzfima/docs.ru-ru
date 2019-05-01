---
title: Аргументы типа не могут быть выведены от делегата
ms.date: 07/20/2015
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords:
- BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
ms.openlocfilehash: 1024cf6f2c1fa112db29cb710eef190a5022d3af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013638"
---
# <a name="type-arguments-could-not-be-inferred-from-the-delegate"></a>Аргументы типа не могут быть выведены от делегата
Оператор назначения использует `AddressOf` для назначения делегату адреса универсальной процедуры, но он не предоставляет универсальной процедуре никакие аргументы типа.  
  
 Как правило, при вызове универсального типа указывается аргумент типа для каждого параметра типа, определяемого этим универсальным типом. Если вы не предоставляете никакие аргументы типов, компилятор пытается вывести типы, которые должны быть переданы в параметры типов. Если контекст не предоставляет достаточно сведений, чтобы компилятор мог вывести типы, возникает ошибка.  
  
 **Идентификатор ошибки:** BC36564  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Укажите аргументы типа для универсальной процедуры в выражении `AddressOf` .  
  
## <a name="see-also"></a>См. также

- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Generic Procedures in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)
- [Список типов](../../../visual-basic/language-reference/statements/type-list.md)
- [Методы расширения](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
