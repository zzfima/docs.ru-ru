---
title: "Предложение Aggregate (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.QueryAggregateIn"
  - "vb.QueryAggregate"
  - "vb.QueryAggregateInto"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Aggregate - предложение"
  - "Aggregate - оператор"
  - "запросы [Visual Basic], Статистическое выражение"
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
caps.latest.revision: 25
caps.handback.revision: 25
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Предложение Aggregate (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

К коллекции применяется одна или несколько агрегатных функций.  
  
## Синтаксис  
  
```  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`element`|Обязательный.  Переменная используется для циклического просмотра элементов коллекции.|  
|`type`|Необязательный.  Тип `element`.  Если тип не указан, то тип `element` выводится из `collection`.|  
|`collection`|Обязательный.  Относится к коллекции, с которой выполняются операции.|  
|`clause`|Необязательный.  Одно или несколько предложений запроса, например предложение `Where`, для уточнения результатов запроса, к которым применяется статистическое предложение.|  
|`expressionList`|Обязательный.  Одно или более выражений, разделенных запятыми, которые идентифицируют агрегатную функцию, применяемую к коллекции.  Можно применить псевдоним агрегатной функции, чтобы указать имя члена для результата запроса.  Если псевдоним не указан, используется имя агрегатной функции.  Примеры содержатся в разделе агрегатных функций далее в этом разделе.|  
  
## Заметки  
 Предложение `Aggregate` может использоваться для включения агрегатных функций в запросы.  Агрегатные функции выполняют проверку и вычисление по набору значений и возвращают одиночное значение.  Можно получить доступ к вычисляемым значениям с помощью члена типа результата запроса.  Стандартные агрегатные функции, которые можно использовать: `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min` и `Sum`.  Эти функции знакомы разработчикам, работавшим с агрегатными функциями в SQL.  Они описаны далее в этом разделе.  
  
 Результат агрегатной функции включается в результат запроса в виде поля типа результата запроса.  Можно указать псевдоним для результатов агрегатной функции, чтобы указать имя члена типа результата запроса, который будет содержать значение статистического выражения.  Если псевдоним не указан, используется имя агрегатной функции.  
  
 Предложение `Aggregate` может располагаться в начале запроса или использоваться в нем в качестве дополнительного предложения.  Если предложение `Aggregate` располагается в начале запроса, результатом является одно значение, которое представляет результат агрегатной функции, указанной в предложении `Into`.  Если в предложении `Into` указано несколько агрегатных функций, запрос возвращает отдельный тип с отдельным свойством, ссылающийся на результаты каждой агрегатной функции в предложении `Into`.  Если предложение `Aggregate` включено в запрос как дополнительное предложение, тип возвращаемой коллекции запроса будет иметь отдельные свойства, ссылающиеся на результат каждой агрегатной функции предложения`Into`.  
  
## Агрегатные функции  
 Ниже перечислены стандартные агрегатные функции, которые могут указываться вместе с предложением `Aggregate`.  
  
|||  
|-|-|  
|Функция|Описание|  
|`All`|Возвращает `true`, если все элементы в коллекции удовлетворяют указанному условию. В противном случае возвращает `false`.  Например:<br /><br /> [!code-vb[VbSimpleQuerySamples#5](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_1.vb)]|  
|`Any`|Возвращает `true`, если все элементы в коллекции удовлетворяют указанному условию. В противном случае возвращает `false`.  Например:<br /><br /> [!code-vb[VbSimpleQuerySamples#6](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_2.vb)]|  
|`Average`|Вычисляет среднее значение всех элементов в коллекции или указанное выражение для всех элементов в коллекции.  Например:<br /><br /> [!code-vb[VbSimpleQuerySamples#7](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_3.vb)]|  
|`Count`|Подсчет числа элементов в коллекции.  Можно указать необязательное выражение `Boolean` для подсчета числа только тех элементов в коллекции, которые удовлетворяют условию.  Например:<br /><br /> [!code-vb[VbSimpleQuerySamples#8](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_4.vb)]|  
|`Group`|Ссылается на результаты запроса, которые сгруппированы в результате выполнения предложения `Group By` или `Group Join`.  Функция `Group` допустима только в предложении `Into` предложения `Group By` или предложения `Group Join`.  Дополнительные сведения и примеры см. в разделах [Предложение Group By](../../../visual-basic/language-reference/queries/group-by-clause.md) и [Предложение Group Join](../../../visual-basic/language-reference/queries/group-join-clause.md).|  
|`LongCount`|Подсчет числа элементов в коллекции.  Можно указать необязательное выражение `Boolean` для подсчета числа только тех элементов в коллекции, которые удовлетворяют условию.  Возвращает результат типа `Long`.  Пример см. в разделе "Агрегатная функция `Count`".|  
|`Max`|Вычисляет максимальное значение всех элементов в коллекции или указанное выражение для всех элементов в коллекции.  Например:<br /><br /> [!code-vb[VbSimpleQuerySamples#9](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_5.vb)]|  
|`Min`|Вычисляет минимальное значение всех элементов в коллекции или указанное выражение для всех элементов в коллекции.  Например:<br /><br /> [!code-vb[VbSimpleQuerySamples#10](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_6.vb)]|  
|`Sum`|Вычисляет сумму всех элементов в коллекции или указанное выражение для всех элементов в коллекции.  Например:<br /><br /> [!code-vb[VbSimpleQuerySamples#15](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_7.vb)]|  
  
## Пример  
 В следующем примере показывается использование предложения `Aggregate` для применения агрегатных функций к результатам запроса.  
  
 [!code-vb[VbSimpleQuerySamples#4](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_8.vb)]  
  
## Создание определяемых пользователем агрегатных функций  
 Можно включить пользовательские агрегатные функции в выражение запроса путем добавления методов расширения типа <xref:System.Collections.Generic.IEnumerable%601>.  Пользовательский метод может выполнить расчет или операцию на перечисление коллекции, на которую есть ссылки в агрегатной функции.  Дополнительные сведения о методах расширения см. в разделе [Методы расширения](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
 Например, в следующем примере показана пользовательская агрегатная функция, вычисляющая значение медианы из коллекции чисел.  Существуют две перегрузки метода расширения `Median`.  Первая перегрузка в качестве входных данных принимает коллекцию типа `IEnumerable(Of Double)`.  Если агрегатная функция `Median` вызывается для поля типа `Double`, будет вызван этот метод.  Второй способ перегрузки метода `Median` — это передача в него любого базового типа.  Универсальная перегрузка метода `Median` принимает второй параметр, который ссылается на лямбда\-выражение `Func(Of T, Double)`, чтобы проектировать значения для типа \(из коллекции\), как значение соответствующего типа `Double`.  Затем делегируется расчет значения медианы другой перегрузке метода `Median`.  Дополнительные сведения о лямбда\-выражениях см. в разделе [Лямбда\-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbSimpleQuerySamples#18](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_9.vb)]  
  
 В следующем примере показаны примеры запросов вызова агрегатной функции `Median` для коллекции типа `Integer` и коллекции типа `Double`.  Запрос, который вызывает агрегатную функцию `Median` для коллекции типа `Double`, вызывает перегрузку метода `Median`, который принимает тип `Double` в качестве выходных данных.  Запрос, который вызывает агрегатную функцию `Median` для коллекции типа `Integer`, вызывает универсальную перегрузку метода `Median`.  
  
 [!code-vb[VbSimpleQuerySamples#19](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_10.vb)]  
  
## См. также  
 [Знакомство с LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Запросы](../../../visual-basic/language-reference/queries/queries.md)   
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Предложение Where](../../../visual-basic/language-reference/queries/where-clause.md)   
 [Предложение Group By](../../../visual-basic/language-reference/queries/group-by-clause.md)