---
title: Неподдерживаемые функциональные возможности
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: 18a1a8f33a9360b4299648bcd329f4c5f2e7de88
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097877"
---
# <a name="unsupported-functionality"></a><span data-ttu-id="e30fc-102">Неподдерживаемые функциональные возможности</span><span class="sxs-lookup"><span data-stu-id="e30fc-102">Unsupported Functionality</span></span>
<span data-ttu-id="e30fc-103">В LINQ to SQL следующие функции SQL недоступны путем преобразования существующих конструкций среды CLR и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e30fc-103">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     <span data-ttu-id="e30fc-104">Хотя функция `LIKE` не поддерживается прямым преобразованием, аналогичная функция существует в классе <xref:System.Data.Linq.SqlClient.SqlMethods>.</span><span class="sxs-lookup"><span data-stu-id="e30fc-104">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="e30fc-105">Дополнительные сведения см. в разделе <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e30fc-105">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
-   `DATEDIFF`  
  
     <span data-ttu-id="e30fc-106">В LINQ to SQL реализована ограниченная поддержка функции `DATEDIFF`.</span><span class="sxs-lookup"><span data-stu-id="e30fc-106">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="e30fc-107">Аналогичная функция существует в классе <xref:System.Data.Linq.SqlClient.SqlMethods>.</span><span class="sxs-lookup"><span data-stu-id="e30fc-107">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
-   `ROUND`  
  
     <span data-ttu-id="e30fc-108">В LINQ to SQL реализована ограниченная поддержка функции `ROUND`.</span><span class="sxs-lookup"><span data-stu-id="e30fc-108">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="e30fc-109">Дополнительные сведения см. в разделе [System.Math методы](system-math-methods.md).</span><span class="sxs-lookup"><span data-stu-id="e30fc-109">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e30fc-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e30fc-110">See also</span></span>

- [<span data-ttu-id="e30fc-111">Типы данных и функции</span><span class="sxs-lookup"><span data-stu-id="e30fc-111">Data Types and Functions</span></span>](data-types-and-functions.md)
