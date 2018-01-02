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
ms.workload: dotnet
ms.openlocfilehash: 11500830c7c5fd75a9e2880a5875bd21fb070634
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltconnectionpoolsettingsgt"></a><span data-ttu-id="8ecad-102">&lt;connectionPoolSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="8ecad-102">&lt;connectionPoolSettings&gt;</span></span>
<span data-ttu-id="8ecad-103">Задает дополнительные параметры пула подключений для привязки именованного канала.</span><span class="sxs-lookup"><span data-stu-id="8ecad-103">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
 <span data-ttu-id="8ecad-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8ecad-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8ecad-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="8ecad-105">\<bindings></span></span>  
<span data-ttu-id="8ecad-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8ecad-106">\<customBinding></span></span>  
<span data-ttu-id="8ecad-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="8ecad-107">\<binding></span></span>  
<span data-ttu-id="8ecad-108">\<namePipeTransport ></span><span class="sxs-lookup"><span data-stu-id="8ecad-108">\<namePipeTransport></span></span>  
<span data-ttu-id="8ecad-109">\<connectionPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="8ecad-109">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ecad-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ecad-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings  
        groupName="String"  
    idleTimeout"TimeSpan"  
    maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ecad-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8ecad-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8ecad-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8ecad-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ecad-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8ecad-113">Attributes</span></span>  
  
|<span data-ttu-id="8ecad-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8ecad-114">Attribute</span></span>|<span data-ttu-id="8ecad-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8ecad-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="8ecad-116">Строка, определяющая имя пула подключений, используемого для исходящих каналов.</span><span class="sxs-lookup"><span data-stu-id="8ecad-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="8ecad-117">В потоковом режиме общий доступ к подключениям не предоставляется, то есть пул подключений отключен.</span><span class="sxs-lookup"><span data-stu-id="8ecad-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="8ecad-118">Значение по умолчанию - строка «default».</span><span class="sxs-lookup"><span data-stu-id="8ecad-118">The default is a "default" string.</span></span> <span data-ttu-id="8ecad-119">Это значение можно изменить, чтобы изолировать подключения для конкретного клиента в отдельные группы.</span><span class="sxs-lookup"><span data-stu-id="8ecad-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="8ecad-120">Положительное значение <xref:System.TimeSpan>, указывающее максимальное время бездействия для подключения перед его закрытием.</span><span class="sxs-lookup"><span data-stu-id="8ecad-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="8ecad-121">Значение по умолчанию - 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="8ecad-121">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="8ecad-122">Положительное целое число, указывающее максимальное число подключений к удаленной конечной точке, инициированных одной службой.</span><span class="sxs-lookup"><span data-stu-id="8ecad-122">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="8ecad-123">Соединения сверх лимита помещаются в очередь до высвобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8ecad-123">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="8ecad-124">Параметр `idleTimeout` ограничивает продолжительность времени, в течение которого подключения остаются в очереди до возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="8ecad-124">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="8ecad-125">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="8ecad-125">The default is 10.</span></span><br /><br /> <span data-ttu-id="8ecad-126">Этот атрибут ограничивает число одновременных активных подключений клиента к конкретной конечной точке службы.</span><span class="sxs-lookup"><span data-stu-id="8ecad-126">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="8ecad-127">В случае превышения этого значения при наличии большего числа активных соединений клиентов служба может прекратить отвечать на запросы клиента.</span><span class="sxs-lookup"><span data-stu-id="8ecad-127">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="8ecad-128">В таком случае это значение следует скорректировать, чтобы оно было больше предполагаемого максимума одновременных подключений клиента к конкретной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="8ecad-128">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ecad-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8ecad-129">Child Elements</span></span>  
 <span data-ttu-id="8ecad-130">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8ecad-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ecad-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8ecad-131">Parent Elements</span></span>  
  
|<span data-ttu-id="8ecad-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="8ecad-132">Element</span></span>|<span data-ttu-id="8ecad-133">Описание:</span><span class="sxs-lookup"><span data-stu-id="8ecad-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ecad-134">\<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="8ecad-134">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="8ecad-135">Определяет транспорт, вызывающий передачу сообщений с использованием именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="8ecad-135">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ecad-136">См. также</span><span class="sxs-lookup"><span data-stu-id="8ecad-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="8ecad-137">Транспорты</span><span class="sxs-lookup"><span data-stu-id="8ecad-137">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="8ecad-138">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="8ecad-138">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="8ecad-139">Привязки</span><span class="sxs-lookup"><span data-stu-id="8ecad-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="8ecad-140">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="8ecad-140">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="8ecad-141">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="8ecad-141">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="8ecad-142">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8ecad-142">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
