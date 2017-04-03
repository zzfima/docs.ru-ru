---
title: "Соединение с помощью составных ключей"
description: "Практическое руководство по соединению с помощью составных ключей."
keywords: .NET, .NET Core, C#
author: stevehoag
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: da70b54d-3213-45eb-8437-fbe75cbcf935
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f504c9dabcd7ca2d198d58c6d81e1fde1052e3be
ms.lasthandoff: 03/13/2017

---
# <a name="join-by-using-composite-keys"></a>Соединение с помощью составных ключей

В этом примере показано, как выполнить операции соединения, в которых требуется использовать более одного ключа для определения соответствия. Для этих целей используется составной ключ. Составной ключ создается как анонимный тип или именованный тип со значениями, которые нужно сравнить. Если переменная запроса будет передана за пределы границ метода, используйте именованный тип, переопределяющий <xref:System.Object.Equals%2A> и <xref:System.Object.GetHashCode%2A> для ключа. Имена свойств и порядок, в котором они возникают, должны совпадать в каждом ключе.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется использование составного ключа для объединения данных из трех таблиц:  
  
```csharp  
var query = from o in db.Orders  
    from p in db.Products  
    join d in db.OrderDetails   
        on new {o.OrderID, p.ProductID} equals new {d.OrderID,        d.ProductID} into details  
        from d in details  
        select new {o.OrderID, p.ProductID, d.UnitPrice};  
```  
  
 Определение типа в составных ключах зависит от имен свойств в ключах и порядка, в котором они возникают. Если свойства в исходных последовательностях имеют другие имена, в ключах им необходимо присвоить новые имена. Например, если в таблицах `Orders` и `OrderDetails` используются разные имена столбцов, можно создать составные ключи, назначив одинаковые имена в анонимных типах:  
  
```csharp  
join...on new {Name = o.CustomerName, ID = o.CustID} equals   
    new {Name = d.CustName, ID = d.CustID }  
```  
  
 Составные ключи можно также использовать в предложении `group`.  

## <a name="see-also"></a>См. также  
 [Выражения запросов LINQ](index.md)   
 [Предложение Join](../language-reference/keywords/join-clause.md)   
 [предложение group](../language-reference/keywords/group-clause.md)
