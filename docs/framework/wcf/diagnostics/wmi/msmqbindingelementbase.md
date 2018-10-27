---
title: MsmqBindingElementBase
ms.date: 03/30/2017
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
ms.openlocfilehash: e7f4cf41168bd1e5483524195e20541d896a6569
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183195"
---
# <a name="msmqbindingelementbase"></a><span data-ttu-id="749eb-102">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="749eb-102">MsmqBindingElementBase</span></span>
<span data-ttu-id="749eb-103">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="749eb-103">MsmqBindingElementBase</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="749eb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="749eb-104">Syntax</span></span>  
  
```csharp  
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
  
## <a name="methods"></a><span data-ttu-id="749eb-105">Методы</span><span class="sxs-lookup"><span data-stu-id="749eb-105">Methods</span></span>  
 <span data-ttu-id="749eb-106">Класс MsmqBindingElementBase не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="749eb-106">The MsmqBindingElementBase class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="749eb-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="749eb-107">Properties</span></span>  
 <span data-ttu-id="749eb-108">Класс MsmqBindingElementBase имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="749eb-108">The MsmqBindingElementBase class has the following properties:</span></span>  
  
### <a name="customdeadletterqueue"></a><span data-ttu-id="749eb-109">CustomDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="749eb-109">CustomDeadLetterQueue</span></span>  
 <span data-ttu-id="749eb-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="749eb-110">Data type: string</span></span>  
  
 <span data-ttu-id="749eb-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="749eb-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="749eb-112">Универсальный код ресурса (URI), содержащий местоположение очереди недоставленных сообщений для каждого приложения; в эту очередь помещаются просроченные сообщения или сообщения, которые не удалось передать или доставить.</span><span class="sxs-lookup"><span data-stu-id="749eb-112">A URI that contains the location of the dead letter queue for each application, where messages that have expired or that have failed transfer or delivery are placed.</span></span>  
  
### <a name="deadletterqueue"></a><span data-ttu-id="749eb-113">DeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="749eb-113">DeadLetterQueue</span></span>  
 <span data-ttu-id="749eb-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="749eb-114">Data type: string</span></span>  
  
 <span data-ttu-id="749eb-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="749eb-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="749eb-116">Значение перечисления, указывающее тип используемой очереди недоставленных сообщений.</span><span class="sxs-lookup"><span data-stu-id="749eb-116">An enumeration value that indicates the type of dead letter queue to use.</span></span>  
  
### <a name="durable"></a><span data-ttu-id="749eb-117">Durable</span><span class="sxs-lookup"><span data-stu-id="749eb-117">Durable</span></span>  
 <span data-ttu-id="749eb-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="749eb-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="749eb-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="749eb-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="749eb-120">Значение, указывающее, являются ли сообщения, обрабатываемые этой привязкой, устойчивыми или неустойчивыми.</span><span class="sxs-lookup"><span data-stu-id="749eb-120">A value that indicates whether the messages processed by this binding are durable or volatile.</span></span>  
  
### <a name="exactlyonce"></a><span data-ttu-id="749eb-121">ExactlyOnce</span><span class="sxs-lookup"><span data-stu-id="749eb-121">ExactlyOnce</span></span>  
 <span data-ttu-id="749eb-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="749eb-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="749eb-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="749eb-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="749eb-124">Логическое значение, указывающее, доставляются ли сообщения, обрабатываемые этой привязкой, только один раз.</span><span class="sxs-lookup"><span data-stu-id="749eb-124">A Boolean value that indicates whether messages processed by this binding are received exactly once.</span></span>  
  
### <a name="maxretrycycles"></a><span data-ttu-id="749eb-125">MaxRetryCycles</span><span class="sxs-lookup"><span data-stu-id="749eb-125">MaxRetryCycles</span></span>  
 <span data-ttu-id="749eb-126">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="749eb-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="749eb-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="749eb-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="749eb-128">Максимальное количество циклов повторных попыток доставить сообщение принимающему приложению.</span><span class="sxs-lookup"><span data-stu-id="749eb-128">The maximum number of retry cycles to attempt delivery of messages to the receiving application.</span></span>  
  
### <a name="receiveerrorhandling"></a><span data-ttu-id="749eb-129">ReceiveErrorHandling</span><span class="sxs-lookup"><span data-stu-id="749eb-129">ReceiveErrorHandling</span></span>  
 <span data-ttu-id="749eb-130">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="749eb-130">Data type: string</span></span>  
  
 <span data-ttu-id="749eb-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="749eb-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="749eb-132">Параметры обработки подозрительных сообщений.</span><span class="sxs-lookup"><span data-stu-id="749eb-132">The settings for poison message handling.</span></span>  
  
### <a name="receiveretrycount"></a><span data-ttu-id="749eb-133">ReceiveRetryCount</span><span class="sxs-lookup"><span data-stu-id="749eb-133">ReceiveRetryCount</span></span>  
 <span data-ttu-id="749eb-134">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="749eb-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="749eb-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="749eb-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="749eb-136">Максимальное количество немедленных повторных попыток считывания сообщения из очереди приложения.</span><span class="sxs-lookup"><span data-stu-id="749eb-136">The maximum number of immediate retry attempts on a message that is read from the application queue.</span></span>  
  
### <a name="retrycycledelay"></a><span data-ttu-id="749eb-137">RetryCycleDelay</span><span class="sxs-lookup"><span data-stu-id="749eb-137">RetryCycleDelay</span></span>  
 <span data-ttu-id="749eb-138">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="749eb-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="749eb-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="749eb-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="749eb-140">Значение, указывающее временную задержку между циклами повторных попыток доставить сообщение, которое не удалось доставить немедленно.</span><span class="sxs-lookup"><span data-stu-id="749eb-140">A value that indicates the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span>  
  
### <a name="timetolive"></a><span data-ttu-id="749eb-141">TimeToLive</span><span class="sxs-lookup"><span data-stu-id="749eb-141">TimeToLive</span></span>  
 <span data-ttu-id="749eb-142">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="749eb-142">Data type: datetime</span></span>  
  
 <span data-ttu-id="749eb-143">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="749eb-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="749eb-144">Промежуток времени, соответствующий максимальному сроку нахождения в очереди сообщений, обрабатываемых этой привязкой.</span><span class="sxs-lookup"><span data-stu-id="749eb-144">The interval of time that indicates how long the messages processed by this binding can be in the queue before they expire.</span></span>  
  
### <a name="usemsmqtracing"></a><span data-ttu-id="749eb-145">UseMsmqTracing</span><span class="sxs-lookup"><span data-stu-id="749eb-145">UseMsmqTracing</span></span>  
 <span data-ttu-id="749eb-146">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="749eb-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="749eb-147">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="749eb-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="749eb-148">Логическое значение, указывающее, следует ли трассировать сообщения, обрабатываемые этой привязкой.</span><span class="sxs-lookup"><span data-stu-id="749eb-148">A Boolean value that indicates whether messages processed by this binding should be traced.</span></span>  
  
### <a name="usesourcejournal"></a><span data-ttu-id="749eb-149">UseSourceJournal</span><span class="sxs-lookup"><span data-stu-id="749eb-149">UseSourceJournal</span></span>  
 <span data-ttu-id="749eb-150">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="749eb-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="749eb-151">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="749eb-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="749eb-152">Логическое значение, указывающее, должны ли сохраняться в очереди журнала источника копии сообщений, обрабатываемых этой привязкой.</span><span class="sxs-lookup"><span data-stu-id="749eb-152">A Boolean value that indicates whether copies of messages processed by this binding should be stored in the source journal queue.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="749eb-153">Требования</span><span class="sxs-lookup"><span data-stu-id="749eb-153">Requirements</span></span>  
  
|<span data-ttu-id="749eb-154">MOF</span><span class="sxs-lookup"><span data-stu-id="749eb-154">MOF</span></span>|<span data-ttu-id="749eb-155">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="749eb-155">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="749eb-156">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="749eb-156">Namespace</span></span>|<span data-ttu-id="749eb-157">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="749eb-157">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="749eb-158">См. также</span><span class="sxs-lookup"><span data-stu-id="749eb-158">See Also</span></span>  
 <xref:System.ServiceModel.NetMsmqBinding>  
 <xref:System.ServiceModel.MsmqBindingBase>
