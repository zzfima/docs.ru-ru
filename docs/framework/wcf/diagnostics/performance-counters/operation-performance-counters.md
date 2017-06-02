---
title: "Счетчики производительности операций | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Счетчики производительности операций
При просмотре с помощью системного монитора \(Perfmon.exe\) счетчики производительности операций находятся под объектом производительности `ServiceModelOperation 4.0.0.0`.Каждая операция содержит отдельный экземпляр.Следовательно, если указанный контракт имеет 10 операций, 10 экземпляров счетчика операций связаны с этим контрактом.Экземпляры объекта именуются по следующей схеме:  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 Этот счетчик позволяет измерить, как используется вызов и насколько успешно выполняется операция.  
  
> [!CAUTION]
>  Длина имени экземпляра счетчика производительности ограничена.Если длина имени экземпляра счетчика [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] превышает максимально допустимое значение, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] заменяет часть имени экземпляра значением хэша.  
  
## См. также  
 [Счетчики производительности](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)