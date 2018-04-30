---
title: Поддержка нескольких привязок узла IIS
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40440495-254d-45c8-a8c6-b29f364892ba
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a4b586b4d5c3c37355bf7b05a8a0227565a5b5e5
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="supporting-multiple-iis-site-bindings"></a><span data-ttu-id="fbbbe-102">Поддержка нескольких привязок узла IIS</span><span class="sxs-lookup"><span data-stu-id="fbbbe-102">Supporting Multiple IIS Site Bindings</span></span>
<span data-ttu-id="fbbbe-103">При размещении службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] в каталоге служб IIS 7.0 может понадобиться предоставить несколько базовых адресов, использующих один и тот же протокол на одном и том же узле.</span><span class="sxs-lookup"><span data-stu-id="fbbbe-103">When hosting a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service under Internet Information Services (IIS) 7.0, you may want to provide multiple base addresses that use the same protocol on the same site.</span></span> <span data-ttu-id="fbbbe-104">Это позволяет одной и той же службе отвечать на несколько разных URI.</span><span class="sxs-lookup"><span data-stu-id="fbbbe-104">This allows the same service to respond to a number of different URIs.</span></span> <span data-ttu-id="fbbbe-105">Это полезно, если вы хотите разместить службу, прослушивает http://www.contoso.com и http://contoso.com. Также может использоваться при создании службы, имеющей базовый адрес для внутренних пользователей и отдельный базовый адрес для внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="fbbbe-105">This is useful when you want to host a service that listens on http://www.contoso.com and http://contoso.com. It is also useful to create a service that has a base address for internal users and a separate base address for external users.</span></span> <span data-ttu-id="fbbbe-106">Например: http://internal.contoso.com и http://www.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="fbbbe-106">For example: http://internal.contoso.com and http://www.contoso.com.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fbbbe-107">Эта функция доступна только при использовании протокола HTTP.</span><span class="sxs-lookup"><span data-stu-id="fbbbe-107">This functionality is only available using the HTTP protocol.</span></span>  
  
## <a name="multiple-base-addresses"></a><span data-ttu-id="fbbbe-108">Несколько базовых адресов</span><span class="sxs-lookup"><span data-stu-id="fbbbe-108">Multiple Base Addresses</span></span>  
 <span data-ttu-id="fbbbe-109">Данная функция доступна только в службах [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], размещенных в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="fbbbe-109">This feature is only available to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services that are hosted under IIS.</span></span> <span data-ttu-id="fbbbe-110">Эта функция отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fbbbe-110">This feature is not enabled by default.</span></span> <span data-ttu-id="fbbbe-111">Чтобы включить, то необходимо добавить `multipleSiteBindingsEnabled` атрибут <`serviceHostingEnvironment`> элемент в файл Web.config файл и присвойте ему значение `true`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fbbbe-111">To enable it you must add the `multipleSiteBindingsEnabled` attribute to the <`serviceHostingEnvironment`> element in your Web.config file and set it to `true`, as shown in the following example.</span></span>  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"/>  
```  
  
 <span data-ttu-id="fbbbe-112">При размещении службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в службах IIS создается один базовый адрес на основе URI в виртуальном каталоге, содержащем приложение.</span><span class="sxs-lookup"><span data-stu-id="fbbbe-112">When hosting a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service under IIS, IIS creates one base address for you based on the URI to the virtual directory that contains the application.</span></span> <span data-ttu-id="fbbbe-113">Чтобы добавить одну или несколько привязок, можно с помощью диспетчера служб IIS добавить на веб-сайт дополнительные базовые адреса, использующие тот же протокол.</span><span class="sxs-lookup"><span data-stu-id="fbbbe-113">You can add additional base addresses that use the same protocol by using Internet Information Services Manager to add one or more bindings to your Web site.</span></span> <span data-ttu-id="fbbbe-114">Для каждой привязки укажите протокол (HTTP или HTTPS), IP-адрес, порт и имя узла.</span><span class="sxs-lookup"><span data-stu-id="fbbbe-114">For each binding specify a protocol (HTTP or HTTPS), an IP address, a port, and a host name.</span></span> <span data-ttu-id="fbbbe-115">Дополнительные сведения об использовании диспетчера служб IIS см. в разделе [диспетчера служб IIS (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164057).</span><span class="sxs-lookup"><span data-stu-id="fbbbe-115">For more information about using Internet Information Services Manager, see [IIS Manager (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164057).</span></span> <span data-ttu-id="fbbbe-116">Дополнительные сведения о добавлении привязки к сайту см. в разделе [создать веб-сайт (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164060)</span><span class="sxs-lookup"><span data-stu-id="fbbbe-116">For more information about adding bindings to a site, see [Create a Web Site (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164060)</span></span>  
  
 <span data-ttu-id="fbbbe-117">Указание нескольких базовых адресов для одного и того же узла влияет на содержимое страницы справки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], импорт схемы и сведения WSDL/MEX, сформированные службой.</span><span class="sxs-lookup"><span data-stu-id="fbbbe-117">Specifying multiple base addresses for the same site affects the content of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Help page, importing schema, and the WSDL/MEX information generated by the service.</span></span> <span data-ttu-id="fbbbe-118">Страница справки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отображает командную строку для создания клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], способного взаимодействовать со службой.</span><span class="sxs-lookup"><span data-stu-id="fbbbe-118">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Help page displays the command line to use to generate a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client that can communicate with the service.</span></span> <span data-ttu-id="fbbbe-119">Эта командная строка содержит только первый адрес, указанный в привязке служб IIS для веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="fbbbe-119">This command line contains only the first address specified in the IIS binding for the Web site.</span></span> <span data-ttu-id="fbbbe-120">Аналогичным образом при импорте схемы используется только первый базовый адрес, указанный в привязке служб IIS.</span><span class="sxs-lookup"><span data-stu-id="fbbbe-120">Similarly when importing schema, only the first base address specified in the IIS binding is used.</span></span> <span data-ttu-id="fbbbe-121">Данные WSDL и MEX содержит все базовые адреса, указанные в привязках служб IIS.</span><span class="sxs-lookup"><span data-stu-id="fbbbe-121">WSDL and MEX data contain all the base addresses specified in the IIS bindings.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="fbbbe-122">Это означает, что если служба имеет два базовых адреса (для внутренних и для внешних пользователей), то оба они указываются в данных WSDL/MEX, сформированных службой.</span><span class="sxs-lookup"><span data-stu-id="fbbbe-122">This means that if a service has two base addresses, one for internal users and one for external users, both are specified in the WSDL/MEX information generated by the service.</span></span>
