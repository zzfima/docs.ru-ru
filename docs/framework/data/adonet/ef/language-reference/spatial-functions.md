---
title: Пространственные функции
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: ad6b722e84aae40354e30434b107752d02352645
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47078283"
---
# <a name="spatial-functions"></a><span data-ttu-id="6184a-102">Пространственные функции</span><span class="sxs-lookup"><span data-stu-id="6184a-102">Spatial Functions</span></span>
<span data-ttu-id="6184a-103">Форматов литералов для пространственных типов не имеется.</span><span class="sxs-lookup"><span data-stu-id="6184a-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="6184a-104">Однако можно использовать канонические функции Entity Framework, вызываемые с помощью строк в формате известного текстового представления.</span><span class="sxs-lookup"><span data-stu-id="6184a-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="6184a-105">Например, следующий вызов функции создает точку геометрии.</span><span class="sxs-lookup"><span data-stu-id="6184a-105">For example, the following function call creates a geometry point:</span></span>  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="6184a-106">[Методы SpatialEdmFunctions](https://msdn.microsoft.com/library/hh749531.aspx) странице перечисляются все Пространственные канонические методы Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="6184a-106">The [SpatialEdmFunctions Methods](https://msdn.microsoft.com/library/hh749531.aspx) page lists all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="6184a-107">Щелкните интересующий метод, чтобы посмотреть, какие параметры должны быть переданы функции.</span><span class="sxs-lookup"><span data-stu-id="6184a-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
