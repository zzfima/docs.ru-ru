---
title: <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 3c8d905a04f8f6d7ecff9b0ef9e7d3c8afa727e3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925971"
---
# <a name="connectionpoolsettings"></a><span data-ttu-id="78888-101">\<Коннектионпулсеттингс ></span><span class="sxs-lookup"><span data-stu-id="78888-101">\<connectionPoolSettings></span></span>
<span data-ttu-id="78888-102">Задает дополнительные параметры пула подключений для привязки именованного канала.</span><span class="sxs-lookup"><span data-stu-id="78888-102">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
 <span data-ttu-id="78888-103">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="78888-103">\<system.serviceModel></span></span>  
<span data-ttu-id="78888-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="78888-104">\<bindings></span></span>  
<span data-ttu-id="78888-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="78888-105">\<customBinding></span></span>  
<span data-ttu-id="78888-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="78888-106">\<binding></span></span>  
<span data-ttu-id="78888-107">\<Намепипетранспорт ></span><span class="sxs-lookup"><span data-stu-id="78888-107">\<namePipeTransport></span></span>  
<span data-ttu-id="78888-108">\<Коннектионпулсеттингс ></span><span class="sxs-lookup"><span data-stu-id="78888-108">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78888-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78888-109">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78888-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="78888-110">Attributes and Elements</span></span>  
 <span data-ttu-id="78888-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="78888-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78888-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="78888-112">Attributes</span></span>  
  
|<span data-ttu-id="78888-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="78888-113">Attribute</span></span>|<span data-ttu-id="78888-114">Описание</span><span class="sxs-lookup"><span data-stu-id="78888-114">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="78888-115">Строка, определяющая имя пула подключений, используемого для исходящих каналов.</span><span class="sxs-lookup"><span data-stu-id="78888-115">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="78888-116">В потоковом режиме общий доступ к подключениям не предоставляется, то есть пул подключений отключен.</span><span class="sxs-lookup"><span data-stu-id="78888-116">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="78888-117">Значение по умолчанию - строка «default».</span><span class="sxs-lookup"><span data-stu-id="78888-117">The default is a "default" string.</span></span> <span data-ttu-id="78888-118">Это значение можно изменить, чтобы изолировать подключения для конкретного клиента в отдельные группы.</span><span class="sxs-lookup"><span data-stu-id="78888-118">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="78888-119">Положительное значение <xref:System.TimeSpan>, указывающее максимальное время бездействия для подключения перед его закрытием.</span><span class="sxs-lookup"><span data-stu-id="78888-119">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="78888-120">Значение по умолчанию - 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="78888-120">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="78888-121">Положительное целое число, указывающее максимальное число подключений к удаленной конечной точке, инициированных одной службой.</span><span class="sxs-lookup"><span data-stu-id="78888-121">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="78888-122">Соединения сверх лимита помещаются в очередь до высвобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="78888-122">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="78888-123">Параметр `idleTimeout` ограничивает продолжительность времени, в течение которого подключения остаются в очереди до возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="78888-123">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="78888-124">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="78888-124">The default is 10.</span></span><br /><br /> <span data-ttu-id="78888-125">Этот атрибут ограничивает число одновременных активных подключений клиента к конкретной конечной точке службы.</span><span class="sxs-lookup"><span data-stu-id="78888-125">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="78888-126">В случае превышения этого значения при наличии большего числа активных соединений клиентов служба может прекратить отвечать на запросы клиента.</span><span class="sxs-lookup"><span data-stu-id="78888-126">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="78888-127">В таком случае это значение следует скорректировать, чтобы оно было больше предполагаемого максимума одновременных подключений клиента к конкретной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="78888-127">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78888-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="78888-128">Child Elements</span></span>  
 <span data-ttu-id="78888-129">Нет.</span><span class="sxs-lookup"><span data-stu-id="78888-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78888-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="78888-130">Parent Elements</span></span>  
  
|<span data-ttu-id="78888-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="78888-131">Element</span></span>|<span data-ttu-id="78888-132">Описание</span><span class="sxs-lookup"><span data-stu-id="78888-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78888-133">\<Намедпипетранспорт ></span><span class="sxs-lookup"><span data-stu-id="78888-133">\<namedPipeTransport></span></span>](namedpipetransport.md)|<span data-ttu-id="78888-134">Определяет транспорт, вызывающий передачу сообщений с использованием именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="78888-134">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78888-135">См. также</span><span class="sxs-lookup"><span data-stu-id="78888-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="78888-136">Транспорты</span><span class="sxs-lookup"><span data-stu-id="78888-136">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="78888-137">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="78888-137">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="78888-138">Привязки</span><span class="sxs-lookup"><span data-stu-id="78888-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="78888-139">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="78888-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="78888-140">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="78888-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="78888-141">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="78888-141">\<customBinding></span></span>](custombinding.md)
