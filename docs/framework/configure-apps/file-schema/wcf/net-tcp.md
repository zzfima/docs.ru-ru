---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 4a3a17655f5469fe84c0b684ebdac9848bbfba84
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397697"
---
# <a name="nettcp"></a><span data-ttu-id="8fe81-102">\<> NET. TCP</span><span class="sxs-lookup"><span data-stu-id="8fe81-102">\<net.tcp></span></span>
<span data-ttu-id="8fe81-103">Задает параметры конфигурации для службы общего доступа к портам Net.Tcp, которая позволяет нескольким процессам совместно использовать один и тот же порт протокола TCP.</span><span class="sxs-lookup"><span data-stu-id="8fe81-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
<span data-ttu-id="8fe81-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8fe81-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8fe81-105">&nbsp;&nbsp;[ **\<> System. serviceModel. Activation**](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="8fe81-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="8fe81-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> NET. TCP**</span><span class="sxs-lookup"><span data-stu-id="8fe81-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<net.tcp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fe81-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8fe81-107">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="8fe81-108">Тип</span><span class="sxs-lookup"><span data-stu-id="8fe81-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8fe81-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8fe81-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8fe81-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8fe81-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8fe81-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8fe81-111">Attributes</span></span>  
  
|<span data-ttu-id="8fe81-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8fe81-112">Attribute</span></span>|<span data-ttu-id="8fe81-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8fe81-113">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="8fe81-114">Целое число, указывающее максимальное количество необработанных соединений, принимаемых из общего соединения, но еще не отправленных в службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="8fe81-114">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="8fe81-115">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="8fe81-115">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="8fe81-116">Целое число, которое определяет максимальное количество одновременных необработанных принимающих потоков в конечной точке для общей службы.</span><span class="sxs-lookup"><span data-stu-id="8fe81-116">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="8fe81-117">Значение по умолчанию — 2</span><span class="sxs-lookup"><span data-stu-id="8fe81-117">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="8fe81-118">Максимальное число подключений, принятия которых приложением может ожидать прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="8fe81-118">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="8fe81-119">После превышения значения этой квоты новые входящие подключения сбрасываются, а не ожидают принятия.</span><span class="sxs-lookup"><span data-stu-id="8fe81-119">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="8fe81-120">Возможности подключения (такие как безопасность сообщения) могут вынудить клиента открыть несколько подключений.</span><span class="sxs-lookup"><span data-stu-id="8fe81-120">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="8fe81-121">При установке значения квоты администраторы службы должны учитывать возможность установления дополнительных подключений.</span><span class="sxs-lookup"><span data-stu-id="8fe81-121">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="8fe81-122">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="8fe81-122">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="8fe81-123">Значение <xref:System.TimeSpan>, определяющее время ожидания для чтения данных кадрирования и проведения распределения подключений из базовых подключений.</span><span class="sxs-lookup"><span data-stu-id="8fe81-123">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="8fe81-124">Значение по умолчанию - 00:00:10.</span><span class="sxs-lookup"><span data-stu-id="8fe81-124">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="8fe81-125">Логическое значение, указывающее, использует ли служба совместного использования портов службу Microsoft Teredo для прослушивания TCP-портов от имени служб WCF.</span><span class="sxs-lookup"><span data-stu-id="8fe81-125">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="8fe81-126">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="8fe81-126">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8fe81-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8fe81-127">Child Elements</span></span>  
  
|<span data-ttu-id="8fe81-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="8fe81-128">Element</span></span>|<span data-ttu-id="8fe81-129">Описание</span><span class="sxs-lookup"><span data-stu-id="8fe81-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8fe81-130">\<Алловаккаунтс ></span><span class="sxs-lookup"><span data-stu-id="8fe81-130">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="8fe81-131">Коллекция элементов конфигурации, которая содержит `securityIdentifier` атрибут для указания учетных записей пользователей для процессов, размещающий службы WCF, и которым предоставляется доступ к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="8fe81-131">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8fe81-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8fe81-132">Parent Elements</span></span>  
  
|<span data-ttu-id="8fe81-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="8fe81-133">Element</span></span>|<span data-ttu-id="8fe81-134">Описание</span><span class="sxs-lookup"><span data-stu-id="8fe81-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8fe81-135">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="8fe81-135">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="8fe81-136">Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="8fe81-136">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fe81-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="8fe81-137">Remarks</span></span>  
 <span data-ttu-id="8fe81-138">Дополнительные сведения о совместном использовании портов см. в разделе [общий доступ к портам Net. TCP](../../../wcf/feature-details/net-tcp-port-sharing.md).</span><span class="sxs-lookup"><span data-stu-id="8fe81-138">For more information on port sharing, see [Net.TCP Port Sharing](../../../wcf/feature-details/net-tcp-port-sharing.md).</span></span> <span data-ttu-id="8fe81-139">Сведения о настройке службы общего доступа к портам см. в разделе [Настройка службы совместного использования портов net. TCP](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span><span class="sxs-lookup"><span data-stu-id="8fe81-139">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fe81-140">См. также</span><span class="sxs-lookup"><span data-stu-id="8fe81-140">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [<span data-ttu-id="8fe81-141">Совместное использование портов Net.TCP</span><span class="sxs-lookup"><span data-stu-id="8fe81-141">Net.TCP Port Sharing</span></span>](../../../wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="8fe81-142">Настройка службы совместного использования портов Net.TCP</span><span class="sxs-lookup"><span data-stu-id="8fe81-142">Configuring the Net.TCP Port Sharing Service</span></span>](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
