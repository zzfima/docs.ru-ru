---
title: "Предложение Where (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryWhere"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "запросы [Visual Basic], Where"
  - "Where - предложение"
  - "Where - оператор"
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Предложение Where (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Устанавливает условия фильтрации для запроса.  
  
## Синтаксис  
  
```  
Where condition  
```  
  
## Части  
 `condition`  
 Обязательный.  Выражение, определяющее, должны ли значения текущего элемента коллекции входить в выходную коллекцию.  Выражение должно возвращать значение `Boolean`, либо эквивалент значения `Boolean`.  Если условие имеет значение `True`, элемент будет включен в результат запроса; в противном случае элемент исключается из результата запроса.  
  
## Заметки  
 Предложение `Where` позволяет отфильтровать данные запроса, выбрав только элементы, удовлетворяющие определенным условиям.  Элементы, значения которых делают предложение `Where` эквивалентным `True`, включаются в результат запроса; другие элементы исключаются.  Выражение, которое используется в предложении `Where`, должно иметь значение `Boolean` или эквивалент `Boolean`, например Integer, значение которого равно `False` при значении переменной, равной нулю.  Можно комбинировать несколько выражений в предложении `Where` с помощью логических операторов `And`, `Or`, `AndAlso`, `OrElse`, `Is` и `IsNot`.  
  
 По умолчанию, выражения запроса не вычисляются до тех пор, пока не становятся доступными, например когда они с привязываются к данным или итерируются в цикле `For`.  В результате предложение `Where` не получает значение до тех пор, пока не осуществляется доступ к запросу.  Если имеются значения, внешние по отношению к запросу, используемые в предложении `Where`, убедитесь, что в предложении `Where` соответствующее значение используется во время выполнения запроса.  Дополнительные сведения о выполнении запроса см. в разделе [Написание первого запроса LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
 В предложении `Where` можно вызывать функции для выполнения вычислений или операций со значениями текущего элемента коллекции.  Вызов функции в предложении `Where` может вызвать немедленное выполнение запроса при определении, а не при доступе.  Дополнительные сведения о выполнении запроса см. в разделе [Написание первого запроса LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
## Пример  
 Следующее выражение запроса использует предложение `From` для объявления диапазона переменной `cust` для каждого объекта `Customer` в коллекции `customers`.  Предложение `Where` использует переменную диапазона для ограничения вывода для заказчиков из указанной области.  В результате запроса цикл `For Each` отображает имя компании для каждого заказчика.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#23)]  
  
## Пример  
 Следующий пример использует `And` и  `Or` логические операторы  `Where` предложение.  
  
 [!code-vb[VbSimpleQuerySamples#31](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#31)]  
  
## См. также  
 [Знакомство с LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)   
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)