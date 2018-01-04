---
title: MsmqBindingElementBase
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 10e476931ef07ec694dff200e64ce2ded74c8dfb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="msmqbindingelementbase"></a><span data-ttu-id="8cc70-102">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="8cc70-102">MsmqBindingElementBase</span></span>
<span data-ttu-id="8cc70-103">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="8cc70-103">MsmqBindingElementBase</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cc70-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8cc70-104">Syntax</span></span>  
  
```  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8cc70-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8cc70-105">Methods</span></span>  
 <span data-ttu-id="8cc70-106">Класс MsmqBindingElementBase не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="8cc70-106">The MsmqBindingElementBase class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8cc70-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="8cc70-107">Properties</span></span>  
 <span data-ttu-id="8cc70-108">Класс MsmqBindingElementBase имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="8cc70-108">The MsmqBindingElementBase class has the following properties:</span></span>  
  
### <a name="customdeadletterqueue"></a><span data-ttu-id="8cc70-109">CustomDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="8cc70-109">CustomDeadLetterQueue</span></span>  
 <span data-ttu-id="8cc70-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8cc70-110">Data type: string</span></span>  
  
 <span data-ttu-id="8cc70-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8cc70-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8cc70-112">Универсальный код ресурса (URI), содержащий местоположение очереди недоставленных сообщений для каждого приложения; в эту очередь помещаются просроченные сообщения или сообщения, которые не удалось передать или доставить.</span><span class="sxs-lookup"><span data-stu-id="8cc70-112">A URI that contains the location of the dead letter queue for each application, where messages that have expired or that have failed transfer or delivery are placed.</span></span>  
  
### <a name="deadletterqueue"></a><span data-ttu-id="8cc70-113">DeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="8cc70-113">DeadLetterQueue</span></span>  
 <span data-ttu-id="8cc70-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8cc70-114">Data type: string</span></span>  
  
 <span data-ttu-id="8cc70-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8cc70-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8cc70-116">Значение перечисления, указывающее тип используемой очереди недоставленных сообщений.</span><span class="sxs-lookup"><span data-stu-id="8cc70-116">An enumeration value that indicates the type of dead letter queue to use.</span></span>  
  
### <a name="durable"></a><span data-ttu-id="8cc70-117">Durable</span><span class="sxs-lookup"><span data-stu-id="8cc70-117">Durable</span></span>  
 <span data-ttu-id="8cc70-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="8cc70-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="8cc70-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8cc70-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8cc70-120">Значение, указывающее, являются ли сообщения, обрабатываемые этой привязкой, устойчивыми или неустойчивыми.</span><span class="sxs-lookup"><span data-stu-id="8cc70-120">A value that indicates whether the messages processed by this binding are durable or volatile.</span></span>  
  
### <a name="exactlyonce"></a><span data-ttu-id="8cc70-121">ExactlyOnce</span><span class="sxs-lookup"><span data-stu-id="8cc70-121">ExactlyOnce</span></span>  
 <span data-ttu-id="8cc70-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="8cc70-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="8cc70-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8cc70-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8cc70-124">Логическое значение, указывающее, доставляются ли сообщения, обрабатываемые этой привязкой, только один раз.</span><span class="sxs-lookup"><span data-stu-id="8cc70-124">A Boolean value that indicates whether messages processed by this binding are received exactly once.</span></span>  
  
### <a name="maxretrycycles"></a><span data-ttu-id="8cc70-125">MaxRetryCycles</span><span class="sxs-lookup"><span data-stu-id="8cc70-125">MaxRetryCycles</span></span>  
 <span data-ttu-id="8cc70-126">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="8cc70-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="8cc70-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8cc70-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8cc70-128">Максимальное количество циклов повторных попыток доставить сообщение принимающему приложению.</span><span class="sxs-lookup"><span data-stu-id="8cc70-128">The maximum number of retry cycles to attempt delivery of messages to the receiving application.</span></span>  
  
### <a name="receiveerrorhandling"></a><span data-ttu-id="8cc70-129">ReceiveErrorHandling</span><span class="sxs-lookup"><span data-stu-id="8cc70-129">ReceiveErrorHandling</span></span>  
 <span data-ttu-id="8cc70-130">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8cc70-130">Data type: string</span></span>  
  
 <span data-ttu-id="8cc70-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8cc70-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8cc70-132">Параметры обработки подозрительных сообщений.</span><span class="sxs-lookup"><span data-stu-id="8cc70-132">The settings for poison message handling.</span></span>  
  
### <a name="receiveretrycount"></a><span data-ttu-id="8cc70-133">ReceiveRetryCount</span><span class="sxs-lookup"><span data-stu-id="8cc70-133">ReceiveRetryCount</span></span>  
 <span data-ttu-id="8cc70-134">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="8cc70-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="8cc70-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8cc70-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8cc70-136">Максимальное количество немедленных повторных попыток считывания сообщения из очереди приложения.</span><span class="sxs-lookup"><span data-stu-id="8cc70-136">The maximum number of immediate retry attempts on a message that is read from the application queue.</span></span>  
  
### <a name="retrycycledelay"></a><span data-ttu-id="8cc70-137">RetryCycleDelay</span><span class="sxs-lookup"><span data-stu-id="8cc70-137">RetryCycleDelay</span></span>  
 <span data-ttu-id="8cc70-138">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="8cc70-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="8cc70-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8cc70-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8cc70-140">Значение, указывающее временную задержку между циклами повторных попыток доставить сообщение, которое не удалось доставить немедленно.</span><span class="sxs-lookup"><span data-stu-id="8cc70-140">A value that indicates the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span>  
  
### <a name="timetolive"></a><span data-ttu-id="8cc70-141">TimeToLive</span><span class="sxs-lookup"><span data-stu-id="8cc70-141">TimeToLive</span></span>  
 <span data-ttu-id="8cc70-142">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="8cc70-142">Data type: datetime</span></span>  
  
 <span data-ttu-id="8cc70-143">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8cc70-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8cc70-144">Промежуток времени, соответствующий максимальному сроку нахождения в очереди сообщений, обрабатываемых этой привязкой.</span><span class="sxs-lookup"><span data-stu-id="8cc70-144">The interval of time that indicates how long the messages processed by this binding can be in the queue before they expire.</span></span>  
  
### <a name="usemsmqtracing"></a><span data-ttu-id="8cc70-145">UseMsmqTracing</span><span class="sxs-lookup"><span data-stu-id="8cc70-145">UseMsmqTracing</span></span>  
 <span data-ttu-id="8cc70-146">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="8cc70-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="8cc70-147">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8cc70-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8cc70-148">Логическое значение, указывающее, следует ли трассировать сообщения, обрабатываемые этой привязкой.</span><span class="sxs-lookup"><span data-stu-id="8cc70-148">A Boolean value that indicates whether messages processed by this binding should be traced.</span></span>  
  
### <a name="usesourcejournal"></a><span data-ttu-id="8cc70-149">UseSourceJournal</span><span class="sxs-lookup"><span data-stu-id="8cc70-149">UseSourceJournal</span></span>  
 <span data-ttu-id="8cc70-150">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="8cc70-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="8cc70-151">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8cc70-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8cc70-152">Логическое значение, указывающее, должны ли сохраняться в очереди журнала источника копии сообщений, обрабатываемых этой привязкой.</span><span class="sxs-lookup"><span data-stu-id="8cc70-152">A Boolean value that indicates whether copies of messages processed by this binding should be stored in the source journal queue.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cc70-153">Требования</span><span class="sxs-lookup"><span data-stu-id="8cc70-153">Requirements</span></span>  
  
|<span data-ttu-id="8cc70-154">MOF</span><span class="sxs-lookup"><span data-stu-id="8cc70-154">MOF</span></span>|<span data-ttu-id="8cc70-155">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8cc70-155">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8cc70-156">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="8cc70-156">Namespace</span></span>|<span data-ttu-id="8cc70-157">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="8cc70-157">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8cc70-158">См. также</span><span class="sxs-lookup"><span data-stu-id="8cc70-158">See Also</span></span>  
 <xref:System.ServiceModel.NetMsmqBinding>  
 <xref:System.ServiceModel.MsmqBindingBase>
