---
title: "&#39; #ElseIf &#39; должен предшествовать соответствующий &#39; #If &#39; или &#39; #ElseIf &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords: BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4b3a4e809e1108fcd6e116538a1947057e9548ce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="39elseif39-must-be-preceded-by-a-matching-39if39-or-39elseif39"></a>&#39; #ElseIf &#39; должен предшествовать соответствующий &#39; #If &#39; или &#39; #ElseIf &#39;
`#ElseIf`является директивой условной компиляции. `#ElseIf` Предложение должен предшествовать соответствующий `#If` или `#ElseIf` предложения.  
  
 **Идентификатор ошибки:** BC30014  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что предшествующий `#If` или `#ElseIf` не был отделен от этого `#ElseIf` блоком условной компиляции или неправильно размещенной директивой `#End If`.  
  
2.  Если `#ElseIf` предшествует `#Else` директивы, либо удалите `#Else` или измените ее на `#ElseIf`.  
  
3.  Если все остальное в порядке, добавьте директиву `#If` в начало блока условной компиляции.  
  
## <a name="see-also"></a>См. также  
 [Директивы #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
