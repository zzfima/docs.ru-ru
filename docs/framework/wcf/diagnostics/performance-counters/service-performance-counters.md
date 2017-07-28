---
title: "Счетчики производительности службы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Счетчики производительности службы
Счетчики производительности службы измеряют поведение службы в целом, их можно использовать для диагностики производительности всей службы.При просмотре с помощью системного монитора \(Perfmon.exe\) счетчики находятся под объектом производительности `ServiceModelService 4.0.0.0`.Экземпляры именуются по следующей схеме:  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  Длина имени экземпляра счетчика производительности ограничена.Если длина имени экземпляра счетчика [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] превышает максимально допустимое значение, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] заменяет часть имени экземпляра значением хэша.  
  
## См. также  
 [Счетчики производительности](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)