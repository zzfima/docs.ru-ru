---
title: '&lt;NET.pipe&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 918ee745e12a339b71f228f3f79b366335d7824d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltnetpipegt"></a><span data-ttu-id="85681-102">&lt;NET.pipe&gt;</span><span class="sxs-lookup"><span data-stu-id="85681-102">&lt;net.pipe&gt;</span></span>
<span data-ttu-id="85681-103">Задает параметры конфигурации для службы активации именованных каналов, которая управляет временем существования соединения для именованного канала, а также обрабатывает запросы на активацию, которые поступают по именованным каналам.</span><span class="sxs-lookup"><span data-stu-id="85681-103">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
 <span data-ttu-id="85681-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="85681-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="85681-105">\<NET.pipe ></span><span class="sxs-lookup"><span data-stu-id="85681-105">\<net.pipe></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85681-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85681-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.pipe maxPendingAccepts="Integer"  
                    maxPendingConnections="Integer"  
          receiveTimeout="TimeSpan">  
          <allowAccounts>  
             // LocalSystem account  
             <add securityIdentifier="S-1-5-18"/>  
             // LocalService account  
             <add securityIdentifier="S-1-5-19"/>  
             // Administrators account  
             <add securityIdentifier="S-1-5-20"/>  
             // Network Service account  
             <add securityIdentifier="S-1-5-32-544" />  
             // IIS_IUSRS account (Vista only)  
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.pipe>  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="85681-107">Тип</span><span class="sxs-lookup"><span data-stu-id="85681-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85681-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="85681-108">Attributes and Elements</span></span>  
 <span data-ttu-id="85681-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="85681-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85681-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="85681-110">Attributes</span></span>  
  
|<span data-ttu-id="85681-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="85681-111">Attribute</span></span>|<span data-ttu-id="85681-112">Описание</span><span class="sxs-lookup"><span data-stu-id="85681-112">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="85681-113">Целое число, которое определяет максимальное количество одновременных необработанных принимающих потоков в конечной точке для общей службы.</span><span class="sxs-lookup"><span data-stu-id="85681-113">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="85681-114">Значение по умолчанию — 2.</span><span class="sxs-lookup"><span data-stu-id="85681-114">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="85681-115">Целое число, задающее максимальное количество соединений, которые могут ожидать распределения.</span><span class="sxs-lookup"><span data-stu-id="85681-115">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="85681-116">Значение по умолчанию — 100.</span><span class="sxs-lookup"><span data-stu-id="85681-116">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="85681-117">Значение `TimeSpan`, определяющее время ожидания для чтения данных кадрирования и проведения распределения подключений из базовых подключений.</span><span class="sxs-lookup"><span data-stu-id="85681-117">A `TimeSpan` that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="85681-118">Значение по умолчанию - 00:00:10.</span><span class="sxs-lookup"><span data-stu-id="85681-118">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85681-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="85681-119">Child Elements</span></span>  
  
|<span data-ttu-id="85681-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="85681-120">Element</span></span>|<span data-ttu-id="85681-121">Описание</span><span class="sxs-lookup"><span data-stu-id="85681-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85681-122">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="85681-122">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="85681-123">Коллекция элементов конфигурации, которые содержат атрибут `securityIdentifier`, указывающий учетные записи пользователей для процессов служб [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], которые имеют доступ к совместно используемой службе.</span><span class="sxs-lookup"><span data-stu-id="85681-123">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="85681-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="85681-124">Parent Elements</span></span>  
  
|<span data-ttu-id="85681-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="85681-125">Element</span></span>|<span data-ttu-id="85681-126">Описание</span><span class="sxs-lookup"><span data-stu-id="85681-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85681-127">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="85681-127">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="85681-128">Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="85681-128">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85681-129">См. также</span><span class="sxs-lookup"><span data-stu-id="85681-129">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
