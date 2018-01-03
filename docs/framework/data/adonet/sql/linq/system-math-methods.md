---
title: "Методы System.Math"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 8c5f19918ca1c80daffab482436ab6ce018321f5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="systemmath-methods"></a><span data-ttu-id="faadd-102">Методы System.Math</span><span class="sxs-lookup"><span data-stu-id="faadd-102">System.Math Methods</span></span>
<span data-ttu-id="faadd-103">Ниже перечислены методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], не поддерживаемые технологией <xref:System.Math>.</span><span class="sxs-lookup"><span data-stu-id="faadd-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not support the following <xref:System.Math> methods.</span></span>  
  
-   <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a><span data-ttu-id="faadd-104">Отличия от платформы .NET</span><span class="sxs-lookup"><span data-stu-id="faadd-104">Differences from .NET</span></span>  
 <span data-ttu-id="faadd-105">Семантики округления в .NET Framework отличаются от подобных семантик SQL Server.</span><span class="sxs-lookup"><span data-stu-id="faadd-105">The .NET Framework has different rounding semantics from SQL Server.</span></span> <span data-ttu-id="faadd-106"><xref:System.Math.Round%2A> Метод в .NET Framework выполняет *банковское округление*, в котором числа, оканчивающиеся на.5 округление до ближайшего четного числа, а не для ближайшего большего числа.</span><span class="sxs-lookup"><span data-stu-id="faadd-106">The <xref:System.Math.Round%2A> method in the .NET Framework performs *Banker's rounding*, where numbers that ends in .5 round to the nearest even digit instead of to the next higher digit.</span></span> <span data-ttu-id="faadd-107">Например, число 2,5 округляется до 2, а 3,5 - до 4.</span><span class="sxs-lookup"><span data-stu-id="faadd-107">For example, 2.5 rounds to 2, while 3.5 rounds to 4.</span></span> <span data-ttu-id="faadd-108">(Это помогает избежать систематического смещения в сторону более высоких значений в транзакциях данных.)</span><span class="sxs-lookup"><span data-stu-id="faadd-108">(This technique helps avoid systematic bias toward higher values in large data transactions.)</span></span>  
  
 <span data-ttu-id="faadd-109">В SQL, наоборот, функция `ROUND` всегда округляет от нуля.</span><span class="sxs-lookup"><span data-stu-id="faadd-109">In SQL, the `ROUND` function instead always rounds away from 0.</span></span> <span data-ttu-id="faadd-110">Поэтому число 2,5 округляется до 3, тогда как в платформе .NET Framework - до 2.</span><span class="sxs-lookup"><span data-stu-id="faadd-110">Therefore 2.5 rounds to 3, contrasted with its rounding to 2 in the .NET Framework.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="faadd-111"> передается в семантики SQL `ROUND` и не пытается реализовать банковское округление.</span><span class="sxs-lookup"><span data-stu-id="faadd-111"> passes through to the SQL `ROUND` semantics and does not try to implement Banker's rounding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faadd-112">См. также</span><span class="sxs-lookup"><span data-stu-id="faadd-112">See Also</span></span>  
 [<span data-ttu-id="faadd-113">Типы данных и функции</span><span class="sxs-lookup"><span data-stu-id="faadd-113">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
