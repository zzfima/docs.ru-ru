---
title: "Пространственные функции | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Пространственные функции
Форматов литералов для пространственных типов не имеется.  Однако можно использовать канонические функции Entity Framework, вызываемые с помощью строк в формате известного текстового представления.  Например, следующий вызов функции создает точку геометрии.  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 На странице [Методы SpatialEdmFunctions](http://msdn.microsoft.com/library/hh749531.aspx) перечисляются все пространственные канонические методы Entity Framework.  Щелкните интересующий метод, чтобы посмотреть, какие параметры должны быть переданы функции.