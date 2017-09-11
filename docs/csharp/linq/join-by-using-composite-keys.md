---
title: "Соединение с помощью составных ключей"
description: "Практическое руководство по соединению с помощью составных ключей."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: da70b54d-3213-45eb-8437-fbe75cbcf935
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e3e860729ca9267d29ba105ac03ebe22a70b1762
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="join-by-using-composite-keys"></a><span data-ttu-id="a24f8-104">Соединение с помощью составных ключей</span><span class="sxs-lookup"><span data-stu-id="a24f8-104">Join by using composite keys</span></span>

<span data-ttu-id="a24f8-105">В этом примере показано, как выполнить операции соединения, в которых требуется использовать более одного ключа для определения соответствия.</span><span class="sxs-lookup"><span data-stu-id="a24f8-105">This example shows how to perform join operations in which you want to use more than one key to define a match.</span></span> <span data-ttu-id="a24f8-106">Для этих целей используется составной ключ.</span><span class="sxs-lookup"><span data-stu-id="a24f8-106">This is accomplished by using a composite key.</span></span> <span data-ttu-id="a24f8-107">Составной ключ создается как анонимный тип или именованный тип со значениями, которые нужно сравнить.</span><span class="sxs-lookup"><span data-stu-id="a24f8-107">You create a composite key as an anonymous type or named typed with the values that you want to compare.</span></span> <span data-ttu-id="a24f8-108">Если переменная запроса будет передаваться за пределы метода, необходимо использовать именованный тип, который переопределяет <xref:System.Object.Equals%2A> и <xref:System.Object.GetHashCode%2A> для ключа.</span><span class="sxs-lookup"><span data-stu-id="a24f8-108">If the query variable will be passed across method boundaries, use a named type that overrides <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> for the key.</span></span> <span data-ttu-id="a24f8-109">Имена свойств и порядок, в котором они возникают, должны совпадать в каждом ключе.</span><span class="sxs-lookup"><span data-stu-id="a24f8-109">The names of the properties, and the order in which they occur, must be identical in each key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a24f8-110">Пример</span><span class="sxs-lookup"><span data-stu-id="a24f8-110">Example</span></span>  
 <span data-ttu-id="a24f8-111">В следующем примере демонстрируется использование составного ключа для объединения данных из трех таблиц:</span><span class="sxs-lookup"><span data-stu-id="a24f8-111">The following example demonstrates how to use a composite key to join data from three tables:</span></span>  
  
```csharp  
var query = from o in db.Orders  
    from p in db.Products  
    join d in db.OrderDetails   
        on new {o.OrderID, p.ProductID} equals new {d.OrderID,        d.ProductID} into details  
        from d in details  
        select new {o.OrderID, p.ProductID, d.UnitPrice};  
```  
  
 <span data-ttu-id="a24f8-112">Определение типа в составных ключах зависит от имен свойств в ключах и порядка, в котором они возникают.</span><span class="sxs-lookup"><span data-stu-id="a24f8-112">Type inference on composite keys depends on the names of the properties in the keys, and the order in which they occur.</span></span> <span data-ttu-id="a24f8-113">Если свойства в исходных последовательностях имеют другие имена, в ключах им необходимо присвоить новые имена.</span><span class="sxs-lookup"><span data-stu-id="a24f8-113">If the properties in the source sequences do not have the same names, you must assign new names in the keys.</span></span> <span data-ttu-id="a24f8-114">Например, если в таблицах `Orders` и `OrderDetails` используются разные имена столбцов, можно создать составные ключи, назначив одинаковые имена в анонимных типах:</span><span class="sxs-lookup"><span data-stu-id="a24f8-114">For example, if the `Orders` table and `OrderDetails` table each used different names for their columns, you could create composite keys by assigning identical names in the anonymous types:</span></span>  
  
```csharp  
join...on new {Name = o.CustomerName, ID = o.CustID} equals   
    new {Name = d.CustName, ID = d.CustID }  
```  
  
 <span data-ttu-id="a24f8-115">Составные ключи можно также использовать в предложении `group`.</span><span class="sxs-lookup"><span data-stu-id="a24f8-115">Composite keys can be also used in a `group` clause.</span></span>  

## <a name="see-also"></a><span data-ttu-id="a24f8-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a24f8-116">See also</span></span>  
 <span data-ttu-id="a24f8-117">[Выражения запросов LINQ](index.md) </span><span class="sxs-lookup"><span data-stu-id="a24f8-117">[LINQ query expressions](index.md) </span></span>  
 <span data-ttu-id="a24f8-118">[Предложение Join](../language-reference/keywords/join-clause.md) </span><span class="sxs-lookup"><span data-stu-id="a24f8-118">[join clause](../language-reference/keywords/join-clause.md) </span></span>  
 [<span data-ttu-id="a24f8-119">предложение group</span><span class="sxs-lookup"><span data-stu-id="a24f8-119">group clause</span></span>](../language-reference/keywords/group-clause.md)

