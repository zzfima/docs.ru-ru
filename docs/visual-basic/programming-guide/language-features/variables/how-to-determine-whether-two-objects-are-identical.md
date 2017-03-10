---
title: "Практическое руководство. Определение идентичности двух объектов (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "объектные переменные, определение идентификации"
  - "объекты [Visual Basic], сравнение"
  - "проверка, объекты"
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Практическое руководство. Определение идентичности двух объектов (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] две ссылки на переменные считаются идентичными, если их указатели совпадают, то есть если обе переменных указывают на один экземпляр класса в памяти.  Например, в приложении Windows Forms может потребоваться сделать сравнение, чтобы определить, идентичен ли текущий экземпляр \(`Me`\) конкретному экземпляру, например `Form2`.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] предоставляет два оператора для сравнения указателей.  [Оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) возвращает значение `True` если объекты идентичны, и [Оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) возвращает значение `True` если нет.  
  
## Определение идентичности двух объектов  
  
#### Определение идентичности двух объектов  
  
1.  Укажите выражение `Boolean` для проверки двух объектов.  
  
2.  В проверяемом выражении используйте оператор `Is` с двумя объектами в качестве операндов.  
  
     `Is` возвращает значение `True`, если объекты указывают на один и тот же экземпляр класса.  
  
## Определение различности двух объектов  
 В некоторых случаях требуется выполнить действие, если два объекта не идентичны, и может быть неудобно объединять `Not` и `Is`, например `If Not obj1 Is obj2`.  В таком случае можно использовать оператор `IsNot`.  
  
#### Определение различности двух объектов  
  
1.  Укажите выражение `Boolean` для проверки двух объектов.  
  
2.  В проверяемом выражении используйте оператор `IsNot` с двумя объектами в качестве операндов.  
  
     `IsNot` возвращает `True`, если объекты не указывают на один и тот же экземпляр класса.  
  
## Пример  
 Следующий пример проверяет пары переменных `Object`, чтобы увидеть, указывают ли они на один экземпляр класса.  
  
 [!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/visualbasic/how-to-determine-whether_1_1.vb)]  
  
 В предыдущем примере отображаются следующие выходные данные.  
  
 `objA different from objB?  True`  
  
 `objA identical to objC?  True`  
  
## См. также  
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md)   
 [Оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Практическое руководство. Определение наличия связи между двумя объектами](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)   
 [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)