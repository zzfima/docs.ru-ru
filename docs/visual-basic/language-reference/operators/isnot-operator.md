---
title: "Оператор IsNot (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.isnot"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "IsNot - оператор"
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Оператор IsNot (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Сравнивает две переменные объектных ссылок.  
  
## Синтаксис  
  
```  
  
result = object1 IsNot object2  
```  
  
## Части  
 `result`  
 Обязательный.  Значение `Boolean`.  
  
 `object1`  
 Обязательный.  Любая переменная `Object` или выражение.  
  
 `object2`  
 Обязательный.  Любая переменная `Object` или выражение.  
  
## Заметки  
 Оператор `IsNot` определяет, ссылаются ли две объектные ссылки на различные объекты.  Однако сравнение значений не выполняется.  Если `object1` и `object2` ссылаются на один экземпляр объекта, то `result` является `False`; если нет, то `result` является `True`.  
  
 `IsNot` является противоположностью оператора `Is`.  Преимуществом `IsNot` является то, что можно избежать неуклюжего синтаксиса с `Not` и `Is`, который достаточно трудно читать.  
  
 Можно использовать операторы `Is` и `IsNot` для проверки объектов с ранней и поздней привязкой.  
  
> [!NOTE]
>  Оператор `IsNot` нельзя использовать для сравнения выражений, возвращенных оператором `TypeOf`.  Вместо этого используйте операторы `Not` и `Is`.  
  
## Пример  
 Следующий код примера использует оба оператора: `Is` и `IsNot` для выполнения того же сравнения.  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## См. также  
 [Оператор Is](../../../visual-basic/language-reference/operators/is-operator.md)   
 [Оператор TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Практическое руководство. Проверка совпадения двух объектов](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)