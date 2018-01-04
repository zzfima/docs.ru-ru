---
title: "Перенос приложений удаленного взаимодействия .NET на платформу WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b7d305adf1810832016cdafbb60fc025f17e0786
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>Перенос приложений удаленного взаимодействия .NET на платформу WCF
**Этот раздел относится к технологии прежних версий, которая сохраняется для обеспечения обратной совместимости с существующими приложениями и не рекомендуется для разработки новых приложений. Теперь распределенные приложения разрабатываются при помощи платформы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].**  
  
 Существует два способа использовать преимущества [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в сочетании с существующими приложениями удаленного взаимодействия .NET: интеграция и миграция. Интеграция позволяет запускать .Net Remoting 2.0 и [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] параллельно, т. е. предоставлять одни и те же бизнес-объекты одновременно посредством обеих технологий без внесения изменений в существующий код .Net Remoting 2.0. Интеграция требует использования [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 или выше. Если совместимость на уровне линий связи с системами Remoting 2.0 не требуется, для использования преимуществ [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно целиком мигрировать службу в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Миграция с .NET Remoting 2.0 на [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] требует внесения изменений в интерфейс удаленного объекта и параметры его конфигурации. В этих разделах рассматриваются [из удаленного взаимодействия на платформу Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403).  
  
## <a name="see-also"></a>См. также  
 [Концептуальный обзор](../../../../docs/framework/wcf/conceptual-overview.md)
