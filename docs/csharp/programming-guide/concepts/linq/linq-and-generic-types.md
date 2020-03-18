---
title: LINQ и универсальные типы (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], generic types
- generic types [LINQ]
- generics [LINQ]
ms.assetid: 660e3799-25ca-462c-8c4a-8bce04fbb031
ms.openlocfilehash: 9a2d1ac72f70e7cd314d349e81ab2bc815a5bf13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635578"
---
# <a name="linq-and-generic-types-c"></a>LINQ и универсальные типы (C#)
Запросы LINQ основаны на универсальных типах, которые впервые появились в .NET Framework 2.0. Для того чтобы приступить к написанию запросов, не требуется глубокое знание универсальных типов. Тем не менее необходимо понимание двух основных принципов.  
  
1. При создании экземпляра универсального класса коллекции, такого как <xref:System.Collections.Generic.List%601>, замените "T" типом объектов, которые будут храниться в списке. Например, список строк выражается как `List<string>`, а список объектов `Customer` — как `List<Customer>`. Универсальный список является строго типизированным и предоставляет ряд преимуществ по сравнению с коллекциями, которые хранят свои элементы как <xref:System.Object>. При попытке добавить `Customer` в `List<string>` будет выдана ошибка во время компиляции. Универсальные коллекции просты в использовании, поскольку нет необходимости выполнять приведение типов во время выполнения.  
  
2. <xref:System.Collections.Generic.IEnumerable%601> — это интерфейс, поддерживающий перечисление универсальных классов коллекций с помощью оператора `foreach`. Универсальные классы коллекций поддерживают <xref:System.Collections.Generic.IEnumerable%601> так же, как неуниверсальные классы коллекций (например <xref:System.Collections.ArrayList>) поддерживают <xref:System.Collections.IEnumerable>.  
  
 Дополнительные сведения об универсальных классах см. в разделе [Универсальные шаблоны](../../generics/index.md).  
  
## <a name="ienumerablet-variables-in-linq-queries"></a>Переменные IEnumerable<T\> в запросах LINQ  
 Переменные запроса LINQ типизированы как <xref:System.Collections.Generic.IEnumerable%601> или производный тип, например <xref:System.Linq.IQueryable%601>. Если появляется переменная запроса, которая типизируется как `IEnumerable<Customer>`, это просто означает, что запрос при выполнении выведет последовательность из нуля или более объектов `Customer`.  
  
 [!code-csharp[csLINQGettingStarted#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#34)]  
  
 Дополнительные сведения см. в разделе [Связи типов в операциях запроса LINQ](./type-relationships-in-linq-query-operations.md).  
  
## <a name="letting-the-compiler-handle-generic-type-declarations"></a>Передача обработки объявлений универсальных типов компилятору  
 При желании можно отказаться от обычного синтаксиса универсальных типов, используя ключевое слово [var](../../../language-reference/keywords/var.md). Ключевое слово `var` дает компилятору указание вывести тип переменной запроса путем поиска в источнике данных, указанном в предложении `from`. В следующем примере создается тот же скомпилированный код, что и в предыдущем примере:  
  
 [!code-csharp[csLINQGettingStarted#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#35)]  
  
 Ключевое слово `var` удобно, если тип переменной является очевидным, или если не требуется явно указывать вложенные универсальные типы, например создаваемые групповыми запросами. Как правило, рекомендуется помнить о том, что использование `var` делает код более сложным для чтения. Дополнительные сведения см. в разделе [Неявно типизированные локальные переменные](../../classes-and-structs/implicitly-typed-local-variables.md).  
  
## <a name="see-also"></a>См. также раздел

- [Универсальные шаблоны](../../generics/index.md)
