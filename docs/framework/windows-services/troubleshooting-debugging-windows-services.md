---
title: "Разрешение вопросов. Отладка служб Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- troubleshooting service applications
- services, troubleshooting
- troubleshooting debugging, Windows Services
- Windows Service applications, debugging
- services, debugging
- Windows Service applications, troubleshooting
ms.assetid: cf859d4c-f04c-4cb7-81e3-bc7de8bea190
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 51c28f6e9b6fa2974fb9861716b2c9fc2a38fe1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="c0629-102">Разрешение вопросов. Отладка служб Windows</span><span class="sxs-lookup"><span data-stu-id="c0629-102">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="c0629-103">При отладке приложения службы Windows, службы и **Windows Service Manager** взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="c0629-103">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="c0629-104">**Service Manager** запускает службу путем вызова <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метода, а затем — 30 секунд для ожидания <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метод для возврата.</span><span class="sxs-lookup"><span data-stu-id="c0629-104">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="c0629-105">Если метод не возвращает в течение этого времени, диспетчер отображает ошибку, что служба не запущена.</span><span class="sxs-lookup"><span data-stu-id="c0629-105">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="c0629-106">При отладке <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метода, как описано в [как: отладка приложений служб Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), необходимо иметь в виду этого 30-секундного периода.</span><span class="sxs-lookup"><span data-stu-id="c0629-106">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="c0629-107">Если установить точку останова в <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метода и не пройти ее за 30 секунд, служба не запускается диспетчер.</span><span class="sxs-lookup"><span data-stu-id="c0629-107">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0629-108">См. также</span><span class="sxs-lookup"><span data-stu-id="c0629-108">See Also</span></span>  
 [<span data-ttu-id="c0629-109">Как: отладка приложений служб Windows</span><span class="sxs-lookup"><span data-stu-id="c0629-109">How to: Debug Windows Service Applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [<span data-ttu-id="c0629-110">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="c0629-110">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
