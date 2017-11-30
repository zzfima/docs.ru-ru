---
title: "Пространственные функции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 935708457c3ebc8257b2495da36886468be1c706
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="spatial-functions"></a><span data-ttu-id="712bc-102">Пространственные функции</span><span class="sxs-lookup"><span data-stu-id="712bc-102">Spatial Functions</span></span>
<span data-ttu-id="712bc-103">Форматов литералов для пространственных типов не имеется.</span><span class="sxs-lookup"><span data-stu-id="712bc-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="712bc-104">Однако можно использовать канонические функции Entity Framework, вызываемые с помощью строк в формате известного текстового представления.</span><span class="sxs-lookup"><span data-stu-id="712bc-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="712bc-105">Например, следующий вызов функции создает точку геометрии.</span><span class="sxs-lookup"><span data-stu-id="712bc-105">For example, the following function call creates a geometry point:</span></span>  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="712bc-106">[Методы SpatialEdmFunctions](http://msdn.microsoft.com/library/hh749531.aspx) странице перечисляются все Пространственные канонические методы Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="712bc-106">The [SpatialEdmFunctions Methods](http://msdn.microsoft.com/library/hh749531.aspx) page lists all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="712bc-107">Щелкните интересующий метод, чтобы посмотреть, какие параметры должны быть переданы функции.</span><span class="sxs-lookup"><span data-stu-id="712bc-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
