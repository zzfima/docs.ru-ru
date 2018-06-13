---
title: 216 - MessageSentByTransport
ms.date: 03/30/2017
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
ms.openlocfilehash: fa21568e4c8c38eefe359c417d47ec0a9d30a7c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458687"
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="e4118-102">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="e4118-102">216 - MessageSentByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="e4118-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="e4118-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e4118-104">ID</span><span class="sxs-lookup"><span data-stu-id="e4118-104">ID</span></span>|<span data-ttu-id="e4118-105">216</span><span class="sxs-lookup"><span data-stu-id="e4118-105">216</span></span>|  
|<span data-ttu-id="e4118-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e4118-106">Keywords</span></span>|<span data-ttu-id="e4118-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e4118-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="e4118-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="e4118-108">Level</span></span>|<span data-ttu-id="e4118-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="e4118-109">Information</span></span>|  
|<span data-ttu-id="e4118-110">Канал</span><span class="sxs-lookup"><span data-stu-id="e4118-110">Channel</span></span>|<span data-ttu-id="e4118-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e4118-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e4118-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e4118-112">Description</span></span>  
 <span data-ttu-id="e4118-113">Это событие возникает при отправке сообщения транспортом на основе TCP.</span><span class="sxs-lookup"><span data-stu-id="e4118-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="e4118-114">Обратите внимание, что в рамках одной операции между клиентом и службой может быть передано несколько сообщений уровня транспорта.</span><span class="sxs-lookup"><span data-stu-id="e4118-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="e4118-115">Это может быть вызвано особенностями инфраструктуры (и требования безопасности - хороший пример).</span><span class="sxs-lookup"><span data-stu-id="e4118-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="e4118-116">Таким образом, число **MessageSentByTransport** создаваемых событий зависит от привязки службы и его конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e4118-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e4118-117">Сообщение</span><span class="sxs-lookup"><span data-stu-id="e4118-117">Message</span></span>  
 <span data-ttu-id="e4118-118">Транспорт отправил сообщение «%1».</span><span class="sxs-lookup"><span data-stu-id="e4118-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e4118-119">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="e4118-119">Details</span></span>  
  
|<span data-ttu-id="e4118-120">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="e4118-120">Data Item Name</span></span>|<span data-ttu-id="e4118-121">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="e4118-121">Data Item Type</span></span>|<span data-ttu-id="e4118-122">Описание</span><span class="sxs-lookup"><span data-stu-id="e4118-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e4118-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="e4118-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="e4118-124">Адрес, на который было отправлено сообщение запроса.</span><span class="sxs-lookup"><span data-stu-id="e4118-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="e4118-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="e4118-125">HostReference</span></span>|<span data-ttu-id="e4118-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="e4118-126">xs:string</span></span>|<span data-ttu-id="e4118-127">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="e4118-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e4118-128">Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="e4118-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e4118-129">Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="e4118-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e4118-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e4118-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e4118-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e4118-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
