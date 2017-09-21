---
title: "LINQ и универсальные типы (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- LINQ [C#], generic types
- generic types [LINQ]
- generics [LINQ]
ms.assetid: 660e3799-25ca-462c-8c4a-8bce04fbb031
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 177db64491d58b31ca50cef0bb2eda8c2cb65078
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="linq-and-generic-types-c"></a>LINQ и универсальные типы (C#)
Запросы [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] основаны на универсальных типах, которые впервые появились в версии [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 2.0. Для того чтобы приступить к написанию запросов, не требуется глубокое знание универсальных типов. Тем не менее необходимо понимание двух основных принципов.  
  
1.  При создании экземпляра универсального класса коллекции, такого как <xref:System.Collections.Generic.List%601>, замените "T" типом объектов, которые будут храниться в списке. Например, список строк выражается как `List<string>`, а список объектов `Customer` — как `List<Customer>`. Универсальный список является строго типизированным и предоставляет ряд преимуществ по сравнению с коллекциями, которые хранят свои элементы как <xref:System.Object>. При попытке добавить `Customer` в `List<string>` будет выдана ошибка во время компиляции. Универсальные коллекции просты в использовании, поскольку нет необходимости выполнять приведение типов во время выполнения.  
  
2.  <xref:System.Collections.Generic.IEnumerable%601> — это интерфейс, поддерживающий перечисление универсальных классов коллекций с помощью оператора `foreach`. Универсальные классы коллекций поддерживают <xref:System.Collections.Generic.IEnumerable%601> так же, как неуниверсальные классы коллекций (например <xref:System.Collections.ArrayList>) поддерживают <xref:System.Collections.IEnumerable>.  
  
 Дополнительные сведения об универсальных классах см. в разделе [Универсальные шаблоны](../../../../csharp/programming-guide/generics/index.md).  
  
## <a name="ienumerablet-variables-in-linq-queries"></a>Переменные IEnumerable<T\> в запросах LINQ  
 Переменные запроса [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] типизированы как <xref:System.Collections.Generic.IEnumerable%601> или производный тип, например <xref:System.Linq.IQueryable%601>. Если появляется переменная запроса, которая типизируется как `IEnumerable<Customer>`, это просто означает, что запрос при выполнении выведет последовательность из нуля или более объектов `Customer`.  
  
 [!code-cs[csLINQGettingStarted#34](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_1.cs)]  
  
 Дополнительные сведения см. в разделе [Связи типов в операциях запроса LINQ](../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
## <a name="letting-the-compiler-handle-generic-type-declarations"></a>Передача обработки объявлений универсальных типов компилятору  
 При желании можно отказаться от обычного синтаксиса универсальных типов, используя ключевое слово [var](../../../../csharp/language-reference/keywords/var.md). Ключевое слово `var` дает компилятору указание вывести тип переменной запроса путем поиска в источнике данных, указанном в предложении `from`. В следующем примере создается тот же скомпилированный код, что и в предыдущем примере:  
  
 [!code-cs[csLINQGettingStarted#35](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_2.cs)]  
  
 Ключевое слово `var` удобно, если тип переменной является очевидным, или если не требуется явно указывать вложенные универсальные типы, например создаваемые групповыми запросами. Как правило, рекомендуется помнить о том, что использование `var` делает код более сложным для чтения. Дополнительные сведения см. в разделе [Неявно типизированные локальные переменные](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
## <a name="see-also"></a>См. также  
 [Приступая к работе с LINQ в C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Универсальные шаблоны](../../../../csharp/programming-guide/generics/index.md)

