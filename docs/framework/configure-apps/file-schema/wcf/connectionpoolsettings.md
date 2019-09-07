---
title: <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 842173c7bd9673a1e08c93d5ed650a42b9d979e5
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400470"
---
# <a name="connectionpoolsettings"></a><span data-ttu-id="b4c66-101">\<Коннектионпулсеттингс ></span><span class="sxs-lookup"><span data-stu-id="b4c66-101">\<connectionPoolSettings></span></span>
<span data-ttu-id="b4c66-102">Задает дополнительные параметры пула подключений для привязки именованного канала.</span><span class="sxs-lookup"><span data-stu-id="b4c66-102">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
<span data-ttu-id="b4c66-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b4c66-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b4c66-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b4c66-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b4c66-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="b4c66-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="b4c66-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="b4c66-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="b4c66-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="b4c66-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="b4c66-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Намедпипетранспорт >** ](namedpipetransport.md)</span><span class="sxs-lookup"><span data-stu-id="b4c66-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedPipeTransport>**](namedpipetransport.md)</span></span>\
<span data-ttu-id="b4c66-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Коннектионпулсеттингс >**</span><span class="sxs-lookup"><span data-stu-id="b4c66-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4c66-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4c66-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4c66-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b4c66-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b4c66-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b4c66-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4c66-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b4c66-113">Attributes</span></span>  
  
|<span data-ttu-id="b4c66-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b4c66-114">Attribute</span></span>|<span data-ttu-id="b4c66-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b4c66-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="b4c66-116">Строка, определяющая имя пула подключений, используемого для исходящих каналов.</span><span class="sxs-lookup"><span data-stu-id="b4c66-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="b4c66-117">В потоковом режиме общий доступ к подключениям не предоставляется, то есть пул подключений отключен.</span><span class="sxs-lookup"><span data-stu-id="b4c66-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="b4c66-118">Значение по умолчанию - строка «default».</span><span class="sxs-lookup"><span data-stu-id="b4c66-118">The default is a "default" string.</span></span> <span data-ttu-id="b4c66-119">Это значение можно изменить, чтобы изолировать подключения для конкретного клиента в отдельные группы.</span><span class="sxs-lookup"><span data-stu-id="b4c66-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="b4c66-120">Положительное значение <xref:System.TimeSpan>, указывающее максимальное время бездействия для подключения перед его закрытием.</span><span class="sxs-lookup"><span data-stu-id="b4c66-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="b4c66-121">Значение по умолчанию - 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="b4c66-121">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="b4c66-122">Положительное целое число, указывающее максимальное число подключений к удаленной конечной точке, инициированных одной службой.</span><span class="sxs-lookup"><span data-stu-id="b4c66-122">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="b4c66-123">Соединения сверх лимита помещаются в очередь до высвобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b4c66-123">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="b4c66-124">Параметр `idleTimeout` ограничивает продолжительность времени, в течение которого подключения остаются в очереди до возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="b4c66-124">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="b4c66-125">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="b4c66-125">The default is 10.</span></span><br /><br /> <span data-ttu-id="b4c66-126">Этот атрибут ограничивает число одновременных активных подключений клиента к конкретной конечной точке службы.</span><span class="sxs-lookup"><span data-stu-id="b4c66-126">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="b4c66-127">В случае превышения этого значения при наличии большего числа активных соединений клиентов служба может прекратить отвечать на запросы клиента.</span><span class="sxs-lookup"><span data-stu-id="b4c66-127">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="b4c66-128">В таком случае это значение следует скорректировать, чтобы оно было больше предполагаемого максимума одновременных подключений клиента к конкретной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="b4c66-128">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4c66-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b4c66-129">Child Elements</span></span>  
 <span data-ttu-id="b4c66-130">Нет.</span><span class="sxs-lookup"><span data-stu-id="b4c66-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4c66-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b4c66-131">Parent Elements</span></span>  
  
|<span data-ttu-id="b4c66-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="b4c66-132">Element</span></span>|<span data-ttu-id="b4c66-133">Описание</span><span class="sxs-lookup"><span data-stu-id="b4c66-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4c66-134">\<Намедпипетранспорт ></span><span class="sxs-lookup"><span data-stu-id="b4c66-134">\<namedPipeTransport></span></span>](namedpipetransport.md)|<span data-ttu-id="b4c66-135">Определяет транспорт, вызывающий передачу сообщений с использованием именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="b4c66-135">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4c66-136">См. также</span><span class="sxs-lookup"><span data-stu-id="b4c66-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b4c66-137">Транспорты</span><span class="sxs-lookup"><span data-stu-id="b4c66-137">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="b4c66-138">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="b4c66-138">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="b4c66-139">Привязки</span><span class="sxs-lookup"><span data-stu-id="b4c66-139">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b4c66-140">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="b4c66-140">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b4c66-141">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="b4c66-141">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b4c66-142">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b4c66-142">\<customBinding></span></span>](custombinding.md)
