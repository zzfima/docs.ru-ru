---
title: Класс HttpListener
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 0d5b7fccdac9dba3fd44d12241dd60cbaefa1b7a
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2018
ms.locfileid: "47192944"
---
# <a name="httplistener"></a><span data-ttu-id="a314d-102">Класс HttpListener</span><span class="sxs-lookup"><span data-stu-id="a314d-102">HttpListener</span></span>
<span data-ttu-id="a314d-103">Класс <xref:System.Net.HttpListener> предоставляет программно управляемый прослушиватель протокола HTTP.</span><span class="sxs-lookup"><span data-stu-id="a314d-103">The <xref:System.Net.HttpListener> class provides a programmatically controlled HTTP protocol listener.</span></span> <span data-ttu-id="a314d-104">Прослушиватель активен в течение времени существования <xref:System.Net.HttpListener> объекта и выполняется в приложении.</span><span class="sxs-lookup"><span data-stu-id="a314d-104">The listener is active for the lifetime of the <xref:System.Net.HttpListener> object and runs within your application.</span></span>  
  
## <a name="httpsys"></a><span data-ttu-id="a314d-105">HTTP.SYS</span><span class="sxs-lookup"><span data-stu-id="a314d-105">HTTP.SYS</span></span>  
 <span data-ttu-id="a314d-106">Класс <xref:System.Net.HttpListener> построен на базе HTTP.sys, который является прослушивателем режима ядра, обрабатывающим весь трафик HTTP для Windows.</span><span class="sxs-lookup"><span data-stu-id="a314d-106">The <xref:System.Net.HttpListener> class is built on top of HTTP.sys, which is the kernel mode listener that handles all HTTP traffic for Windows.</span></span> <span data-ttu-id="a314d-107">HTTP.sys обеспечивает управление соединениями, регулирование полосы пропускания и ведение журналов веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="a314d-107">HTTP.sys provides connection management, bandwidth throttling, and Web server logging.</span></span> <span data-ttu-id="a314d-108">Используйте средство `HttpCfg.exe` для добавления SSL-сертификатов.</span><span class="sxs-lookup"><span data-stu-id="a314d-108">Use the `HttpCfg.exe` tool to add SSL certificates.</span></span> <span data-ttu-id="a314d-109">Дополнительные сведения см. в документации к средству [HttpCfg.exe](https://go.microsoft.com/fwlink/?LinkID=178284) в документации к [серверу](https://go.microsoft.com/fwlink/?LinkID=178285).</span><span class="sxs-lookup"><span data-stu-id="a314d-109">For more information, see the documentation on the [HttpCfg.exe](https://go.microsoft.com/fwlink/?LinkID=178284) tool in the [Server](https://go.microsoft.com/fwlink/?LinkID=178285) documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a314d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a314d-110">See Also</span></span>  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpWebRequest>  
 <xref:System.Net.HttpWebResponse>  
 [<span data-ttu-id="a314d-111">HTTP-сервер</span><span class="sxs-lookup"><span data-stu-id="a314d-111">HTTP Server</span></span>](https://go.microsoft.com/fwlink/?LinkID=178285)  
 [<span data-ttu-id="a314d-112">Усовершенствования безопасности в Internet Information</span><span class="sxs-lookup"><span data-stu-id="a314d-112">Security Enhancements in Internet Information</span></span>](https://go.microsoft.com/fwlink/?LinkID=178286)  
 [<span data-ttu-id="a314d-113">Образец ведущего приложения ASPX HttpListener</span><span class="sxs-lookup"><span data-stu-id="a314d-113">HttpListener ASPX Host Application Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=179560)  
 [<span data-ttu-id="a314d-114">Пример технологии HttpListener</span><span class="sxs-lookup"><span data-stu-id="a314d-114">HttpListener Technology Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=179558)  
 [<span data-ttu-id="a314d-115">Примеры сетевого программирования</span><span class="sxs-lookup"><span data-stu-id="a314d-115">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)
