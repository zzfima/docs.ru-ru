---
title: "Практическое руководство. Проверка совпадения двух объектов (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76f5c19386cce84207f80d217326d2e3babf4e44
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>Практическое руководство. Проверка совпадения двух объектов (Visual Basic)
Если у вас есть две переменные, которые ссылаются на объекты, можно использовать любой `Is` или `IsNot` оператор, или оба, чтобы определить, ссылаются ли они на один экземпляр.  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>Чтобы проверить ли два объекта совпадают  
  
-   Используйте [оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) или [оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) с двумя переменными в качестве операндов.  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-objects-are-the-same_1.vb)]  
  
 Может потребоваться выполнить определенные действия в зависимости от того, ссылаются ли два объекта на тот же экземпляр. Предыдущий пример сравнивает управления `c` с активным элементом управления в форме `f`. Если нет активный элемент управления, или если имеется один, но он не является тем же экземпляром `c`, то `If` случае инструкция завершается ошибкой, а процедура возвращает без дополнительной обработки.  
  
 Использование `Is` или `IsNot` в зависимости от предпочтений пользователя. Один может оказаться легче другого в заданном выражении.  
  
## <a name="see-also"></a>См. также  
 [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
