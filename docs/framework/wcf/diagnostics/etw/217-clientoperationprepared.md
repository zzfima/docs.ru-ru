---
title: 217 - ClientOperationPrepared
ms.date: 03/30/2017
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
ms.openlocfilehash: 5979cd8ffe0e05b61af01d2aa98c4a2c63fd432c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781771"
---
# <a name="217---clientoperationprepared"></a><span data-ttu-id="a116f-102">217 - ClientOperationPrepared</span><span class="sxs-lookup"><span data-stu-id="a116f-102">217 - ClientOperationPrepared</span></span>
## <a name="properties"></a><span data-ttu-id="a116f-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="a116f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a116f-104">ID</span><span class="sxs-lookup"><span data-stu-id="a116f-104">ID</span></span>|<span data-ttu-id="a116f-105">217</span><span class="sxs-lookup"><span data-stu-id="a116f-105">217</span></span>|  
|<span data-ttu-id="a116f-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a116f-106">Keywords</span></span>|<span data-ttu-id="a116f-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a116f-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a116f-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="a116f-108">Level</span></span>|<span data-ttu-id="a116f-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="a116f-109">Information</span></span>|  
|<span data-ttu-id="a116f-110">Канал</span><span class="sxs-lookup"><span data-stu-id="a116f-110">Channel</span></span>|<span data-ttu-id="a116f-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a116f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a116f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a116f-112">Description</span></span>  
 <span data-ttu-id="a116f-113">Это событие создается клиентом непосредственно перед отправкой операции службе.</span><span class="sxs-lookup"><span data-stu-id="a116f-113">This event is emitted by clients just before an operation is sent to the service.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a116f-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="a116f-114">Message</span></span>  
 <span data-ttu-id="a116f-115">Клиент выполняет действие «%1», связанное с контрактом «%2».</span><span class="sxs-lookup"><span data-stu-id="a116f-115">The Client is executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="a116f-116">Сообщение будет отправлено «%3».</span><span class="sxs-lookup"><span data-stu-id="a116f-116">The message will be sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a116f-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="a116f-117">Details</span></span>  
  
|<span data-ttu-id="a116f-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="a116f-118">Data Item Name</span></span>|<span data-ttu-id="a116f-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="a116f-119">Data Item Type</span></span>|<span data-ttu-id="a116f-120">Описание</span><span class="sxs-lookup"><span data-stu-id="a116f-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a116f-121">Действие</span><span class="sxs-lookup"><span data-stu-id="a116f-121">Action</span></span>|`xs:string`|<span data-ttu-id="a116f-122">Заголовок действия SOAP исходящего сообщения.</span><span class="sxs-lookup"><span data-stu-id="a116f-122">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="a116f-123">Contract Name</span><span class="sxs-lookup"><span data-stu-id="a116f-123">Contract Name</span></span>|`xs:string`|<span data-ttu-id="a116f-124">Имя контракта.</span><span class="sxs-lookup"><span data-stu-id="a116f-124">The name of the contract.</span></span> <span data-ttu-id="a116f-125">Пример ICalculator.</span><span class="sxs-lookup"><span data-stu-id="a116f-125">Example: ICalculator.</span></span>|  
|<span data-ttu-id="a116f-126">Назначение</span><span class="sxs-lookup"><span data-stu-id="a116f-126">Destination</span></span>|`xs:string`|<span data-ttu-id="a116f-127">Адрес конечной точки службы, которой отправляется сообщение.</span><span class="sxs-lookup"><span data-stu-id="a116f-127">The address of the service endpoint that the message is sent to.</span></span>|  
|<span data-ttu-id="a116f-128">HostReference</span><span class="sxs-lookup"><span data-stu-id="a116f-128">HostReference</span></span>|`xs:string`|<span data-ttu-id="a116f-129">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="a116f-129">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a116f-130">Формат определяется как "виртуальный путь приложения имя веб-сайта&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="a116f-130">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a116f-131">Пример "По умолчанию веб-сайт/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="a116f-131">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a116f-132">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="a116f-132">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a116f-133">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a116f-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
