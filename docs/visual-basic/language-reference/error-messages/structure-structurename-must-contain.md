---
title: Структура &#39; &lt;имя_структуры&gt; &#39; должен содержать по крайней мере один экземпляр переменной члена или объявление события по крайней мере один экземпляр не помечен как &#39;Custom&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: d8c654c212a459d40c6cf20cd62c3e0fcda8511b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603785"
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a>Структура &#39; &lt;имя_структуры&gt; &#39; должен содержать по крайней мере один экземпляр переменной члена или объявление события по крайней мере один экземпляр не помечен как &#39;Custom&#39;
Определение структуры не включает все совместно переменные или обычные события.  
  
 Каждая структура должна иметь переменную либо событие, которое применяется к каждому определенному экземпляру (не общие), а не ко всем экземплярам совокупности ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)). Неиспользуемые совместно константы, свойства и процедуры не удовлетворяют этим требованиям. Кроме того, если нет неиспользуемых совместно переменных и только одно событие, не являющиеся общими, что событие не может быть `Custom` событий.  
  
 **Идентификатор ошибки:** BC30941  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Определите по крайней мере одну переменную или событие, которое не является `Shared`. Если вы определяете только одно событие, он должен быть являющуюся, а также не совместно.  
  
## <a name="see-also"></a>См. также
- [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Практическое руководство. Объявление структуры](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
