---
title: "Неподдерживаемые функциональные возможности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 244d9ee7accd3686729542d0f0a15966bcde7b78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="unsupported-functionality"></a><span data-ttu-id="edeb1-102">Неподдерживаемые функциональные возможности</span><span class="sxs-lookup"><span data-stu-id="edeb1-102">Unsupported Functionality</span></span>
<span data-ttu-id="edeb1-103">В LINQ to SQL следующие функции SQL недоступны путем преобразования существующих конструкций среды CLR и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="edeb1-103">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     <span data-ttu-id="edeb1-104">Хотя функция `LIKE` не поддерживается прямым преобразованием, аналогичная функция существует в классе <xref:System.Data.Linq.SqlClient.SqlMethods>.</span><span class="sxs-lookup"><span data-stu-id="edeb1-104">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="edeb1-105">Для получения дополнительной информации см. <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="edeb1-105">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
-   `DATEDIFF`  
  
     <span data-ttu-id="edeb1-106">В LINQ to SQL реализована ограниченная поддержка функции `DATEDIFF`.</span><span class="sxs-lookup"><span data-stu-id="edeb1-106">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="edeb1-107">Аналогичная функция существует в классе <xref:System.Data.Linq.SqlClient.SqlMethods>.</span><span class="sxs-lookup"><span data-stu-id="edeb1-107">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
-   `ROUND`  
  
     <span data-ttu-id="edeb1-108">В LINQ to SQL реализована ограниченная поддержка функции `ROUND`.</span><span class="sxs-lookup"><span data-stu-id="edeb1-108">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="edeb1-109">Дополнительные сведения см. в разделе [методы System.Math](system-math-methods.md).</span><span class="sxs-lookup"><span data-stu-id="edeb1-109">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edeb1-110">См. также</span><span class="sxs-lookup"><span data-stu-id="edeb1-110">See Also</span></span>  
 [<span data-ttu-id="edeb1-111">Типы данных и функции</span><span class="sxs-lookup"><span data-stu-id="edeb1-111">Data Types and Functions</span></span>](data-types-and-functions.md)
