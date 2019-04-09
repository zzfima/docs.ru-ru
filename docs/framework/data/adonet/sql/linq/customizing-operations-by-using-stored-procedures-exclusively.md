---
title: Настройка операций за счет исключительного использования хранимых процедур
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 61230ffc5cd055ee64de9d519cdfb4d76c856ca3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128652"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a><span data-ttu-id="15d6e-102">Настройка операций за счет исключительного использования хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="15d6e-102">Customizing Operations by Using Stored Procedures Exclusively</span></span>
<span data-ttu-id="15d6e-103">Распространенным сценарием является доступ к данным с использованием только хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="15d6e-103">Access to data by using only stored procedures is a common scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15d6e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="15d6e-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="15d6e-105">Описание</span><span class="sxs-lookup"><span data-stu-id="15d6e-105">Description</span></span>  
 <span data-ttu-id="15d6e-106">Можно изменить пример, приведенный в [Настройка операций за счет хранимых процедур](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) , заменив первый запрос (который вызывает динамическое выполнение SQL) на вызов метода, который создает оболочку для хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="15d6e-106">You can modify the example provided in [Customizing Operations By Using Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) by replacing even the first query (which causes dynamic SQL execution) with a method call that wraps a stored procedure.</span></span>  
  
 <span data-ttu-id="15d6e-107">Предположим, что `CustomersByCity` является методом, как в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="15d6e-107">Assume `CustomersByCity` is the method, as in the following example.</span></span>  
  
### <a name="code"></a><span data-ttu-id="15d6e-108">Код</span><span class="sxs-lookup"><span data-stu-id="15d6e-108">Code</span></span>  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 <span data-ttu-id="15d6e-109">Следующий код выполняется без динамического SQL.</span><span class="sxs-lookup"><span data-stu-id="15d6e-109">The following code executes without any dynamic SQL.</span></span>  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="15d6e-110">См. также</span><span class="sxs-lookup"><span data-stu-id="15d6e-110">See also</span></span>

- [<span data-ttu-id="15d6e-111">Ответственность разработчика при переопределении поведения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="15d6e-111">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
