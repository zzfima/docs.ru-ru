---
title: Начальные &#39;. &#39; или &#39;! &#39; может использоваться только внутри &#39;с&#39; инструкции
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 7802b8e0aaf3dff83d5bfbe11f0b8bb1b5bb46cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589451"
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a>Начальные &#39;. &#39; или &#39;! &#39; может использоваться только внутри &#39;с&#39; инструкции
Точка (.) или восклицательный знак (!), не находится внутри `With` блок происходит без выражения слева. Доступ к членам (`.`) и доступ к членам словаря (`!`) требуется выражение, задающее элемент, содержащий элемент. Это должно быть расположено слева от метода доступа или в качестве целевого объекта `With` блок, содержащий доступ к члену.  
  
 **Идентификатор ошибки:** BC30157  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что `With` блок имеет правильный формат.  
  
2.  При наличии не `With` блока, добавьте выражение слева от метода доступа, результатом вычисления элемента, содержащего элемент.  
  
## <a name="see-also"></a>См. также  
 [Специальные символы в коде](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 [Оператор With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
