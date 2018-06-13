---
title: 222 - OperationFailed
ms.date: 03/30/2017
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
ms.openlocfilehash: c49aad0f93ce47b66306d75741267530dc6d3fe5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460746"
---
# <a name="222---operationfailed"></a><span data-ttu-id="f91a4-102">222 - OperationFailed</span><span class="sxs-lookup"><span data-stu-id="f91a4-102">222 - OperationFailed</span></span>
## <a name="properties"></a><span data-ttu-id="f91a4-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="f91a4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f91a4-104">ID</span><span class="sxs-lookup"><span data-stu-id="f91a4-104">ID</span></span>|<span data-ttu-id="f91a4-105">222</span><span class="sxs-lookup"><span data-stu-id="f91a4-105">222</span></span>|  
|<span data-ttu-id="f91a4-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="f91a4-106">Keywords</span></span>|<span data-ttu-id="f91a4-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f91a4-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f91a4-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="f91a4-108">Level</span></span>|<span data-ttu-id="f91a4-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="f91a4-109">Warning</span></span>|  
|<span data-ttu-id="f91a4-110">Канал</span><span class="sxs-lookup"><span data-stu-id="f91a4-110">Channel</span></span>|<span data-ttu-id="f91a4-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f91a4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f91a4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f91a4-112">Description</span></span>  
 <span data-ttu-id="f91a4-113">Это событие создается в том случае, когда `OperationInvoker` модели службы по умолчанию обнаруживает исключение при вызове его метода.</span><span class="sxs-lookup"><span data-stu-id="f91a4-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception while invoking its method.</span></span> <span data-ttu-id="f91a4-114">Обратите внимание, что исключения, производные от `FaultException`, не вызывают это событие.</span><span class="sxs-lookup"><span data-stu-id="f91a4-114">Note that exceptions that derive from `FaultException` cause this event to not be emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f91a4-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f91a4-115">Message</span></span>  
 <span data-ttu-id="f91a4-116">Метод «%1» вызвал необработанное исключение после того, как был вызван OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="f91a4-116">The '%1' method threw an unhandled exception when invoked by the OperationInvoker.</span></span> <span data-ttu-id="f91a4-117">Длительность вызова метода составила «%2» мс.</span><span class="sxs-lookup"><span data-stu-id="f91a4-117">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f91a4-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="f91a4-118">Details</span></span>  
  
|<span data-ttu-id="f91a4-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="f91a4-119">Data Item Name</span></span>|<span data-ttu-id="f91a4-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="f91a4-120">Data Item Type</span></span>|<span data-ttu-id="f91a4-121">Описание</span><span class="sxs-lookup"><span data-stu-id="f91a4-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f91a4-122">Имя метода</span><span class="sxs-lookup"><span data-stu-id="f91a4-122">Method Name</span></span>|`xs:string`|<span data-ttu-id="f91a4-123">Имя CLR метода, который был вызван `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="f91a4-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="f91a4-124">Длительность</span><span class="sxs-lookup"><span data-stu-id="f91a4-124">Duration</span></span>|`xs:long`|<span data-ttu-id="f91a4-125">Время в миллисекундах, которое потребовалось `OperationInvoker`, чтобы вызвать метод.</span><span class="sxs-lookup"><span data-stu-id="f91a4-125">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="f91a4-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="f91a4-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="f91a4-127">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="f91a4-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f91a4-128">Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="f91a4-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f91a4-129">Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="f91a4-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f91a4-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f91a4-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f91a4-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f91a4-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
