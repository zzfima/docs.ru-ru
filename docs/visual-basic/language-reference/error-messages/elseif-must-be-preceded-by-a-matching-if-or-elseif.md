---
title: 'Оператору #ElseIf должен предшествовать соответствующий оператор #If или #ElseIf'
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: d6fa76b2aba45e3455cef6ceafc0f737ef56225d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271555"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a>Оператору #ElseIf должен предшествовать соответствующий оператор #If или #ElseIf
`#ElseIf` является директивой условной компиляции. `#ElseIf` Предложение должен предшествовать соответствующий `#If` или `#ElseIf` предложение.  
  
 **Идентификатор ошибки:** BC30014  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что предшествующий `#If` или `#ElseIf` не отделена от этого `#ElseIf` блоком условной компиляции или неправильно размещенной директивой `#End If`.  
  
2.  Если `#ElseIf` предшествует `#Else` директива, либо удалите `#Else` или измените его на `#ElseIf`.  
  
3.  Если все остальное в порядке, добавьте директиву `#If` в начало блока условной компиляции.  
  
## <a name="see-also"></a>См. также
- [Директивы #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
