---
title: Структура &#39; &lt;имя_структуры&gt;&#39; должна содержать по крайней мере один экземпляр переменной-члена или объявление события по крайней мере один экземпляр не помечен &#39; Настраиваемый &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b28dd59271bdaca52072710ea797fae6e9168eab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a>Структура &#39; &lt;имя_структуры&gt;&#39; должна содержать по крайней мере один экземпляр переменной-члена или объявление события по крайней мере один экземпляр не помечен &#39; Настраиваемый &#39;
Определение структуры не включает неиспользуемые совместно переменные или обычные события.  
  
 Каждая структура должна иметь переменную либо событие, которое применяется к каждому определенному экземпляру (неиспользуемому совместно), а не ко всем экземплярам совокупности ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)). Неиспользуемые совместно константы, свойства и процедуры не удовлетворяют этим требованиям. Кроме того, если нет неиспользуемых совместно переменных и только одно событие, не являющихся общими, это событие не может быть `Custom` событий.  
  
 **Идентификатор ошибки:** BC30941  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Определите по крайней мере одну переменную или событие, которое не `Shared`. Если определить только одно событие, должен быть являющуюся, а также не являющихся общими.  
  
## <a name="see-also"></a>См. также  
 [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Практическое руководство. Объявление структуры](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
