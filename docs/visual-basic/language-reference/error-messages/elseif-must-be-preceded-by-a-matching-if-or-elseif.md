---
title: '&#39;#ElseIf&#39; должен предшествовать соответствующий &#39;#If&#39; или &#39;#ElseIf&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: ef904173b1791309f6c2722bd959cabdad1d71da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588152"
---
# <a name="39elseif39-must-be-preceded-by-a-matching-39if39-or-39elseif39"></a>&#39;#ElseIf&#39; должен предшествовать соответствующий &#39;#If&#39; или &#39;#ElseIf&#39;
`#ElseIf` является директивой условной компиляции. `#ElseIf` Предложение должен предшествовать соответствующий `#If` или `#ElseIf` предложения.  
  
 **Идентификатор ошибки:** BC30014  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что предшествующий `#If` или `#ElseIf` не был отделен от этого `#ElseIf` блоком условной компиляции или неправильно размещенной директивой `#End If`.  
  
2.  Если `#ElseIf` предшествует `#Else` директивы, либо удалите `#Else` или измените ее на `#ElseIf`.  
  
3.  Если все остальное в порядке, добавьте директиву `#If` в начало блока условной компиляции.  
  
## <a name="see-also"></a>См. также  
 [Директивы #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
