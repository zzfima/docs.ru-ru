---
title: 216 - MessageSentByTransport
ms.date: 03/30/2017
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
ms.openlocfilehash: fa21568e4c8c38eefe359c417d47ec0a9d30a7c4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781814"
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="0e1bd-102">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="0e1bd-102">216 - MessageSentByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="0e1bd-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="0e1bd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0e1bd-104">ID</span><span class="sxs-lookup"><span data-stu-id="0e1bd-104">ID</span></span>|<span data-ttu-id="0e1bd-105">216</span><span class="sxs-lookup"><span data-stu-id="0e1bd-105">216</span></span>|  
|<span data-ttu-id="0e1bd-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="0e1bd-106">Keywords</span></span>|<span data-ttu-id="0e1bd-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0e1bd-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="0e1bd-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="0e1bd-108">Level</span></span>|<span data-ttu-id="0e1bd-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="0e1bd-109">Information</span></span>|  
|<span data-ttu-id="0e1bd-110">Канал</span><span class="sxs-lookup"><span data-stu-id="0e1bd-110">Channel</span></span>|<span data-ttu-id="0e1bd-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="0e1bd-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0e1bd-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0e1bd-112">Description</span></span>  
 <span data-ttu-id="0e1bd-113">Это событие возникает при отправке сообщения транспортом на основе TCP.</span><span class="sxs-lookup"><span data-stu-id="0e1bd-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="0e1bd-114">Обратите внимание, что в рамках одной операции между клиентом и службой может быть передано несколько сообщений уровня транспорта.</span><span class="sxs-lookup"><span data-stu-id="0e1bd-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="0e1bd-115">Это может быть вызвано особенностями инфраструктуры (и требования безопасности - хороший пример).</span><span class="sxs-lookup"><span data-stu-id="0e1bd-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="0e1bd-116">Таким образом, число **MessageSentByTransport** события, создаваемые различаются в зависимости от привязки службы и его конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0e1bd-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0e1bd-117">Сообщение</span><span class="sxs-lookup"><span data-stu-id="0e1bd-117">Message</span></span>  
 <span data-ttu-id="0e1bd-118">Транспорт отправил сообщение «%1».</span><span class="sxs-lookup"><span data-stu-id="0e1bd-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0e1bd-119">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="0e1bd-119">Details</span></span>  
  
|<span data-ttu-id="0e1bd-120">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="0e1bd-120">Data Item Name</span></span>|<span data-ttu-id="0e1bd-121">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="0e1bd-121">Data Item Type</span></span>|<span data-ttu-id="0e1bd-122">Описание</span><span class="sxs-lookup"><span data-stu-id="0e1bd-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0e1bd-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="0e1bd-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="0e1bd-124">Адрес, на который было отправлено сообщение запроса.</span><span class="sxs-lookup"><span data-stu-id="0e1bd-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="0e1bd-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="0e1bd-125">HostReference</span></span>|<span data-ttu-id="0e1bd-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="0e1bd-126">xs:string</span></span>|<span data-ttu-id="0e1bd-127">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="0e1bd-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="0e1bd-128">Формат определяется как "виртуальный путь приложения имя веб-сайта&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="0e1bd-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="0e1bd-129">Пример "По умолчанию веб-сайт/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="0e1bd-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="0e1bd-130">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="0e1bd-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0e1bd-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0e1bd-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
