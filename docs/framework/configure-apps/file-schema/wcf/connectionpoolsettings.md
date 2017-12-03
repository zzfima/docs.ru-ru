---
title: '&lt;connectionPoolSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f1980365da8514060290066a4e15e5f88e35f7f4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltconnectionpoolsettingsgt"></a><span data-ttu-id="bce69-102">&lt;connectionPoolSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="bce69-102">&lt;connectionPoolSettings&gt;</span></span>
<span data-ttu-id="bce69-103">Задает дополнительные параметры пула подключений для привязки именованного канала.</span><span class="sxs-lookup"><span data-stu-id="bce69-103">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
 <span data-ttu-id="bce69-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="bce69-104">\<system.serviceModel></span></span>  
<span data-ttu-id="bce69-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="bce69-105">\<bindings></span></span>  
<span data-ttu-id="bce69-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="bce69-106">\<customBinding></span></span>  
<span data-ttu-id="bce69-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="bce69-107">\<binding></span></span>  
<span data-ttu-id="bce69-108">\<namePipeTransport ></span><span class="sxs-lookup"><span data-stu-id="bce69-108">\<namePipeTransport></span></span>  
<span data-ttu-id="bce69-109">\<connectionPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="bce69-109">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bce69-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bce69-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings  
        groupName="String"  
    idleTimeout"TimeSpan"  
    maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bce69-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bce69-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bce69-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bce69-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bce69-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bce69-113">Attributes</span></span>  
  
|<span data-ttu-id="bce69-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bce69-114">Attribute</span></span>|<span data-ttu-id="bce69-115">Описание</span><span class="sxs-lookup"><span data-stu-id="bce69-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="bce69-116">Строка, определяющая имя пула подключений, используемого для исходящих каналов.</span><span class="sxs-lookup"><span data-stu-id="bce69-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="bce69-117">В потоковом режиме общий доступ к подключениям не предоставляется, то есть пул подключений отключен.</span><span class="sxs-lookup"><span data-stu-id="bce69-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="bce69-118">Значение по умолчанию - строка «default».</span><span class="sxs-lookup"><span data-stu-id="bce69-118">The default is a "default" string.</span></span> <span data-ttu-id="bce69-119">Это значение можно изменить, чтобы изолировать подключения для конкретного клиента в отдельные группы.</span><span class="sxs-lookup"><span data-stu-id="bce69-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="bce69-120">Положительное значение <xref:System.TimeSpan>, указывающее максимальное время бездействия для подключения перед его закрытием.</span><span class="sxs-lookup"><span data-stu-id="bce69-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="bce69-121">Значение по умолчанию - 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="bce69-121">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="bce69-122">Положительное целое число, указывающее максимальное число подключений к удаленной конечной точке, инициированных одной службой.</span><span class="sxs-lookup"><span data-stu-id="bce69-122">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="bce69-123">Соединения сверх лимита помещаются в очередь до высвобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="bce69-123">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="bce69-124">Параметр `idleTimeout` ограничивает продолжительность времени, в течение которого подключения остаются в очереди до возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="bce69-124">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="bce69-125">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="bce69-125">The default is 10.</span></span><br /><br /> <span data-ttu-id="bce69-126">Этот атрибут ограничивает число одновременных активных подключений клиента к конкретной конечной точке службы.</span><span class="sxs-lookup"><span data-stu-id="bce69-126">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="bce69-127">В случае превышения этого значения при наличии большего числа активных соединений клиентов служба может прекратить отвечать на запросы клиента.</span><span class="sxs-lookup"><span data-stu-id="bce69-127">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="bce69-128">В таком случае это значение следует скорректировать, чтобы оно было больше предполагаемого максимума одновременных подключений клиента к конкретной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="bce69-128">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bce69-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bce69-129">Child Elements</span></span>  
 <span data-ttu-id="bce69-130">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bce69-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bce69-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bce69-131">Parent Elements</span></span>  
  
|<span data-ttu-id="bce69-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="bce69-132">Element</span></span>|<span data-ttu-id="bce69-133">Описание</span><span class="sxs-lookup"><span data-stu-id="bce69-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bce69-134">\<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="bce69-134">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="bce69-135">Определяет транспорт, вызывающий передачу сообщений с использованием именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="bce69-135">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bce69-136">См. также</span><span class="sxs-lookup"><span data-stu-id="bce69-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="bce69-137">Транспорты</span><span class="sxs-lookup"><span data-stu-id="bce69-137">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="bce69-138">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="bce69-138">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="bce69-139">Привязки</span><span class="sxs-lookup"><span data-stu-id="bce69-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="bce69-140">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="bce69-140">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="bce69-141">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="bce69-141">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="bce69-142">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="bce69-142">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
