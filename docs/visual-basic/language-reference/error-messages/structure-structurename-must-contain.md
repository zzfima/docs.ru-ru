---
title: Структура <structurename> должна содержать по крайней мере один экземпляр переменной члена или экземпляр объявления события, не помеченный как Custom
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 4ce24073896326bb5a68e563e2d34aafa09ef1c1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593206"
---
# <a name="structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a>Структура "\<имя_структуры >" должен содержать по крайней мере один экземпляр переменной члена или объявление по крайней мере один экземпляр события, не помечен как «Custom»
Определение структуры не включает все совместно переменные или обычные события.  
  
 Каждая структура должна иметь переменную либо событие, которое применяется к каждому определенному экземпляру (не общие), а не ко всем экземплярам совокупности ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)). Неиспользуемые совместно константы, свойства и процедуры не удовлетворяют этим требованиям. Кроме того, если нет неиспользуемых совместно переменных и только одно событие, не являющиеся общими, что событие не может быть `Custom` событий.  
  
 **Идентификатор ошибки:** BC30941  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Определите по крайней мере одну переменную или событие, которое не является `Shared`. Если вы определяете только одно событие, он должен быть являющуюся, а также не совместно.  
  
## <a name="see-also"></a>См. также

- [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Практическое руководство. Объявление структуры](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
