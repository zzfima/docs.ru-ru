---
title: "Методы System.Object"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 319dc7ceae191de417bbdd33a5e234b42f3454de
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="systemobject-methods"></a><span data-ttu-id="2a42c-102">Методы System.Object</span><span class="sxs-lookup"><span data-stu-id="2a42c-102">System.Object Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="2a42c-103">поддерживает следующие <xref:System.Object> методы.</span><span class="sxs-lookup"><span data-stu-id="2a42c-103"> supports the following <xref:System.Object> methods.</span></span>  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 <span data-ttu-id="2a42c-104">Ниже перечислены методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], не поддерживаемые технологией <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="2a42c-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not support the following <xref:System.Object> methods.</span></span>  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<span data-ttu-id="2a42c-105"><xref:System.Object.ToString?displayProperty=nameWithType> для двоичных типов, таких как `BINARY`, `VARBINARY`, `IMAGE` и `TIMESTAMP`.</span><span class="sxs-lookup"><span data-stu-id="2a42c-105"><xref:System.Object.ToString?displayProperty=nameWithType> for binary types such as `BINARY`, `VARBINARY`, `IMAGE`, and `TIMESTAMP`.</span></span>||  
  
## <a name="differences-from-net"></a><span data-ttu-id="2a42c-106">Отличия от платформы .NET</span><span class="sxs-lookup"><span data-stu-id="2a42c-106">Differences from .NET</span></span>  
 <span data-ttu-id="2a42c-107">Выходные данные <xref:System.Object.ToString?displayProperty=nameWithType> для double используется SQL `CONVERT`(NVARCHAR(30), @x, 2) на сервере SQL.</span><span class="sxs-lookup"><span data-stu-id="2a42c-107">The output of <xref:System.Object.ToString?displayProperty=nameWithType> for double uses SQL `CONVERT`(NVARCHAR(30), @x, 2) on SQL.</span></span> <span data-ttu-id="2a42c-108">В этом случае SQL всегда использует 16 цифр и экспоненциальный формат (например, «0.000000000000000e+000» для 0).</span><span class="sxs-lookup"><span data-stu-id="2a42c-108">SQL always uses 16 digits and scientific notation in this case (for example, "0.000000000000000e+000" for 0).</span></span> <span data-ttu-id="2a42c-109">В результате преобразование <xref:System.Object.ToString?displayProperty=nameWithType> формирует строку, отличную от строки преобразования <xref:System.Convert.ToString%2A?displayProperty=nameWithType> на платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2a42c-109">As a result, <xref:System.Object.ToString?displayProperty=nameWithType> conversion does not produce the same string as <xref:System.Convert.ToString%2A?displayProperty=nameWithType> in the .NET Framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a42c-110">См. также</span><span class="sxs-lookup"><span data-stu-id="2a42c-110">See Also</span></span>  
 [<span data-ttu-id="2a42c-111">Типы данных и функции</span><span class="sxs-lookup"><span data-stu-id="2a42c-111">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
