---
title: 222 - OperationFailed
ms.date: 03/30/2017
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
ms.openlocfilehash: c49aad0f93ce47b66306d75741267530dc6d3fe5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781645"
---
# <a name="222---operationfailed"></a><span data-ttu-id="93f8c-102">222 - OperationFailed</span><span class="sxs-lookup"><span data-stu-id="93f8c-102">222 - OperationFailed</span></span>
## <a name="properties"></a><span data-ttu-id="93f8c-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="93f8c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="93f8c-104">ID</span><span class="sxs-lookup"><span data-stu-id="93f8c-104">ID</span></span>|<span data-ttu-id="93f8c-105">222</span><span class="sxs-lookup"><span data-stu-id="93f8c-105">222</span></span>|  
|<span data-ttu-id="93f8c-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="93f8c-106">Keywords</span></span>|<span data-ttu-id="93f8c-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="93f8c-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="93f8c-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="93f8c-108">Level</span></span>|<span data-ttu-id="93f8c-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="93f8c-109">Warning</span></span>|  
|<span data-ttu-id="93f8c-110">Канал</span><span class="sxs-lookup"><span data-stu-id="93f8c-110">Channel</span></span>|<span data-ttu-id="93f8c-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="93f8c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="93f8c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="93f8c-112">Description</span></span>  
 <span data-ttu-id="93f8c-113">Это событие создается в том случае, когда `OperationInvoker` модели службы по умолчанию обнаруживает исключение при вызове его метода.</span><span class="sxs-lookup"><span data-stu-id="93f8c-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception while invoking its method.</span></span> <span data-ttu-id="93f8c-114">Обратите внимание, что исключения, производные от `FaultException`, не вызывают это событие.</span><span class="sxs-lookup"><span data-stu-id="93f8c-114">Note that exceptions that derive from `FaultException` cause this event to not be emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="93f8c-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="93f8c-115">Message</span></span>  
 <span data-ttu-id="93f8c-116">Метод «%1» вызвал необработанное исключение после того, как был вызван OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="93f8c-116">The '%1' method threw an unhandled exception when invoked by the OperationInvoker.</span></span> <span data-ttu-id="93f8c-117">Длительность вызова метода составила «%2» мс.</span><span class="sxs-lookup"><span data-stu-id="93f8c-117">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="93f8c-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="93f8c-118">Details</span></span>  
  
|<span data-ttu-id="93f8c-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="93f8c-119">Data Item Name</span></span>|<span data-ttu-id="93f8c-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="93f8c-120">Data Item Type</span></span>|<span data-ttu-id="93f8c-121">Описание</span><span class="sxs-lookup"><span data-stu-id="93f8c-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="93f8c-122">Имя метода</span><span class="sxs-lookup"><span data-stu-id="93f8c-122">Method Name</span></span>|`xs:string`|<span data-ttu-id="93f8c-123">Имя CLR метода, который был вызван `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="93f8c-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="93f8c-124">Длительность</span><span class="sxs-lookup"><span data-stu-id="93f8c-124">Duration</span></span>|`xs:long`|<span data-ttu-id="93f8c-125">Время в миллисекундах, которое потребовалось `OperationInvoker`, чтобы вызвать метод.</span><span class="sxs-lookup"><span data-stu-id="93f8c-125">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="93f8c-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="93f8c-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="93f8c-127">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="93f8c-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="93f8c-128">Формат определяется как "виртуальный путь приложения имя веб-сайта&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="93f8c-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="93f8c-129">Пример "По умолчанию веб-сайт/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="93f8c-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="93f8c-130">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="93f8c-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="93f8c-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="93f8c-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
