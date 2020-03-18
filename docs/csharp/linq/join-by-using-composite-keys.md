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
# <a name="join-by-using-composite-keys"></a><span data-ttu-id="e0663-103">Соединение с помощью составных ключей</span><span class="sxs-lookup"><span data-stu-id="e0663-103">Join by using composite keys</span></span>

<span data-ttu-id="e0663-104">В этом примере показано, как выполнить операции соединения, в которых требуется использовать более одного ключа для определения соответствия.</span><span class="sxs-lookup"><span data-stu-id="e0663-104">This example shows how to perform join operations in which you want to use more than one key to define a match.</span></span> <span data-ttu-id="e0663-105">Для этих целей используется составной ключ.</span><span class="sxs-lookup"><span data-stu-id="e0663-105">This is accomplished by using a composite key.</span></span> <span data-ttu-id="e0663-106">Составной ключ создается как анонимный тип или именованный тип со значениями, которые нужно сравнить.</span><span class="sxs-lookup"><span data-stu-id="e0663-106">You create a composite key as an anonymous type or named typed with the values that you want to compare.</span></span> <span data-ttu-id="e0663-107">Если переменная запроса будет передаваться за пределы метода, необходимо использовать именованный тип, который переопределяет <xref:System.Object.Equals%2A> и <xref:System.Object.GetHashCode%2A> для ключа.</span><span class="sxs-lookup"><span data-stu-id="e0663-107">If the query variable will be passed across method boundaries, use a named type that overrides <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> for the key.</span></span> <span data-ttu-id="e0663-108">Имена свойств и порядок, в котором они возникают, должны совпадать в каждом ключе.</span><span class="sxs-lookup"><span data-stu-id="e0663-108">The names of the properties, and the order in which they occur, must be identical in each key.</span></span>

## <a name="example"></a><span data-ttu-id="e0663-109">Пример</span><span class="sxs-lookup"><span data-stu-id="e0663-109">Example</span></span>

<span data-ttu-id="e0663-110">В следующем примере демонстрируется использование составного ключа для объединения данных из трех таблиц:</span><span class="sxs-lookup"><span data-stu-id="e0663-110">The following example demonstrates how to use a composite key to join data from three tables:</span></span>

```csharp
var query = from o in db.Orders
    from p in db.Products
    join d in db.OrderDetails
        on new {o.OrderID, p.ProductID} equals new {d.OrderID, d.ProductID} into details
        from d in details
        select new {o.OrderID, p.ProductID, d.UnitPrice};
```

<span data-ttu-id="e0663-111">Определение типа в составных ключах зависит от имен свойств в ключах и порядка, в котором они возникают.</span><span class="sxs-lookup"><span data-stu-id="e0663-111">Type inference on composite keys depends on the names of the properties in the keys, and the order in which they occur.</span></span> <span data-ttu-id="e0663-112">Если свойства в исходных последовательностях имеют другие имена, в ключах им необходимо присвоить новые имена.</span><span class="sxs-lookup"><span data-stu-id="e0663-112">If the properties in the source sequences don't have the same names, you must assign new names in the keys.</span></span> <span data-ttu-id="e0663-113">Например, если в таблицах `Orders` и `OrderDetails` используются разные имена столбцов, можно создать составные ключи, назначив одинаковые имена в анонимных типах:</span><span class="sxs-lookup"><span data-stu-id="e0663-113">For example, if the `Orders` table and `OrderDetails` table each used different names for their columns, you could create composite keys by assigning identical names in the anonymous types:</span></span>

```csharp
join...on new {Name = o.CustomerName, ID = o.CustID} equals
    new {Name = d.CustName, ID = d.CustID }
```

<span data-ttu-id="e0663-114">Составные ключи можно также использовать в предложении `group`.</span><span class="sxs-lookup"><span data-stu-id="e0663-114">Composite keys can be also used in a `group` clause.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0663-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e0663-115">See also</span></span>

- [<span data-ttu-id="e0663-116">LINQ</span><span class="sxs-lookup"><span data-stu-id="e0663-116">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="e0663-117">предложение join</span><span class="sxs-lookup"><span data-stu-id="e0663-117">join clause</span></span>](../language-reference/keywords/join-clause.md)
- [<span data-ttu-id="e0663-118">предложение group</span><span class="sxs-lookup"><span data-stu-id="e0663-118">group clause</span></span>](../language-reference/keywords/group-clause.md)
