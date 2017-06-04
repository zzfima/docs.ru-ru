---
title: "Troubleshooting: Debugging Windows Services | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "debugging Windows Service applications"
  - "debugging [Visual Studio], Windows services"
  - "troubleshooting service applications"
  - "services, troubleshooting"
  - "troubleshooting debugging, Windows Services"
  - "Windows Service applications, debugging"
  - "services, debugging"
  - "Windows Service applications, troubleshooting"
ms.assetid: cf859d4c-f04c-4cb7-81e3-bc7de8bea190
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 8
---
# Troubleshooting: Debugging Windows Services
При отладке приложения службы Windows отлаживаемая служба взаимодействует с **диспетчером служб Windows**.  **Диспетчер служб** запускает службу, вызывая ее метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A>. После этого он в течение 30 секунд ожидает завершения метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A>.  Если в течение этого времени метод не завершит работу, диспетчер служб выдает сообщение о невозможности запустить службу.  
  
 При отладке метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A> в соответствии с руководством [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md) необходимо помнить об этом 30\-секундном периоде.  Если поместить точку останова в методе <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и не пройти ее за 30 секунд, то диспетчер служб не запустит службу.  
  
## См. также  
 [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)   
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)