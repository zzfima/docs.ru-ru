---
title: ConnectionOrientedTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c0d399eb859118dfe94eb9e0a421fa405ae0f414
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="connectionorientedtransportbindingelement"></a><span data-ttu-id="eb011-102">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="eb011-102">ConnectionOrientedTransportBindingElement</span></span>
<span data-ttu-id="eb011-103">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="eb011-103">ConnectionOrientedTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb011-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb011-104">Syntax</span></span>  
  
```  
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="eb011-105">Методы</span><span class="sxs-lookup"><span data-stu-id="eb011-105">Methods</span></span>  
 <span data-ttu-id="eb011-106">Класс ConnectionOrientedTransportBindingElement не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="eb011-106">The ConnectionOrientedTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="eb011-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="eb011-107">Properties</span></span>  
 <span data-ttu-id="eb011-108">Класс ConnectionOrientedTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="eb011-108">The ConnectionOrientedTransportBindingElement class has the following properties:</span></span>  
  
### <a name="channelinitializationtimeout"></a><span data-ttu-id="eb011-109">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="eb011-109">ChannelInitializationTimeout</span></span>  
 <span data-ttu-id="eb011-110">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="eb011-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="eb011-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="eb011-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eb011-112">Задает интервал времени, который выделяется для инициализации канала до возникновения тайм-аута.</span><span class="sxs-lookup"><span data-stu-id="eb011-112">The timespan that specifies how long the channel initialization has to complete before timing out.</span></span>  
  
### <a name="connectionbuffersize"></a><span data-ttu-id="eb011-113">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="eb011-113">ConnectionBufferSize</span></span>  
 <span data-ttu-id="eb011-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="eb011-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="eb011-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="eb011-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eb011-116">Размер буфера, используемого для передачи по сети фрагмента сериализованного сообщения от клиента серверу.</span><span class="sxs-lookup"><span data-stu-id="eb011-116">The size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="eb011-117">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="eb011-117">HostNameComparisonMode</span></span>  
 <span data-ttu-id="eb011-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="eb011-118">Data type: string</span></span>  
  
 <span data-ttu-id="eb011-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="eb011-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eb011-120">Значение, указывающее, используется ли имя узла для доступа к службе при сопоставлении по универсальному коду ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="eb011-120">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="eb011-121">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="eb011-121">MaxBufferSize</span></span>  
 <span data-ttu-id="eb011-122">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="eb011-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="eb011-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="eb011-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eb011-124">Максимально используемый размер буфера.</span><span class="sxs-lookup"><span data-stu-id="eb011-124">The maximum size of the buffer to use.</span></span>  
  
### <a name="maxoutputdelay"></a><span data-ttu-id="eb011-125">MaxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="eb011-125">MaxOutputDelay</span></span>  
 <span data-ttu-id="eb011-126">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="eb011-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="eb011-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="eb011-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eb011-128">Максимальный промежуток времени, в течение которого фрагмент сообщения или все сообщение может оставаться в буфере перед отправкой.</span><span class="sxs-lookup"><span data-stu-id="eb011-128">The maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>  
  
### <a name="maxpendingaccepts"></a><span data-ttu-id="eb011-129">MaxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="eb011-129">MaxPendingAccepts</span></span>  
 <span data-ttu-id="eb011-130">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="eb011-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="eb011-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="eb011-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eb011-132">Максимальное число ожидающих асинхронных потоков приема, доступных для обработки входящих подключений к службе.</span><span class="sxs-lookup"><span data-stu-id="eb011-132">The maximum number of pending asynchronous accept threads that are available for processing incoming connections on the service.</span></span>  
  
### <a name="maxpendingconnections"></a><span data-ttu-id="eb011-133">MaxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="eb011-133">MaxPendingConnections</span></span>  
 <span data-ttu-id="eb011-134">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="eb011-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="eb011-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="eb011-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eb011-136">Максимальное количество ожидающих подключений.</span><span class="sxs-lookup"><span data-stu-id="eb011-136">The maximum number of pending connections.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="eb011-137">TransferMode</span><span class="sxs-lookup"><span data-stu-id="eb011-137">TransferMode</span></span>  
 <span data-ttu-id="eb011-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="eb011-138">Data type: string</span></span>  
  
 <span data-ttu-id="eb011-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="eb011-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eb011-140">Значение, указывающее, следует ли буферизировать сообщения, или передавать их потоком с использованием транспорта, ориентированного на подключения.</span><span class="sxs-lookup"><span data-stu-id="eb011-140">A value that specifies whether the messages are buffered or streamed with the connection-oriented transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb011-141">Требования</span><span class="sxs-lookup"><span data-stu-id="eb011-141">Requirements</span></span>  
  
|<span data-ttu-id="eb011-142">MOF</span><span class="sxs-lookup"><span data-stu-id="eb011-142">MOF</span></span>|<span data-ttu-id="eb011-143">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="eb011-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="eb011-144">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="eb011-144">Namespace</span></span>|<span data-ttu-id="eb011-145">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="eb011-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb011-146">См. также</span><span class="sxs-lookup"><span data-stu-id="eb011-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
