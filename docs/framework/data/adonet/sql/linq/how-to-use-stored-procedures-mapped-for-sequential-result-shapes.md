---
title: Практическое руководство. Использование хранимых процедур, сопоставленных для последовательных форм результатов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
ms.openlocfilehash: 8378a175ab2479ab9769ca08579e1c89269eaba4
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003218"
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a><span data-ttu-id="90243-102">Практическое руководство. Использование хранимых процедур, сопоставленных для последовательных форм результатов</span><span class="sxs-lookup"><span data-stu-id="90243-102">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>
<span data-ttu-id="90243-103">Этот тип хранимых процедур может создавать несколько результирующих форм, но всегда известно, в каком порядке возвращаются результаты.</span><span class="sxs-lookup"><span data-stu-id="90243-103">This kind of stored procedure can generate more than one result shape, but you know in what order the results are returned.</span></span> <span data-ttu-id="90243-104">Этот сценарий противоположен сценарию, в котором порядок возвращения результатов не известен.</span><span class="sxs-lookup"><span data-stu-id="90243-104">Contrast this scenario with the scenario where you do not know the sequence of the returns.</span></span> <span data-ttu-id="90243-105">Дополнительные сведения см. [в разделе инструкции. Использование хранимых процедур, сопоставленных с несколькими результирующими формами](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="90243-105">For more information, see [How to: Use Stored Procedures Mapped for Multiple Result Shapes](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="90243-106">Пример</span><span class="sxs-lookup"><span data-stu-id="90243-106">Example</span></span>  
 <span data-ttu-id="90243-107">Ниже представлен код T-SQL для хранимой процедуры, которая последовательно возвращает несколько результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="90243-107">Here is the T-SQL of a stored procedure that returns multiple result shapes sequentially:</span></span>  
  
```sql
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="90243-108">Пример</span><span class="sxs-lookup"><span data-stu-id="90243-108">Example</span></span>  
 <span data-ttu-id="90243-109">Для выполнения этой хранимой процедуры следует использовать код, который выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="90243-109">You would use code similar to the following to execute this stored procedure.</span></span>  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="90243-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="90243-110">See also</span></span>

- [<span data-ttu-id="90243-111">Хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="90243-111">Stored Procedures</span></span>](stored-procedures.md)
