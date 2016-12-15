---
title: "Практическое руководство. Создание запросов LINQ на языке C# | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "запросы [LINQ в C#], написание"
  - "выражения запросов [LINQ в C#], написание запросов"
  - "написание запросов LINQ"
ms.assetid: 45e47fcc-cfa1-4b72-b161-d038ae87bd23
caps.latest.revision: 25
caps.handback.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Создание запросов LINQ на языке C# #
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В этом разделе рассматриваются три способа создания запросов [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] на языке C\#.  
  
1.  Использование синтаксиса запроса.  
  
2.  Использование синтаксиса метода.  
  
3.  Использование сочетания синтаксиса запроса и синтаксиса метода.  
  
 В следующем примере демонстрируются простые запросы [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] при использовании каждого из перечисленных выше синтаксисов.  Общее правило таково: следует использовать \(1\) всегда, когда это возможно; \(2\) и \(3\) при необходимости.  
  
> [!NOTE]
>  Эти запросы работают с простыми коллекциями в памяти, однако базовый синтаксис идентичен синтаксису, использованному в [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq_md.md)] и [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
## Пример  
  
## Синтаксис запроса  
 Лучше всего для создания запросов использовать *синтаксис запроса*, создавая *выражения запросов*.  В следующем примере показано три выражения запроса.  В первом выражении демонстрируется фильтрация или ограничение результатов путем применения условий в предложении `where`.  Оно возвращает все элементы в исходной последовательности со значениями больше 7 и меньше 3.  Второе выражение демонстрирует сортировку возвращаемых результатов.  Третий запрос демонстрирует группировку результатов.  Он возвращает две группы на основе первой буквы слова.  
  
 [!code-cs[csProgGuideLINQ#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-write-linq-queries_1.cs)]  
  
 Обратите внимание, что тип запросов — <xref:System.Collections.Generic.IEnumerable%601>.  Все эти запросы можно написать с помощью `var`, как показано в примере ниже.  
  
 `var query = from num in numbers...`  
  
 В каждом из приведенных выше примеров фактическое выполнение запроса откладывается до использования переменной запроса в операторе `foreach`.  Дополнительные сведения см. в разделе [Introduction to LINQ Queries \(C\#\)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
## Пример  
  
## Синтаксис метода  
 Некоторые операции запросов должны быть выражены в виде вызова метода.  Чаще всего используются методы, возвращающие одноэлементные числовые значения, например <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A> и т.д.  Эти методы всегда должны быть вызваны последними в запросе, поскольку они представляют только одно значение и не могут служить источником дополнительных действий запроса.  В следующем примере демонстрируется вызов метода в выражении запроса.  
  
 [!code-cs[csProgGuideLINQ#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-write-linq-queries_2.cs)]  
  
## Пример  
 Если у метода есть параметры, они представлены в виде [лямбда](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)\-выражения, как показано в следующем примере.  
  
 [!code-cs[csProgGuideLINQ#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-write-linq-queries_3.cs)]  
  
 В предыдущих запросах только запрос №4 выполнялся немедленно.  Причина заключается в том, что он возвращает одиночное значение, а не универсальную коллекцию <xref:System.Collections.Generic.IEnumerable%601>.  Сам метод должен использовать `foreach` для вычисления значения.  
  
 Любой их перечисленных ранее запросов можно написать с использованием неявной типизации с помощью [var](../../../csharp/language-reference/keywords/var.md), как показано в следующем примере.  
  
 [!code-cs[csProgGuideLINQ#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-write-linq-queries_4.cs)]  
  
## Пример  
  
## Смешанный синтаксис запроса и метода  
 В этом примере демонстрируется использование синтаксиса метода для результатов предложения запроса.  Нужно всего лишь заключить выражение запроса в скобки, а затем применить оператор точки и вызвать метод.  В следующем примере запрос \#7 возвращает количество чисел, значение которых лежит в диапазоне от 3 до 7.  Однако в общем случае лучше использовать вторую переменную для хранения результатов вызова метода.  Таким образом, будет меньше вероятность перепутать запрос с результатами запроса.  
  
 [!code-cs[csProgGuideLINQ#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-write-linq-queries_5.cs)]  
  
 Запрос №7 возвращает одиночное значение, а не коллекцию, поэтому он выполняется мгновенно.  
  
 Предыдущий запрос можно написать с использованием неявной типизации с помощью `var`, как показано в следующем примере:  
  
```  
var numCount = (from num in numbers...  
```  
  
 Можно использовать синтаксис метода следующим образом.  
  
```  
var numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
 Можно использовать явную типизацию следующим образом.  
  
```  
int numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
## См. также  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Walkthrough: Writing Queries in C\#](../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)   
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Предложение where](../../../csharp/language-reference/keywords/where-clause.md)