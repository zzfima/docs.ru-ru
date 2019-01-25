---
title: Начальные &#39;. &#39; или &#39;! &#39; может располагаться только внутри &#39;с&#39; инструкции
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: e64318d4ececbd887f55a1a202cc2d58c90c8fc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625956"
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a>Начальные &#39;. &#39; или &#39;! &#39; может располагаться только внутри &#39;с&#39; инструкции
Точка (.) или восклицательный знак (!), не находится внутри `With` блок происходит без выражения в левой части. Доступ к членам (`.`) и доступ к членам словаря (`!`) требуется выражение, задающее элемент, содержащий элемент. Это должно быть расположено слева метода доступа или в качестве целевого объекта `With` блока, содержащего доступ к члену.  
  
 **Идентификатор ошибки:** BC30157  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что `With` блок имеет правильный формат.  
  
2.  Если нет `With` block, добавьте выражение слева от метода доступа, результатом вычисления элемента, содержащего элемент.  
  
## <a name="see-also"></a>См. также
- [Специальные символы в коде](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [Оператор With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
