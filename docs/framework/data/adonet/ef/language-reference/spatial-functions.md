---
title: Пространственные функции
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: eba384e77389f82006479f165178e80fcac244b1
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319304"
---
# <a name="spatial-functions"></a><span data-ttu-id="7a494-102">Пространственные функции</span><span class="sxs-lookup"><span data-stu-id="7a494-102">Spatial Functions</span></span>
<span data-ttu-id="7a494-103">Форматов литералов для пространственных типов не имеется.</span><span class="sxs-lookup"><span data-stu-id="7a494-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="7a494-104">Однако можно использовать канонические функции Entity Framework, вызываемые с помощью строк в формате известного текстового представления.</span><span class="sxs-lookup"><span data-stu-id="7a494-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="7a494-105">Например, следующий вызов функции создает точку геометрии.</span><span class="sxs-lookup"><span data-stu-id="7a494-105">For example, the following function call creates a geometry point:</span></span>  
  
```sql  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="7a494-106">Методы <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> имеют все пространственные канонические Entity Framework методы.</span><span class="sxs-lookup"><span data-stu-id="7a494-106">The <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> methods have all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="7a494-107">Щелкните интересующий метод, чтобы посмотреть, какие параметры должны быть переданы функции.</span><span class="sxs-lookup"><span data-stu-id="7a494-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
