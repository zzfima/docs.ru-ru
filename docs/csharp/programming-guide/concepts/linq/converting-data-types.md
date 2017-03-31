---
title: "Преобразование типов данных (C#) | Документы Майкрософт"
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
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 922e2f26c5f8ded260644e8effa043b03b721020
ms.lasthandoff: 03/13/2017

---
# <a name="converting-data-types-c"></a>Преобразование типов данных (C#)
Методы преобразования изменяют тип входных объектов.  
  
 Операции преобразования в запросах LINQ удобны в различных ситуациях. Ниже приводятся некоторые примеры.  
  
-   Метод <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName> можно использовать для скрытия пользовательской реализации типа стандартного оператора запроса.  
  
-   Метод <xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName> можно использовать для включения непараметризованных коллекций для запросов LINQ.  
  
-   Методы <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> и <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> можно использовать для принудительного немедленного выполнения запроса, не откладывая его до перечисления запроса.  
  
## <a name="methods"></a>Методы  
 В следующей таблице перечислены методы стандартных операторов запросов, выполняющие преобразование типов данных.  
  
 Методы преобразования в этой таблице, имена которых начинаются с "As", изменяют статический тип исходной коллекции, но не выполняют перечисление. Методы, имена которых начинаются с "To", перечисляют исходную коллекцию и помещают элементы в соответствующий тип коллекции.  
  
|Имя метода|Описание|Синтаксис выражения запроса C#|Дополнительные сведения|  
|-----------------|-----------------|---------------------------------|----------------------|  
|AsEnumerable|Возвращает входные данные, типизированные как <xref:System.Collections.Generic.IEnumerable%601>.|Неприменимо.|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>|  
|AsQueryable|Преобразует (универсальный) тип <xref:System.Collections.IEnumerable> в (универсальный) тип <xref:System.Linq.IQueryable>.|Неприменимо.|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName>|  
|Cast|Приводит элементы коллекции к указанному типу.|Используйте явно типизированную переменную диапазона. Например:<br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName>|  
|OfType|Фильтрует значения в зависимости от возможности их приведения к указанному типу.|Неприменимо.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName>|  
|ToArray|Преобразует коллекцию в массив. Этот метод принудительно выполняет запрос.|Неприменимо.|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>|  
|ToDictionary|Помещает элементы в <xref:System.Collections.Generic.Dictionary%602> в зависимости от функции выбора ключа. Этот метод принудительно выполняет запрос.|Неприменимо.|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>|  
|ToList|Преобразует коллекцию в <xref:System.Collections.Generic.List%601>. Этот метод принудительно выполняет запрос.|Неприменимо.|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>|  
|ToLookup|Помещает элементы в <xref:System.Linq.Lookup%602> (словарь "один ко многим") в зависимости от функции выбора ключа. Этот метод принудительно выполняет запрос.|Неприменимо.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a>Пример синтаксиса выражения запроса  
 В следующем примере кода явным образом типизированная переменная диапазона используется для приведения типа к подтипу перед доступом к члену, доступному только для подтипа.  
  
```csharp  
class Plant  
{  
    public string Name { get; set; }  
}  
  
class CarnivorousPlant : Plant  
{  
    public string TrapType { get; set; }  
}  
  
static void Cast()  
{  
    Plant[] plants = new Plant[] {  
        new CarnivorousPlant { Name = "Venus Fly Trap", TrapType = "Snap Trap" },  
        new CarnivorousPlant { Name = "Pitcher Plant", TrapType = "Pitfall Trap" },  
        new CarnivorousPlant { Name = "Sundew", TrapType = "Flypaper Trap" },  
        new CarnivorousPlant { Name = "Waterwheel Plant", TrapType = "Snap Trap" }  
    };  
  
    var query = from CarnivorousPlant cPlant in plants  
                where cPlant.TrapType == "Snap Trap"  
                select cPlant;  
  
    foreach (Plant plant in query)  
        Console.WriteLine(plant.Name);  
  
    /* This code produces the following output:  
  
        Venus Fly Trap  
        Waterwheel Plant  
    */  
}  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq>   
 [Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Предложение From](../../../../csharp/language-reference/keywords/from-clause.md)   
 [Выражения запросов LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Практическое руководство. Выполнение запроса к ArrayList с помощью LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
