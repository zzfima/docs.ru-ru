---
title: ConnectionOrientedTransportBindingElement
ms.date: 03/30/2017
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
ms.openlocfilehash: 04e6abc5941ec99769ff2c15d47881b60e81d2e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62048404"
---
# <a name="connectionorientedtransportbindingelement"></a><span data-ttu-id="fb11c-102">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="fb11c-102">ConnectionOrientedTransportBindingElement</span></span>
<span data-ttu-id="fb11c-103">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="fb11c-103">ConnectionOrientedTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb11c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb11c-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="fb11c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="fb11c-105">Methods</span></span>  
 <span data-ttu-id="fb11c-106">Класс ConnectionOrientedTransportBindingElement не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="fb11c-106">The ConnectionOrientedTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fb11c-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="fb11c-107">Properties</span></span>  
 <span data-ttu-id="fb11c-108">Класс ConnectionOrientedTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="fb11c-108">The ConnectionOrientedTransportBindingElement class has the following properties:</span></span>  
  
### <a name="channelinitializationtimeout"></a><span data-ttu-id="fb11c-109">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="fb11c-109">ChannelInitializationTimeout</span></span>  
 <span data-ttu-id="fb11c-110">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="fb11c-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="fb11c-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="fb11c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11c-112">Задает интервал времени, который выделяется для инициализации канала до возникновения тайм-аута.</span><span class="sxs-lookup"><span data-stu-id="fb11c-112">The timespan that specifies how long the channel initialization has to complete before timing out.</span></span>  
  
### <a name="connectionbuffersize"></a><span data-ttu-id="fb11c-113">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="fb11c-113">ConnectionBufferSize</span></span>  
 <span data-ttu-id="fb11c-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="fb11c-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="fb11c-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="fb11c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11c-116">Размер буфера, используемого для передачи по сети фрагмента сериализованного сообщения от клиента серверу.</span><span class="sxs-lookup"><span data-stu-id="fb11c-116">The size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="fb11c-117">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="fb11c-117">HostNameComparisonMode</span></span>  
 <span data-ttu-id="fb11c-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="fb11c-118">Data type: string</span></span>  
  
 <span data-ttu-id="fb11c-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="fb11c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11c-120">Значение, указывающее, используется ли имя узла для доступа к службе при сопоставлении по универсальному коду ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="fb11c-120">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="fb11c-121">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="fb11c-121">MaxBufferSize</span></span>  
 <span data-ttu-id="fb11c-122">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="fb11c-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="fb11c-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="fb11c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11c-124">Максимально используемый размер буфера.</span><span class="sxs-lookup"><span data-stu-id="fb11c-124">The maximum size of the buffer to use.</span></span>  
  
### <a name="maxoutputdelay"></a><span data-ttu-id="fb11c-125">MaxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="fb11c-125">MaxOutputDelay</span></span>  
 <span data-ttu-id="fb11c-126">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="fb11c-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="fb11c-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="fb11c-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11c-128">Максимальный промежуток времени, в течение которого фрагмент сообщения или все сообщение может оставаться в буфере перед отправкой.</span><span class="sxs-lookup"><span data-stu-id="fb11c-128">The maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>  
  
### <a name="maxpendingaccepts"></a><span data-ttu-id="fb11c-129">MaxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="fb11c-129">MaxPendingAccepts</span></span>  
 <span data-ttu-id="fb11c-130">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="fb11c-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="fb11c-131">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="fb11c-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11c-132">Максимальное число ожидающих асинхронных потоков приема, доступных для обработки входящих подключений к службе.</span><span class="sxs-lookup"><span data-stu-id="fb11c-132">The maximum number of pending asynchronous accept threads that are available for processing incoming connections on the service.</span></span>  
  
### <a name="maxpendingconnections"></a><span data-ttu-id="fb11c-133">MaxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="fb11c-133">MaxPendingConnections</span></span>  
 <span data-ttu-id="fb11c-134">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="fb11c-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="fb11c-135">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="fb11c-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11c-136">Максимальное количество ожидающих подключений.</span><span class="sxs-lookup"><span data-stu-id="fb11c-136">The maximum number of pending connections.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="fb11c-137">TransferMode</span><span class="sxs-lookup"><span data-stu-id="fb11c-137">TransferMode</span></span>  
 <span data-ttu-id="fb11c-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="fb11c-138">Data type: string</span></span>  
  
 <span data-ttu-id="fb11c-139">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="fb11c-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb11c-140">Значение, указывающее, следует ли буферизировать сообщения, или передавать их потоком с использованием транспорта, ориентированного на подключения.</span><span class="sxs-lookup"><span data-stu-id="fb11c-140">A value that specifies whether the messages are buffered or streamed with the connection-oriented transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb11c-141">Требования</span><span class="sxs-lookup"><span data-stu-id="fb11c-141">Requirements</span></span>  
  
|<span data-ttu-id="fb11c-142">MOF</span><span class="sxs-lookup"><span data-stu-id="fb11c-142">MOF</span></span>|<span data-ttu-id="fb11c-143">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fb11c-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fb11c-144">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="fb11c-144">Namespace</span></span>|<span data-ttu-id="fb11c-145">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="fb11c-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb11c-146">См. также</span><span class="sxs-lookup"><span data-stu-id="fb11c-146">See also</span></span>

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
