---
title: ReliableSessionBindingElement
ms.date: 03/30/2017
ms.assetid: effda125-b8d3-4de6-8c0e-f59f5ea8f6eb
ms.openlocfilehash: 2f04e6794342d7bd0acd51481efcbeceb04fd459
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="reliablesessionbindingelement"></a><span data-ttu-id="785f8-102">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="785f8-102">ReliableSessionBindingElement</span></span>
<span data-ttu-id="785f8-103">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="785f8-103">ReliableSessionBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="785f8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="785f8-104">Syntax</span></span>  
  
```  
class ReliableSessionBindingElement : BindingElement  
{  
  datetime AcknowledgementInterval;  
  boolean FlowControlEnabled;  
  datetime InactivityTimeout;  
  sint32 MaxPendingChannels;  
  sint32 MaxRetryCount;  
  sint32 MaxTransferWindowSize;  
  boolean Ordered;  
  integer ReliableMessagingVersion;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="785f8-105">Методы</span><span class="sxs-lookup"><span data-stu-id="785f8-105">Methods</span></span>  
 <span data-ttu-id="785f8-106">Класс ReliableSessionBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="785f8-106">The ReliableSessionBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="785f8-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="785f8-107">Properties</span></span>  
 <span data-ttu-id="785f8-108">Класс ReliableSessionBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="785f8-108">The ReliableSessionBindingElement class has the following properties:</span></span>  
  
### <a name="acknowledgementinterval"></a><span data-ttu-id="785f8-109">AcknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="785f8-109">AcknowledgementInterval</span></span>  
 <span data-ttu-id="785f8-110">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="785f8-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="785f8-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="785f8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="785f8-112">Промежуток времени, в течение которого пункт назначения ожидает перед отправкой подтверждения источнику сообщения по надежным каналам, созданным фабрикой.</span><span class="sxs-lookup"><span data-stu-id="785f8-112">The interval of time that a destination waits before sending an acknowledgement to the message source on reliable channels that are created by the factory.</span></span>  
  
### <a name="flowcontrolenabled"></a><span data-ttu-id="785f8-113">FlowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="785f8-113">FlowControlEnabled</span></span>  
 <span data-ttu-id="785f8-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="785f8-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="785f8-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="785f8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="785f8-116">Логическое значение, указывающее, включено ли управление потоком.</span><span class="sxs-lookup"><span data-stu-id="785f8-116">A Boolean value that specifies whether flow control is enabled.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="785f8-117">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="785f8-117">InactivityTimeout</span></span>  
 <span data-ttu-id="785f8-118">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="785f8-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="785f8-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="785f8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="785f8-120">Максимальное время, в течение которого канал позволяет другому участнику соединения не отправлять никаких сообщений, прежде чем канал будет закрыт с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="785f8-120">Specifies the maximum duration the channel is going to allow the other communicating party not to send any messages before faulting the channel.</span></span>  
  
### <a name="maxpendingchannels"></a><span data-ttu-id="785f8-121">MaxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="785f8-121">MaxPendingChannels</span></span>  
 <span data-ttu-id="785f8-122">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="785f8-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="785f8-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="785f8-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="785f8-124">Максимальное число каналов, ожидающих принятия на прослушивателе.</span><span class="sxs-lookup"><span data-stu-id="785f8-124">The maximum number of channels that can wait to be accepted on the listener.</span></span>  
  
### <a name="maxretrycount"></a><span data-ttu-id="785f8-125">MaxRetryCount</span><span class="sxs-lookup"><span data-stu-id="785f8-125">MaxRetryCount</span></span>  
 <span data-ttu-id="785f8-126">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="785f8-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="785f8-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="785f8-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="785f8-128">Максимальное количество попыток повторной передачи надежным каналом сообщения, для которого не было получено подтверждение приема. Повторная передача осуществляется посредством вызова метода `Send` в базовом канале.</span><span class="sxs-lookup"><span data-stu-id="785f8-128">The maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgement for, by calling `Send` on its underlying channel.</span></span>  
  
### <a name="maxtransferwindowsize"></a><span data-ttu-id="785f8-129">MaxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="785f8-129">MaxTransferWindowSize</span></span>  
 <span data-ttu-id="785f8-130">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="785f8-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="785f8-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="785f8-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="785f8-132">Максимальный размер окна передачи для надежного сеанса.</span><span class="sxs-lookup"><span data-stu-id="785f8-132">The maximum transfer window size for the reliable session.</span></span>  
  
### <a name="ordered"></a><span data-ttu-id="785f8-133">Ordered</span><span class="sxs-lookup"><span data-stu-id="785f8-133">Ordered</span></span>  
 <span data-ttu-id="785f8-134">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="785f8-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="785f8-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="785f8-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="785f8-136">Логическое значение, определяющее, прибывают ли сообщения точно в том порядке, в котором они были отправлены.</span><span class="sxs-lookup"><span data-stu-id="785f8-136">A Boolean value that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span>  
  
### <a name="reliablemessagingversion"></a><span data-ttu-id="785f8-137">ReliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="785f8-137">ReliableMessagingVersion</span></span>  
 <span data-ttu-id="785f8-138">Тип данных: integer</span><span class="sxs-lookup"><span data-stu-id="785f8-138">Data type: integer</span></span>  
  
 <span data-ttu-id="785f8-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="785f8-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="785f8-140">Целочисленное значение, задающее версию используемого в надежном канале протокола WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="785f8-140">An integer that specifies the WS-ReliableMessaging protocol version used in the reliable session.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="785f8-141">Требования</span><span class="sxs-lookup"><span data-stu-id="785f8-141">Requirements</span></span>  
  
|<span data-ttu-id="785f8-142">MOF</span><span class="sxs-lookup"><span data-stu-id="785f8-142">MOF</span></span>|<span data-ttu-id="785f8-143">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="785f8-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="785f8-144">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="785f8-144">Namespace</span></span>|<span data-ttu-id="785f8-145">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="785f8-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="785f8-146">См. также</span><span class="sxs-lookup"><span data-stu-id="785f8-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
