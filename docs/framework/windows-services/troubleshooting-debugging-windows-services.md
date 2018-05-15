---
title: Разрешение вопросов. Отладка служб Windows
ms.date: 03/30/2017
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
author: ghogen
manager: douge
ms.openlocfilehash: 77a0c19c2da2d1886beaf396650fa024fc1243a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="2982a-102">Разрешение вопросов. Отладка служб Windows</span><span class="sxs-lookup"><span data-stu-id="2982a-102">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="2982a-103">При отладке приложения службы Windows, службы и **Windows Service Manager** взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="2982a-103">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="2982a-104">**Service Manager** запускает службу путем вызова <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метода, а затем — 30 секунд для ожидания <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метод для возврата.</span><span class="sxs-lookup"><span data-stu-id="2982a-104">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="2982a-105">Если метод не возвращает в течение этого времени, диспетчер отображает ошибку, что служба не запущена.</span><span class="sxs-lookup"><span data-stu-id="2982a-105">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="2982a-106">При отладке <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метода, как описано в [как: отладка приложений служб Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), необходимо иметь в виду этого 30-секундного периода.</span><span class="sxs-lookup"><span data-stu-id="2982a-106">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="2982a-107">Если установить точку останова в <xref:System.ServiceProcess.ServiceBase.OnStart%2A> метода и не пройти ее за 30 секунд, служба не запускается диспетчер.</span><span class="sxs-lookup"><span data-stu-id="2982a-107">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2982a-108">См. также</span><span class="sxs-lookup"><span data-stu-id="2982a-108">See Also</span></span>  
 [<span data-ttu-id="2982a-109">Практическое руководство. Отладка приложений служб Windows</span><span class="sxs-lookup"><span data-stu-id="2982a-109">How to: Debug Windows Service Applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [<span data-ttu-id="2982a-110">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="2982a-110">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
