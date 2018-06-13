---
title: 218 - ClientOperationCompleted
ms.date: 03/30/2017
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
ms.openlocfilehash: 83f39be84a8d62962b85652b0e39b537c92e612c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457978"
---
# <a name="218---clientoperationcompleted"></a><span data-ttu-id="bc934-102">218 - ClientOperationCompleted</span><span class="sxs-lookup"><span data-stu-id="bc934-102">218 - ClientOperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="bc934-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="bc934-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bc934-104">ID</span><span class="sxs-lookup"><span data-stu-id="bc934-104">ID</span></span>|<span data-ttu-id="bc934-105">218</span><span class="sxs-lookup"><span data-stu-id="bc934-105">218</span></span>|  
|<span data-ttu-id="bc934-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="bc934-106">Keywords</span></span>|<span data-ttu-id="bc934-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bc934-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="bc934-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="bc934-108">Level</span></span>|<span data-ttu-id="bc934-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="bc934-109">Information</span></span>|  
|<span data-ttu-id="bc934-110">Канал</span><span class="sxs-lookup"><span data-stu-id="bc934-110">Channel</span></span>|<span data-ttu-id="bc934-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="bc934-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bc934-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bc934-112">Description</span></span>  
 <span data-ttu-id="bc934-113">Это событие создается клиентом сразу после завершения операции.</span><span class="sxs-lookup"><span data-stu-id="bc934-113">This event is emitted by clients just after an operation completes.</span></span> <span data-ttu-id="bc934-114">Для односторонних операций оно создается сразу после успешной отправки сообщения.</span><span class="sxs-lookup"><span data-stu-id="bc934-114">For one-way operations, this is just after the message is sent successfully.</span></span> <span data-ttu-id="bc934-115">Для операций типа «запрос-ответ» оно создается после получения ответа.</span><span class="sxs-lookup"><span data-stu-id="bc934-115">For request-response operations this is after the response is received.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bc934-116">Сообщение</span><span class="sxs-lookup"><span data-stu-id="bc934-116">Message</span></span>  
 <span data-ttu-id="bc934-117">Клиент завершил выполнение действия «%1», связанного с контрактом «%2».</span><span class="sxs-lookup"><span data-stu-id="bc934-117">The Client completed executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="bc934-118">Сообщение было отправлено «%3».</span><span class="sxs-lookup"><span data-stu-id="bc934-118">The message was sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bc934-119">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="bc934-119">Details</span></span>  
  
|<span data-ttu-id="bc934-120">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="bc934-120">Data Item Name</span></span>|<span data-ttu-id="bc934-121">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="bc934-121">Data Item Type</span></span>|<span data-ttu-id="bc934-122">Описание</span><span class="sxs-lookup"><span data-stu-id="bc934-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bc934-123">Действие</span><span class="sxs-lookup"><span data-stu-id="bc934-123">Action</span></span>|<span data-ttu-id="bc934-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="bc934-124">xs:string</span></span>|<span data-ttu-id="bc934-125">Заголовок действия SOAP исходящего сообщения.</span><span class="sxs-lookup"><span data-stu-id="bc934-125">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="bc934-126">Contract Name</span><span class="sxs-lookup"><span data-stu-id="bc934-126">Contract Name</span></span>|`xs:string`|<span data-ttu-id="bc934-127">Имя контракта.</span><span class="sxs-lookup"><span data-stu-id="bc934-127">The name of the contract.</span></span> <span data-ttu-id="bc934-128">Пример: ICalculator.</span><span class="sxs-lookup"><span data-stu-id="bc934-128">Example: ICalculator.</span></span>|  
|<span data-ttu-id="bc934-129">Назначение</span><span class="sxs-lookup"><span data-stu-id="bc934-129">Destination</span></span>|`xs:string`|<span data-ttu-id="bc934-130">Адрес конечной точки службы, которой было отправлено сообщение.</span><span class="sxs-lookup"><span data-stu-id="bc934-130">The address of the service endpoint that the message was sent to.</span></span>|  
|<span data-ttu-id="bc934-131">HostReference</span><span class="sxs-lookup"><span data-stu-id="bc934-131">HostReference</span></span>|`xs:string`|<span data-ttu-id="bc934-132">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="bc934-132">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="bc934-133">Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="bc934-133">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="bc934-134">Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="bc934-134">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="bc934-135">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bc934-135">AppDomain</span></span>|`xs:string`|<span data-ttu-id="bc934-136">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="bc934-136">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
