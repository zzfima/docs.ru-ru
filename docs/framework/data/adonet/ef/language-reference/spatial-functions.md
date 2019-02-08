---
title: Пространственные функции
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: 09402633c5e7f591a534992fc92655e6a2d1d88d
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904477"
---
# <a name="spatial-functions"></a>Пространственные функции
Форматов литералов для пространственных типов не имеется. Однако можно использовать канонические функции Entity Framework, вызываемые с помощью строк в формате известного текстового представления. Например, следующий вызов функции создает точку геометрии.  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> Методы имеют все Пространственные канонические методы Entity Framework. Щелкните интересующий метод, чтобы посмотреть, какие параметры должны быть переданы функции.
