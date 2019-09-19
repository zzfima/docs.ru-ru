---
title: 'Устранение неполадок: Отладка служб Windows'
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
ms.openlocfilehash: cbedb0051cbb08c2875e145a2bad35ae4d02a74e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053511"
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="1ba28-102">Устранение неполадок: Отладка служб Windows</span><span class="sxs-lookup"><span data-stu-id="1ba28-102">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="1ba28-103">При отладке приложения-службы Windows происходит взаимодействие между службой и диспетчером **Windows Service Manager**.</span><span class="sxs-lookup"><span data-stu-id="1ba28-103">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="1ba28-104">**Service Manager** запускает службу, вызывая метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, после чего 30 секунд ожидает возврат метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A>.</span><span class="sxs-lookup"><span data-stu-id="1ba28-104">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="1ba28-105">Если метод не возвращается за это время, диспетчер отображает ошибку о невозможности запустить службу.</span><span class="sxs-lookup"><span data-stu-id="1ba28-105">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="1ba28-106">При отладке метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, как описано в статье [Практическое руководство. Отладка приложений-служб Windows](how-to-debug-windows-service-applications.md), необходимо помнить об этом 30-секундном периоде.</span><span class="sxs-lookup"><span data-stu-id="1ba28-106">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="1ba28-107">Если в методе <xref:System.ServiceProcess.ServiceBase.OnStart%2A> установить точку останова и не пройти ее за 30 секунд, диспетчер не запустит службу.</span><span class="sxs-lookup"><span data-stu-id="1ba28-107">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ba28-108">См. также</span><span class="sxs-lookup"><span data-stu-id="1ba28-108">See also</span></span>

- [<span data-ttu-id="1ba28-109">Практическое руководство. Отладка приложений служб Windows</span><span class="sxs-lookup"><span data-stu-id="1ba28-109">How to: Debug Windows Service Applications</span></span>](how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="1ba28-110">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="1ba28-110">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
