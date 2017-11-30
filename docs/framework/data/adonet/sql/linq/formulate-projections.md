---
title: "Формулировка проекций"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8afd48c6ce7c6313e82a7b74c2271f52833d1f5e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="formulate-projections"></a><span data-ttu-id="833f5-102">Формулировка проекций</span><span class="sxs-lookup"><span data-stu-id="833f5-102">Formulate Projections</span></span>
<span data-ttu-id="833f5-103">В следующем примере показано сочетание оператора `select` в C# и оператора `Select` в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] с другими возможностями для создания проекций запросов.</span><span class="sxs-lookup"><span data-stu-id="833f5-103">The following examples show how the `select` statement in C# and `Select` statement in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="833f5-104">Пример</span><span class="sxs-lookup"><span data-stu-id="833f5-104">Example</span></span>  
 <span data-ttu-id="833f5-105">В следующем примере используется `Select` предложения в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` предложение в C#) для возвращения последовательности контактных имен для `Customers`.</span><span class="sxs-lookup"><span data-stu-id="833f5-105">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="833f5-106">Пример</span><span class="sxs-lookup"><span data-stu-id="833f5-106">Example</span></span>  
 <span data-ttu-id="833f5-107">В следующем примере используется `Select` предложения в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` предложение в C#) и *анонимные типы* для возвращения последовательности контактных имен и телефонных номеров для `Customers`.</span><span class="sxs-lookup"><span data-stu-id="833f5-107">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="833f5-108">Пример</span><span class="sxs-lookup"><span data-stu-id="833f5-108">Example</span></span>  
 <span data-ttu-id="833f5-109">В следующем примере используется `Select` предложения в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` предложение в C#) и *анонимные типы* для возвращения последовательности имен и телефонных номеров для сотрудников.</span><span class="sxs-lookup"><span data-stu-id="833f5-109">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="833f5-110">`FirstName` И `LastName` поля объединяются в одно поле (`Name`) и `HomePhone` присваивается имя `Phone` в результирующей последовательности.</span><span class="sxs-lookup"><span data-stu-id="833f5-110">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="833f5-111">Пример</span><span class="sxs-lookup"><span data-stu-id="833f5-111">Example</span></span>  
 <span data-ttu-id="833f5-112">В следующем примере используется `Select` предложения в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` предложение в C#) и *анонимные типы* для возвращения последовательности всех `ProductID`и вычисляемого значения с именем `HalfPrice`.</span><span class="sxs-lookup"><span data-stu-id="833f5-112">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="833f5-113">В качестве значения устанавливается `UnitPrice`, разделенная на 2.</span><span class="sxs-lookup"><span data-stu-id="833f5-113">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="833f5-114">Пример</span><span class="sxs-lookup"><span data-stu-id="833f5-114">Example</span></span>  
 <span data-ttu-id="833f5-115">В следующем примере используется `Select` предложения в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` предложение в C#) и *условного оператора* для возвращения последовательности названия продукта и доступности продуктов.</span><span class="sxs-lookup"><span data-stu-id="833f5-115">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="833f5-116">Пример</span><span class="sxs-lookup"><span data-stu-id="833f5-116">Example</span></span>  
 <span data-ttu-id="833f5-117">В следующем примере используется [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `Select` предложение (`select` предложение в C#) и *известного типа* (имя) для возвращения последовательности имен сотрудников.</span><span class="sxs-lookup"><span data-stu-id="833f5-117">The following example uses a [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="833f5-118">Пример</span><span class="sxs-lookup"><span data-stu-id="833f5-118">Example</span></span>  
 <span data-ttu-id="833f5-119">В следующем примере используется `Select` и `Where` в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` и `where` в C#) для возврата *отфильтрованной последовательности* контактных имен для клиентов из Лондона.</span><span class="sxs-lookup"><span data-stu-id="833f5-119">The following example uses `Select` and `Where` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="833f5-120">Пример</span><span class="sxs-lookup"><span data-stu-id="833f5-120">Example</span></span>  
 <span data-ttu-id="833f5-121">В следующем примере используется `Select` предложения в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` предложение в C#) и *анонимные типы* для возврата *сформированного подмножества* данных о клиентах.</span><span class="sxs-lookup"><span data-stu-id="833f5-121">The following example uses a `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="833f5-122">Пример</span><span class="sxs-lookup"><span data-stu-id="833f5-122">Example</span></span>  
 <span data-ttu-id="833f5-123">В следующем примере вложенные запросы используется для возврата следующих результатов.</span><span class="sxs-lookup"><span data-stu-id="833f5-123">The following example uses nested queries to return the following results:</span></span>  
  
-   <span data-ttu-id="833f5-124">Последовательность всех заказов и их соответствующие `OrderID`.</span><span class="sxs-lookup"><span data-stu-id="833f5-124">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
-   <span data-ttu-id="833f5-125">Последовательность элементов, упорядоченных по наличию скидки.</span><span class="sxs-lookup"><span data-stu-id="833f5-125">A subsequence of the items in the order for which there is a discount.</span></span>  
  
-   <span data-ttu-id="833f5-126">Количество сэкономленных средств при отсутствии расходов на доставку.</span><span class="sxs-lookup"><span data-stu-id="833f5-126">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="833f5-127">См. также</span><span class="sxs-lookup"><span data-stu-id="833f5-127">See Also</span></span>  
 [<span data-ttu-id="833f5-128">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="833f5-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
