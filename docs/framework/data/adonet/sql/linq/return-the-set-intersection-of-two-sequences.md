---
title: "Возврат пересечения наборов двух последовательностей."
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
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: dea534ef48b1b37d2f603e9c02d015ab1abe9dac
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="33b75-102">Возврат пересечения наборов двух последовательностей.</span><span class="sxs-lookup"><span data-stu-id="33b75-102">Return the Set Intersection of Two Sequences</span></span>
<span data-ttu-id="33b75-103">Для возвращения пересечения наборов двух последовательностей используется оператор <xref:System.Linq.Queryable.Intersect%2A>.</span><span class="sxs-lookup"><span data-stu-id="33b75-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33b75-104">Пример</span><span class="sxs-lookup"><span data-stu-id="33b75-104">Example</span></span>  
 <span data-ttu-id="33b75-105">В данном примере для возвращения последовательности всех стран, где живут как сотрудники (<xref:System.Linq.Queryable.Intersect%2A>), так и клиенты (`Customers`), используется оператор `Employees`.</span><span class="sxs-lookup"><span data-stu-id="33b75-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="33b75-106">В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] оператор <xref:System.Linq.Queryable.Intersect%2A> правильно определен только в наборах.</span><span class="sxs-lookup"><span data-stu-id="33b75-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="33b75-107">Семантика для мультинаборов не определена.</span><span class="sxs-lookup"><span data-stu-id="33b75-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b75-108">См. также</span><span class="sxs-lookup"><span data-stu-id="33b75-108">See Also</span></span>  
 [<span data-ttu-id="33b75-109">Примеры запросов</span><span class="sxs-lookup"><span data-stu-id="33b75-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="33b75-110">Преобразование стандартных операторов запросов</span><span class="sxs-lookup"><span data-stu-id="33b75-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
