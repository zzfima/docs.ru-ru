---
title: "Рекомендации по использованию классов System.Net"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- sending data, best practices
- requesting data from Internet, best practices
- WebRequest class, best practices
- data requests, best practices
- WebResponse class, best practices
- best practices, data requests
- receiving data, best practices
ms.assetid: 716decc6-5952-47b7-9c5a-ba6fc5698684
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 83254955138c99ec0187e5cf74566266c2ecb303
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="best-practices-for-systemnet-classes"></a><span data-ttu-id="a1092-102">Рекомендации по использованию классов System.Net</span><span class="sxs-lookup"><span data-stu-id="a1092-102">Best Practices for System.Net Classes</span></span>
<span data-ttu-id="a1092-103">В этом разделе приводятся рекомендации по наиболее эффективному использованию классов, содержащихся в <xref:System.Net>:</span><span class="sxs-lookup"><span data-stu-id="a1092-103">The following recommendations will help you use the classes contained in <xref:System.Net> to their best advantage:</span></span>  
  
-   <span data-ttu-id="a1092-104">По возможности рекомендуется всегда использовать <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> вместо приведения типов к классам потомков.</span><span class="sxs-lookup"><span data-stu-id="a1092-104">Use <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> whenever possible instead of type casting to descendant classes.</span></span> <span data-ttu-id="a1092-105">Приложения, использующие **WebRequest** и **WebResponse**, могут использовать преимущества новых протоколов Интернета, не требуя при этом серьезного изменения кода.</span><span class="sxs-lookup"><span data-stu-id="a1092-105">Applications that use **WebRequest** and **WebResponse** can take advantage of new Internet protocols without needing extensive code changes.</span></span>  
  
-   <span data-ttu-id="a1092-106">При написании приложений ASP.NET, которые выполняются на сервере с использованием классов **System.Net**, с точки зрения производительности зачастую лучше использовать асинхронные методы для <xref:System.Net.WebRequest.GetResponse%2A> и <xref:System.Net.WebResponse.GetResponseStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="a1092-106">When writing ASP.NET applications that run on a server using the **System.Net** classes, it is often better, from a performance standpoint, to use the asynchronous methods for <xref:System.Net.WebRequest.GetResponse%2A> and <xref:System.Net.WebResponse.GetResponseStream%2A>.</span></span>  
  
-   <span data-ttu-id="a1092-107">Число открытых подключений к интернет-ресурсам может заметно влиять на производительность и пропускную способность сети.</span><span class="sxs-lookup"><span data-stu-id="a1092-107">The number of connections opened to an Internet resource can have a significant impact on network performance and throughput.</span></span> <span data-ttu-id="a1092-108">В **System.Net** по умолчанию используется два подключения для каждого приложения на один ведущий узел.</span><span class="sxs-lookup"><span data-stu-id="a1092-108">**System.Net** uses two connections per application per host by default.</span></span> <span data-ttu-id="a1092-109">С помощью свойства <xref:System.Net.ServicePoint.ConnectionLimit%2A> в <xref:System.Net.ServicePoint> приложения можно увеличить число его подключений для конкретного узла.</span><span class="sxs-lookup"><span data-stu-id="a1092-109">Setting the <xref:System.Net.ServicePoint.ConnectionLimit%2A> property in the <xref:System.Net.ServicePoint> for your application can increase this number for a particular host.</span></span> <span data-ttu-id="a1092-110">Свойство <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=nameWithType> позволяет увеличить это значение по умолчанию для всех узлов.</span><span class="sxs-lookup"><span data-stu-id="a1092-110">Setting the <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=nameWithType> property can increase this default for all hosts.</span></span>  
  
-   <span data-ttu-id="a1092-111">При написании протоколов уровня сокета по возможности используйте <xref:System.Net.Sockets.TcpClient> или <xref:System.Net.Sockets.UdpClient> вместо прямого использования <xref:System.Net.Sockets.Socket>.</span><span class="sxs-lookup"><span data-stu-id="a1092-111">When writing socket-level protocols, try to use <xref:System.Net.Sockets.TcpClient> or <xref:System.Net.Sockets.UdpClient> whenever possible instead of writing directly to a <xref:System.Net.Sockets.Socket>.</span></span> <span data-ttu-id="a1092-112">Эти два клиентских класса инкапсулируют создание сокетов TCP и UDP, не требуя от вас обработки сведений о подключении.</span><span class="sxs-lookup"><span data-stu-id="a1092-112">These two client classes encapsulate the creation of TCP and UDP sockets without requiring you to handle the details of the connection.</span></span>  
  
-   <span data-ttu-id="a1092-113">При доступе к узлам, требующим ввода учетных данных, используйте класс <xref:System.Net.CredentialCache> для создания кэша учетных данных вместо того, чтобы предоставлять их с каждым запросом.</span><span class="sxs-lookup"><span data-stu-id="a1092-113">When accessing sites that require credentials, use the <xref:System.Net.CredentialCache> class to create a cache of credentials rather than supplying them with every request.</span></span> <span data-ttu-id="a1092-114">Класс **CredentialCache** выполняет поиск соответствующих запросу учетных данных в кэше, освобождая вас от необходимости создавать и предоставлять учетные данные на основе URL.</span><span class="sxs-lookup"><span data-stu-id="a1092-114">The **CredentialCache** class searches the cache to find the appropriate credential to present with a request, relieving you of the responsibility of creating and presenting credentials based on the URL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1092-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a1092-115">See Also</span></span>  
 [<span data-ttu-id="a1092-116">Сетевое программирование в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a1092-116">Network Programming in the .NET Framework</span></span>](../../../docs/framework/network-programming/index.md)
