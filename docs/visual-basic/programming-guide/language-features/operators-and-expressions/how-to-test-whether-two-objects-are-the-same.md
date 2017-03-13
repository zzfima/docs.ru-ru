---
title: "Практическое руководство. Проверка совпадения двух объектов (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Is - оператор [Visual Basic], сравнение объектов"
  - "объекты [Visual Basic], переменные, ссылающиеся на тот же"
  - "ссылка на переменные"
  - "переменные [Visual Basic], справочник"
  - "переменные [Visual Basic], ссылка на тот же объект"
  - "код Visual Basic, операторы"
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Практическое руководство. Проверка совпадения двух объектов (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Если имеются две переменные, которые ссылаются на объекты, можно использовать операторы `Is` и\/или `IsNot`, чтобы определить, ссылаются ли эти переменные на один и тот же экземпляр.  
  
### Проверка совпадения двух объектов  
  
-   Используйте [Оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) или [Оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) с двумя переменными в качестве операндов.  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-objects-are-the-same_1.vb)]  
  
 Пользователю может потребоваться выполнить определенные действия в зависимости от того, ссылаются ли два объекта на один и тот же экземпляр или нет.  Предыдущий пример сравнивает элемент управления `c` с активным элементом управления на форме `f`.  Если активный элемент управления отсутствует, или он присутствует, но не является тем же экземпляром `c`, тогда инструкция `If` завершается ошибкой, и осуществляется выход из процедуры без дальнейшей обработки.  
  
 Использование `Is` или `IsNot` зависит от предпочтений пользователя.  Один может читаться легче другого в заданном выражении.  
  
## См. также  
 [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)