---
title: Размещение в управляемом приложении
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1e81a8eb27725edeccf3e5c7489109ba47b70dec
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="hosting-in-a-managed-application"></a>Размещение в управляемом приложении
Службы[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] можно разместить в любом приложении [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] . Резидентное размещение служб - самый гибкий вариант размещения, так как в этом случае требуется минимальное развертывание инфраструктуры. Однако это и наименее надежный вариант размещения, так как управляемые приложения не предоставляют дополнительные функции размещения и управления, как другие варианты размещения в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], такие как службы IIS и службы Windows.  
  
 Для создания резидентной службы необходимо создать и открыть экземпляр узла службы <xref:System.ServiceModel.ServiceHost>, который запускает службу, ожидающую сообщений. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Как: размещение службы WCF в управляемом приложении](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Полный пример определения контракта, реализации контракта и размещения службы внутри управляемого приложения в разделе [учебник по началу работы](../../../../docs/framework/wcf/getting-started-tutorial.md) и [резидентной](../../../../docs/framework/wcf/samples/self-host.md).  
  
 В следующих разделах описаны стандартные сценарии, использующие этот вариант размещения.  
  
## <a name="console-applications"></a>Консольные приложения  
 Одним из стандартных сценариев, обеспечиваемых резидентным размещением, является выполнение служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в консольных приложениях. Размещение службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] внутри консольного приложения, как правило, целесообразно на этапе разработки службы. В этом случае приложение легко отлаживать, удобно получать данные трассировки, чтобы узнать, что происходит внутри приложения, и удобно копировать приложение в другие расположения.  
  
## <a name="rich-client-applications"></a>Функционально насыщенные клиентские приложения  
 Других стандартных сценариев, обеспечиваемых резидентным размещением насыщенных клиентских приложений, например те, на основе Windows Presentation Foundation (WPF) или Windows Forms (WinForms). Кроме того, этот вариант размещения упрощает взаимодействие функционально насыщенных клиентских приложений, таких как приложения [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] и WinForms, с внешними системами. Например, одноранговый клиент для совместной работы может использовать в качестве пользовательского интерфейса [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] и размещать службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] , позволяющую другим клиентам подключаться к нему и обмениваться с ним информацией.  
  
## <a name="see-also"></a>См. также  
 [Размещение служб](../../../../docs/framework/wcf/hosting-services.md)  
 [Руководство по началу работы](../../../../docs/framework/wcf/getting-started-tutorial.md)
