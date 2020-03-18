---
title: Соединение с помощью составных ключей (LINQ в C#)
description: Узнайте, как выполнять соединение с помощью составных ключей в LINQ.
ms.date: 12/01/2016
ms.assetid: da70b54d-3213-45eb-8437-fbe75cbcf935
ms.openlocfilehash: 460a52da7e0c0a47b77d4c64e76641bae9da7cd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659882"
---
# <a name="join-by-using-composite-keys"></a>Соединение с помощью составных ключей

В этом примере показано, как выполнить операции соединения, в которых требуется использовать более одного ключа для определения соответствия. Для этих целей используется составной ключ. Составной ключ создается как анонимный тип или именованный тип со значениями, которые нужно сравнить. Если переменная запроса будет передаваться за пределы метода, необходимо использовать именованный тип, который переопределяет <xref:System.Object.Equals%2A> и <xref:System.Object.GetHashCode%2A> для ключа. Имена свойств и порядок, в котором они возникают, должны совпадать в каждом ключе.

## <a name="example"></a>Пример

В следующем примере демонстрируется использование составного ключа для объединения данных из трех таблиц:

```csharp
var query = from o in db.Orders
    from p in db.Products
    join d in db.OrderDetails
        on new {o.OrderID, p.ProductID} equals new {d.OrderID, d.ProductID} into details
        from d in details
        select new {o.OrderID, p.ProductID, d.UnitPrice};
```

Определение типа в составных ключах зависит от имен свойств в ключах и порядка, в котором они возникают. Если свойства в исходных последовательностях имеют другие имена, в ключах им необходимо присвоить новые имена. Например, если в таблицах `Orders` и `OrderDetails` используются разные имена столбцов, можно создать составные ключи, назначив одинаковые имена в анонимных типах:

```csharp
join...on new {Name = o.CustomerName, ID = o.CustID} equals
    new {Name = d.CustName, ID = d.CustID }
```

Составные ключи можно также использовать в предложении `group`.

## <a name="see-also"></a>См. также раздел

- [LINQ](index.md)
- [предложение join](../language-reference/keywords/join-clause.md)
- [предложение group](../language-reference/keywords/group-clause.md)
