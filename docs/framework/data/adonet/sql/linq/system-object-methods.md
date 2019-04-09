---
title: Методы System.Object
ms.date: 03/30/2017
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
ms.openlocfilehash: 3a52f081f1c0c6e6c5218550009c736d0ed60514
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097672"
---
# <a name="systemobject-methods"></a><span data-ttu-id="f2639-102">Методы System.Object</span><span class="sxs-lookup"><span data-stu-id="f2639-102">System.Object Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="f2639-103">поддерживает следующие <xref:System.Object> методы.</span><span class="sxs-lookup"><span data-stu-id="f2639-103">supports the following <xref:System.Object> methods.</span></span>  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="f2639-104">не поддерживает следующие <xref:System.Object> методы.</span><span class="sxs-lookup"><span data-stu-id="f2639-104">does not support the following <xref:System.Object> methods.</span></span>  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType> <span data-ttu-id="f2639-105">для двоичных типов, таких как `BINARY`, `VARBINARY`, `IMAGE`, и `TIMESTAMP`.</span><span class="sxs-lookup"><span data-stu-id="f2639-105">for binary types such as `BINARY`, `VARBINARY`, `IMAGE`, and `TIMESTAMP`.</span></span>||  
  
## <a name="differences-from-net"></a><span data-ttu-id="f2639-106">Отличия от платформы .NET</span><span class="sxs-lookup"><span data-stu-id="f2639-106">Differences from .NET</span></span>  
 <span data-ttu-id="f2639-107">Выходные данные <xref:System.Object.ToString?displayProperty=nameWithType> для double используется SQL `CONVERT`(NVARCHAR(30), @x, 2) на SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2639-107">The output of <xref:System.Object.ToString?displayProperty=nameWithType> for double uses SQL `CONVERT`(NVARCHAR(30), @x, 2) on SQL.</span></span> <span data-ttu-id="f2639-108">В этом случае SQL всегда использует 16 цифр и экспоненциальный формат (например, «0.000000000000000e+000» для 0).</span><span class="sxs-lookup"><span data-stu-id="f2639-108">SQL always uses 16 digits and scientific notation in this case (for example, "0.000000000000000e+000" for 0).</span></span> <span data-ttu-id="f2639-109">В результате преобразование <xref:System.Object.ToString?displayProperty=nameWithType> формирует строку, отличную от строки преобразования <xref:System.Convert.ToString%2A?displayProperty=nameWithType> на платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f2639-109">As a result, <xref:System.Object.ToString?displayProperty=nameWithType> conversion does not produce the same string as <xref:System.Convert.ToString%2A?displayProperty=nameWithType> in the .NET Framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2639-110">См. также</span><span class="sxs-lookup"><span data-stu-id="f2639-110">See also</span></span>

- [<span data-ttu-id="f2639-111">Типы данных и функции</span><span class="sxs-lookup"><span data-stu-id="f2639-111">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
