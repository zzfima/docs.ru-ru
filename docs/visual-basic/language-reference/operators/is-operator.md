---
title: "Оператор Is (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.is"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "операторы сравнения"
  - "эквивалентные объекты"
  - "Is - оператор [Visual Basic]"
  - "TypeOf...Is - выражение"
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Оператор Is (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Сравнивает две переменные объектных ссылок.  
  
## Синтаксис  
  
```  
  
result = object1 Is object2  
```  
  
## Части  
 `result`  
 Обязательный.  Любое значение `Boolean`.  
  
 `object1`  
 Обязательный.  Любое имя `Object`.  
  
 `object2`  
 Обязательный.  Любое имя `Object`.  
  
## Заметки  
 Оператор `Is` определяет, относятся ли две объектные ссылки к одному и тому же объекту.  Однако сравнение значений не выполняется.  Если `object1` и `object2` ссылаются на один экземпляр объекта, то `result` является `True`; если нет, то `result` является `False`.  
  
 `Is` можно использовать вместе с ключевым словом `TypeOf` для формирования выражения `TypeOf`...`Is`, которое используется для проверки совместимости объектной переменной с типом данных.  
  
> [!NOTE]
>  Ключевое слово `Is` также используется в [Оператор Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## Пример  
 В следующем примере оператор `Is` используется для сравнения пар объектных ссылок.  Результаты присваиваются значению `Boolean`, показывающему, являются ли два объекта идентичными.  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 Как показано в предыдущем примере, можно использовать оператор `Is` для проверки объектов раннего и позднего связывания.  
  
## См. также  
 [Оператор TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)   
 [Оператор IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Операторы сравнения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)