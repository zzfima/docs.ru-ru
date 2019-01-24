---
title: '&#39;#ElseIf&#39; должен предшествовать соответствующий &#39;#If&#39; или &#39;#ElseIf&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 1e63595ee573e9356f6870a02b2131897c725baf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505787"
---
# <a name="39elseif39-must-be-preceded-by-a-matching-39if39-or-39elseif39"></a>&#39;#ElseIf&#39; должен предшествовать соответствующий &#39;#If&#39; или &#39;#ElseIf&#39;
`#ElseIf` является директивой условной компиляции. `#ElseIf` Предложение должен предшествовать соответствующий `#If` или `#ElseIf` предложение.  
  
 **Идентификатор ошибки:** BC30014  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что предшествующий `#If` или `#ElseIf` не отделена от этого `#ElseIf` блоком условной компиляции или неправильно размещенной директивой `#End If`.  
  
2.  Если `#ElseIf` предшествует `#Else` директива, либо удалите `#Else` или измените его на `#ElseIf`.  
  
3.  Если все остальное в порядке, добавьте директиву `#If` в начало блока условной компиляции.  
  
## <a name="see-also"></a>См. также
- [Директивы #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
