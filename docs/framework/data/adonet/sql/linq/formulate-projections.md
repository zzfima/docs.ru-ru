---
title: Формулировка проекций
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: 9b32ee4c7745fda482561311dc116e0e38b49ab7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599158"
---
# <a name="formulate-projections"></a><span data-ttu-id="0fce3-102">Формулировка проекций</span><span class="sxs-lookup"><span data-stu-id="0fce3-102">Formulate Projections</span></span>
<span data-ttu-id="0fce3-103">В следующих примерах показывается как `select` инструкции в C# и `Select` в Visual Basic можно объединить с другими возможностями для создания проекций запросов.</span><span class="sxs-lookup"><span data-stu-id="0fce3-103">The following examples show how the `select` statement in C# and `Select` statement in Visual Basic can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fce3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0fce3-104">Example</span></span>  
 <span data-ttu-id="0fce3-105">В следующем примере используется `Select` предложение в Visual Basic (`select` предложение в C#) для возвращения последовательности контактных имен для `Customers`.</span><span class="sxs-lookup"><span data-stu-id="0fce3-105">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="0fce3-106">Пример</span><span class="sxs-lookup"><span data-stu-id="0fce3-106">Example</span></span>  
 <span data-ttu-id="0fce3-107">В следующем примере используется `Select` предложение в Visual Basic (`select` предложение в C#) и *анонимные типы* для возвращения последовательности контактных имен и телефонных номеров для `Customers`.</span><span class="sxs-lookup"><span data-stu-id="0fce3-107">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="0fce3-108">Пример</span><span class="sxs-lookup"><span data-stu-id="0fce3-108">Example</span></span>  
 <span data-ttu-id="0fce3-109">В следующем примере используется `Select` предложение в Visual Basic (`select` предложение в C#) и *анонимные типы* для возвращения последовательности имен и телефонных номеров для сотрудников.</span><span class="sxs-lookup"><span data-stu-id="0fce3-109">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="0fce3-110">`FirstName` И `LastName` поля объединяются в одно поле (`Name`) и `HomePhone` поле переименовывается в `Phone` в результирующей последовательности.</span><span class="sxs-lookup"><span data-stu-id="0fce3-110">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="0fce3-111">Пример</span><span class="sxs-lookup"><span data-stu-id="0fce3-111">Example</span></span>  
 <span data-ttu-id="0fce3-112">В следующем примере используется `Select` предложение в Visual Basic (`select` предложение в C#) и *анонимные типы* для возвращения последовательности всех `ProductID`s и вычисляемого значения с именем `HalfPrice`.</span><span class="sxs-lookup"><span data-stu-id="0fce3-112">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="0fce3-113">В качестве значения устанавливается `UnitPrice`, разделенная на 2.</span><span class="sxs-lookup"><span data-stu-id="0fce3-113">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="0fce3-114">Пример</span><span class="sxs-lookup"><span data-stu-id="0fce3-114">Example</span></span>  
 <span data-ttu-id="0fce3-115">В следующем примере используется `Select` предложение в Visual Basic (`select` предложение в C#) и *условный оператор* для возвращения последовательности названия продукта и доступности продуктов.</span><span class="sxs-lookup"><span data-stu-id="0fce3-115">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="0fce3-116">Пример</span><span class="sxs-lookup"><span data-stu-id="0fce3-116">Example</span></span>  
 <span data-ttu-id="0fce3-117">В следующем примере используется Visual Basic `Select` предложение (`select` предложение в C#) и *известного типа* (имя) для возвращения последовательности имен сотрудников.</span><span class="sxs-lookup"><span data-stu-id="0fce3-117">The following example uses a Visual Basic `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="0fce3-118">Пример</span><span class="sxs-lookup"><span data-stu-id="0fce3-118">Example</span></span>  
 <span data-ttu-id="0fce3-119">В следующем примере используется `Select` и `Where` в Visual Basic (`select` и `where` в C#) для возврата *отфильтрованной последовательности* контактных имен для клиентов в Лондоне.</span><span class="sxs-lookup"><span data-stu-id="0fce3-119">The following example uses `Select` and `Where` in Visual Basic (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="0fce3-120">Пример</span><span class="sxs-lookup"><span data-stu-id="0fce3-120">Example</span></span>  
 <span data-ttu-id="0fce3-121">В следующем примере используется `Select` предложение в Visual Basic (`select` предложение в C#) и *анонимные типы* для возврата *сформированного подмножества* данных о клиентах.</span><span class="sxs-lookup"><span data-stu-id="0fce3-121">The following example uses a `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="0fce3-122">Пример</span><span class="sxs-lookup"><span data-stu-id="0fce3-122">Example</span></span>  
 <span data-ttu-id="0fce3-123">В следующем примере вложенные запросы используется для возврата следующих результатов.</span><span class="sxs-lookup"><span data-stu-id="0fce3-123">The following example uses nested queries to return the following results:</span></span>  
  
-   <span data-ttu-id="0fce3-124">Последовательность всех заказов и их соответствующие `OrderID`.</span><span class="sxs-lookup"><span data-stu-id="0fce3-124">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
-   <span data-ttu-id="0fce3-125">Последовательность элементов, упорядоченных по наличию скидки.</span><span class="sxs-lookup"><span data-stu-id="0fce3-125">A subsequence of the items in the order for which there is a discount.</span></span>  
  
-   <span data-ttu-id="0fce3-126">Количество сэкономленных средств при отсутствии расходов на доставку.</span><span class="sxs-lookup"><span data-stu-id="0fce3-126">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="0fce3-127">См. также</span><span class="sxs-lookup"><span data-stu-id="0fce3-127">See also</span></span>
- [<span data-ttu-id="0fce3-128">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="0fce3-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
