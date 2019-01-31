---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 85a9112def77fc31c8e4b826454894fe7372b31b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257659"
---
# <a name="nettcp"></a><span data-ttu-id="cc30f-102">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="cc30f-102">\<net.tcp></span></span>
<span data-ttu-id="cc30f-103">Задает параметры конфигурации для службы общего доступа к портам Net.Tcp, которая позволяет нескольким процессам совместно использовать один и тот же порт протокола TCP.</span><span class="sxs-lookup"><span data-stu-id="cc30f-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
 <span data-ttu-id="cc30f-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="cc30f-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="cc30f-105">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="cc30f-105">\<net.tcp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc30f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc30f-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.tcp listenBacklog="Integer"
             maxPendingAccepts="Integer"
             maxPendingConnections="Integer"
             receiveTimeout="TimeSpan"
             teredoEnabled="Boolean">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18"/>
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19"/>
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20"/>
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only)-->
        <add securityIdentifier="S-1-5-32-568"/>
      </allowAccounts>
    </net.tcp>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="cc30f-107">Тип</span><span class="sxs-lookup"><span data-stu-id="cc30f-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc30f-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cc30f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cc30f-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cc30f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc30f-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cc30f-110">Attributes</span></span>  
  
|<span data-ttu-id="cc30f-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cc30f-111">Attribute</span></span>|<span data-ttu-id="cc30f-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="cc30f-112">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="cc30f-113">Целое число, указывающее максимальное количество необработанных соединений, принятых от общего соединения, но еще не переданных службам Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="cc30f-113">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="cc30f-114">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="cc30f-114">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="cc30f-115">Целое число, которое определяет максимальное количество одновременных необработанных принимающих потоков в конечной точке для общей службы.</span><span class="sxs-lookup"><span data-stu-id="cc30f-115">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="cc30f-116">Значение по умолчанию — 2.</span><span class="sxs-lookup"><span data-stu-id="cc30f-116">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="cc30f-117">Максимальное число подключений, принятия которых приложением может ожидать прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="cc30f-117">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="cc30f-118">После превышения значения этой квоты новые входящие подключения сбрасываются, а не ожидают принятия.</span><span class="sxs-lookup"><span data-stu-id="cc30f-118">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="cc30f-119">Функции подключения (такие как безопасность сообщения) могут вынудить клиента открыть несколько подключений.</span><span class="sxs-lookup"><span data-stu-id="cc30f-119">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="cc30f-120">При установке значения квоты администраторы службы должны учитывать возможность установления дополнительных подключений.</span><span class="sxs-lookup"><span data-stu-id="cc30f-120">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="cc30f-121">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="cc30f-121">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="cc30f-122">Значение `TimeSpan`, определяющее время ожидания для чтения данных кадрирования и проведения распределения подключений из базовых подключений.</span><span class="sxs-lookup"><span data-stu-id="cc30f-122">A `TimeSpan` that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="cc30f-123">Значение по умолчанию - 00:00:10.</span><span class="sxs-lookup"><span data-stu-id="cc30f-123">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="cc30f-124">Логическое значение, указывающее, использует ли служба совместного использования портов службу Microsoft Teredo для прослушивания TCP-портов от имени служб WCF.</span><span class="sxs-lookup"><span data-stu-id="cc30f-124">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="cc30f-125">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="cc30f-125">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cc30f-126">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cc30f-126">Child Elements</span></span>  
  
|<span data-ttu-id="cc30f-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="cc30f-127">Element</span></span>|<span data-ttu-id="cc30f-128">Описание:</span><span class="sxs-lookup"><span data-stu-id="cc30f-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc30f-129">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="cc30f-129">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="cc30f-130">Коллекция элементов конфигурации, которые содержат `securityIdentifier` атрибут для указания учетных записей пользователей для процессов размещения служб WCF, которые предоставляются доступ при подключении к совместно используемой службе.</span><span class="sxs-lookup"><span data-stu-id="cc30f-130">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cc30f-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cc30f-131">Parent Elements</span></span>  
  
|<span data-ttu-id="cc30f-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="cc30f-132">Element</span></span>|<span data-ttu-id="cc30f-133">Описание:</span><span class="sxs-lookup"><span data-stu-id="cc30f-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc30f-134">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="cc30f-134">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="cc30f-135">Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="cc30f-135">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc30f-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="cc30f-136">Remarks</span></span>  
 <span data-ttu-id="cc30f-137">Дополнительные сведения о совместное использование порта, см. в разделе [совместного использования портов Net.TCP](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md).</span><span class="sxs-lookup"><span data-stu-id="cc30f-137">For more information on port sharing, see [Net.TCP Port Sharing](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md).</span></span> <span data-ttu-id="cc30f-138">Чтобы понять, как настроить службы совместного использования портов, см. в разделе [Настройка службы совместного использования портов Net.TCP](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span><span class="sxs-lookup"><span data-stu-id="cc30f-138">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc30f-139">См. также</span><span class="sxs-lookup"><span data-stu-id="cc30f-139">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [<span data-ttu-id="cc30f-140">Совместное использование портов Net.TCP</span><span class="sxs-lookup"><span data-stu-id="cc30f-140">Net.TCP Port Sharing</span></span>](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="cc30f-141">Настройка службы совместного использования портов Net.TCP</span><span class="sxs-lookup"><span data-stu-id="cc30f-141">Configuring the Net.TCP Port Sharing Service</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
