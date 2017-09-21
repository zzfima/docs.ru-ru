---
title: "Предложение from (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- from_CSharpKeyword
- from
dev_langs:
- CSharp
helpviewer_keywords:
- from clause [C#]
- from keyword [C#]
ms.assetid: 1aefd18c-1314-47f8-99ec-9bcefb09e699
caps.latest.revision: 27
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f0165144acfa8d0928015e8222179f7e69f19644
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="from-clause-c-reference"></a>Предложение from (справочник по C#)
Выражение запроса должно начинаться с предложения `from`. Кроме того, выражение запроса может содержать вложенные запросы, которые также начинаются с предложения `from`. Предложение `from` определяет следующее:  
  
-   Источник данных, в отношении которого будет выполнен запрос или вложенный запрос.  
  
-   Локальная *переменная диапазона*, которая представляет каждый элемент в последовательности источника.  
  
 Переменная диапазона и источник данных строго типизированы. Источник данных, на который ссылается предложение `from`, должен иметь тип <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601> или производный от них тип, например <xref:System.Linq.IQueryable%601>.  
  
 В следующем примере `numbers` — это источник данных, а `num` — переменная диапазона. Обратите внимание, что обе переменные строго типизированы, даже несмотря на использование ключевого слова [var](../../../csharp/language-reference/keywords/var.md).  
  
 [!code-cs[cscsrefQueryKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_1.cs)]  
  
## <a name="the-range-variable"></a>Переменная диапазона  
 Компилятор выводит тип переменной диапазона, если источник данных реализует <xref:System.Collections.Generic.IEnumerable%601>. Например, если источник данных имеет тип `IEnumerable<Customer>`, выводится переменная диапазона `Customer`. Явно задавать тип необходимо только в том случае, если источник имеет не являющийся универсальным тип `IEnumerable`, например <xref:System.Collections.ArrayList>. Дополнительные сведения см. в разделе [Практическое руководство. Выполнение запроса к ArrayList с помощью LINQ](http://msdn.microsoft.com/library/c318b79a-fa4d-4de3-b62d-c1162beb267e).  
  
 В предыдущем примере `num` выводится к типу `int`. Поскольку переменная диапазона строго типизирована, вы можете использовать ее в вызовах методов и других операциях. Например, вместо кода `select num` можно использовать запись `select num.ToString()`, в результате чего выражение запроса будет возвращать последовательность строк вместо целых чисел. Также можно использовать запись `select n + 10`, в результате чего выражение будет возвращать последовательность 14, 11, 13, 12, 10. Дополнительные сведения см. в разделе [Предложение select](../../../csharp/language-reference/keywords/select-clause.md).  
  
 Переменные диапазона схожи с переменными итерации в инструкции [foreach](../../../csharp/language-reference/keywords/foreach-in.md), за исключением одного важного отличия: в переменной диапазона никогда не хранятся фактические данные из источника. Это лишь способ оптимизировать код, позволяющий запросу описывать действия, которые произойдут при выполнении запроса. Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
## <a name="compound-from-clauses"></a>Составные предложения from  
 В некоторых случаях каждый элемент в последовательности источника может сам представлять собой последовательность или содержать ее. Например, в качестве источника данных может выступать `IEnumerable<Student>`, в котором каждый объект учащегося представляет собой последовательность, содержащую список полученных оценок. Для доступа к внутреннему списку каждого элемента `Student` можно использовать составные предложения `from`. Этот способ аналогичен использованию вложенных предложений [foreach](../../../csharp/language-reference/keywords/foreach-in.md). Для фильтрации результатов можно добавить предложения [where](../../../csharp/language-reference/keywords/partial-method.md) или [orderby](../../../csharp/language-reference/keywords/orderby-clause.md) в любое из предложений `from`. В следующем примере показана последовательность объектов `Student`, каждый из которых содержит внутренний список `List` с целыми числами, соответствующими оценкам. Для доступа к внутреннему списку следует использовать предложение `from`. При необходимости вы можете вставлять предложения между двумя предложениями `from`.  
  
 [!code-cs[cscsrefQueryKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_2.cs)]  
  
## <a name="using-multiple-from-clauses-to-perform-joins"></a>Использование нескольких предложений from для выполнения соединений  
 Составное предложение `from` используется для доступа к внутренним коллекциям в одном источнике данных. Тем не менее запрос может содержать несколько предложений `from`, которые создают дополнительные запросы из независимых источников данных. Такой способ позволяет выполнять определенные типы операций соединения, которые нельзя выполнить с помощью [предложения join](../../../csharp/language-reference/keywords/join-clause.md).  
  
 В следующем примере показано, как можно выполнить полное перекрестное соединение двух источников данных с помощью двух предложений `from`.  
  
 [!code-cs[cscsrefQueryKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_3.cs)]  
  
 Дополнительные сведения об операциях соединения, использующих несколько предложений `from`, см. в разделе [Практическое руководство. Выполнение пользовательских операций соединения](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md).  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова запроса (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)

