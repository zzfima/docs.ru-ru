---
title: 217 - ClientOperationPrepared
ms.date: 03/30/2017
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
ms.openlocfilehash: 5979cd8ffe0e05b61af01d2aa98c4a2c63fd432c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461069"
---
# <a name="217---clientoperationprepared"></a><span data-ttu-id="cebf5-102">217 - ClientOperationPrepared</span><span class="sxs-lookup"><span data-stu-id="cebf5-102">217 - ClientOperationPrepared</span></span>
## <a name="properties"></a><span data-ttu-id="cebf5-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="cebf5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cebf5-104">ID</span><span class="sxs-lookup"><span data-stu-id="cebf5-104">ID</span></span>|<span data-ttu-id="cebf5-105">217</span><span class="sxs-lookup"><span data-stu-id="cebf5-105">217</span></span>|  
|<span data-ttu-id="cebf5-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="cebf5-106">Keywords</span></span>|<span data-ttu-id="cebf5-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cebf5-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="cebf5-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="cebf5-108">Level</span></span>|<span data-ttu-id="cebf5-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="cebf5-109">Information</span></span>|  
|<span data-ttu-id="cebf5-110">Канал</span><span class="sxs-lookup"><span data-stu-id="cebf5-110">Channel</span></span>|<span data-ttu-id="cebf5-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="cebf5-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cebf5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="cebf5-112">Description</span></span>  
 <span data-ttu-id="cebf5-113">Это событие создается клиентом непосредственно перед отправкой операции службе.</span><span class="sxs-lookup"><span data-stu-id="cebf5-113">This event is emitted by clients just before an operation is sent to the service.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cebf5-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="cebf5-114">Message</span></span>  
 <span data-ttu-id="cebf5-115">Клиент выполняет действие «%1», связанное с контрактом «%2».</span><span class="sxs-lookup"><span data-stu-id="cebf5-115">The Client is executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="cebf5-116">Сообщение будет отправлено «%3».</span><span class="sxs-lookup"><span data-stu-id="cebf5-116">The message will be sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cebf5-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="cebf5-117">Details</span></span>  
  
|<span data-ttu-id="cebf5-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="cebf5-118">Data Item Name</span></span>|<span data-ttu-id="cebf5-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="cebf5-119">Data Item Type</span></span>|<span data-ttu-id="cebf5-120">Описание</span><span class="sxs-lookup"><span data-stu-id="cebf5-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cebf5-121">Действие</span><span class="sxs-lookup"><span data-stu-id="cebf5-121">Action</span></span>|`xs:string`|<span data-ttu-id="cebf5-122">Заголовок действия SOAP исходящего сообщения.</span><span class="sxs-lookup"><span data-stu-id="cebf5-122">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="cebf5-123">Contract Name</span><span class="sxs-lookup"><span data-stu-id="cebf5-123">Contract Name</span></span>|`xs:string`|<span data-ttu-id="cebf5-124">Имя контракта.</span><span class="sxs-lookup"><span data-stu-id="cebf5-124">The name of the contract.</span></span> <span data-ttu-id="cebf5-125">Пример: ICalculator.</span><span class="sxs-lookup"><span data-stu-id="cebf5-125">Example: ICalculator.</span></span>|  
|<span data-ttu-id="cebf5-126">Назначение</span><span class="sxs-lookup"><span data-stu-id="cebf5-126">Destination</span></span>|`xs:string`|<span data-ttu-id="cebf5-127">Адрес конечной точки службы, которой отправляется сообщение.</span><span class="sxs-lookup"><span data-stu-id="cebf5-127">The address of the service endpoint that the message is sent to.</span></span>|  
|<span data-ttu-id="cebf5-128">HostReference</span><span class="sxs-lookup"><span data-stu-id="cebf5-128">HostReference</span></span>|`xs:string`|<span data-ttu-id="cebf5-129">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="cebf5-129">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="cebf5-130">Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="cebf5-130">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="cebf5-131">Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="cebf5-131">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="cebf5-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cebf5-132">AppDomain</span></span>|`xs:string`|<span data-ttu-id="cebf5-133">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="cebf5-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
