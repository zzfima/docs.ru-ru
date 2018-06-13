---
title: Практическое руководство. Использование хранимых процедур, сопоставленных для последовательных форм результатов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
ms.openlocfilehash: ade123f10e1c9ffd6d042b45599cc6e352614e5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351944"
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a><span data-ttu-id="f5bf2-102">Практическое руководство. Использование хранимых процедур, сопоставленных для последовательных форм результатов</span><span class="sxs-lookup"><span data-stu-id="f5bf2-102">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>
<span data-ttu-id="f5bf2-103">Этот тип хранимых процедур может создавать несколько результирующих форм, но всегда известно, в каком порядке возвращаются результаты.</span><span class="sxs-lookup"><span data-stu-id="f5bf2-103">This kind of stored procedure can generate more than one result shape, but you know in what order the results are returned.</span></span> <span data-ttu-id="f5bf2-104">Этот сценарий противоположен сценарию, в котором порядок возвращения результатов не известен.</span><span class="sxs-lookup"><span data-stu-id="f5bf2-104">Contrast this scenario with the scenario where you do not know the sequence of the returns.</span></span> <span data-ttu-id="f5bf2-105">Дополнительные сведения см. в разделе [как: используйте хранимые процедуры, сопоставленные с несколькими формами результатов](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="f5bf2-105">For more information, see [How to: Use Stored Procedures Mapped for Multiple Result Shapes](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5bf2-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f5bf2-106">Example</span></span>  
 <span data-ttu-id="f5bf2-107">Ниже представлен код T-SQL для хранимой процедуры, которая последовательно возвращает несколько результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="f5bf2-107">Here is the T-SQL of a stored procedure that returns multiple result shapes sequentially:</span></span>  
  
```  
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="f5bf2-108">Пример</span><span class="sxs-lookup"><span data-stu-id="f5bf2-108">Example</span></span>  
 <span data-ttu-id="f5bf2-109">Для выполнения этой хранимой процедуры следует использовать код, который выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f5bf2-109">You would use code similar to the following to execute this stored procedure.</span></span>  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="f5bf2-110">См. также</span><span class="sxs-lookup"><span data-stu-id="f5bf2-110">See Also</span></span>  
 [<span data-ttu-id="f5bf2-111">Хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="f5bf2-111">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
