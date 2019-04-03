---
title: Символ "." или "!", стоящий в начале оператора, может использоваться только внутри оператора "With"
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 4821dbab90eec3c99c0996e8bff10d51b5a8f99d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824953"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a>Символ "." или "!", стоящий в начале оператора, может использоваться только внутри оператора "With"
Точка (.) или восклицательный знак (!), не находится внутри `With` блок происходит без выражения в левой части. Доступ к членам (`.`) и доступ к членам словаря (`!`) требуется выражение, задающее элемент, содержащий элемент. Это должно быть расположено слева метода доступа или в качестве целевого объекта `With` блока, содержащего доступ к члену.  
  
 **Идентификатор ошибки:** BC30157  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что `With` блок имеет правильный формат.  
  
2.  Если нет `With` block, добавьте выражение слева от метода доступа, результатом вычисления элемента, содержащего элемент.  
  
## <a name="see-also"></a>См. также

- [Специальные символы в коде](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [Оператор With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
