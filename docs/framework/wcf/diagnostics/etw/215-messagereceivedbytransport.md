---
title: 215 - MessageReceivedByTransport
ms.date: 03/30/2017
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
ms.openlocfilehash: a8ba90b88ef8dbe3c8651bc565da61aae16a0a4a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460907"
---
# <a name="215---messagereceivedbytransport"></a><span data-ttu-id="38528-102">215 - MessageReceivedByTransport</span><span class="sxs-lookup"><span data-stu-id="38528-102">215 - MessageReceivedByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="38528-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="38528-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="38528-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="38528-104">ID</span></span>|<span data-ttu-id="38528-105">215</span><span class="sxs-lookup"><span data-stu-id="38528-105">215</span></span>|  
|<span data-ttu-id="38528-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="38528-106">Keywords</span></span>|<span data-ttu-id="38528-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="38528-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="38528-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="38528-108">Level</span></span>|<span data-ttu-id="38528-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="38528-109">Information</span></span>|  
|<span data-ttu-id="38528-110">Канал</span><span class="sxs-lookup"><span data-stu-id="38528-110">Channel</span></span>|<span data-ttu-id="38528-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="38528-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="38528-112">Описание</span><span class="sxs-lookup"><span data-stu-id="38528-112">Description</span></span>  
 <span data-ttu-id="38528-113">Это событие происходит, когда транспорт на основе TCP получает сообщение.</span><span class="sxs-lookup"><span data-stu-id="38528-113">This event occurs when a TCP-based transport receives a message.</span></span> <span data-ttu-id="38528-114">Обратите внимание, что на транспортном уровне для одной операции между клиентом и службой может быть передано несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="38528-114">Note that at the transport level, multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="38528-115">Это может зависеть от инфраструктуры, и требования безопасности - хороший пример.</span><span class="sxs-lookup"><span data-stu-id="38528-115">This can be due to infrastructure behavior, security is a good example.</span></span> <span data-ttu-id="38528-116">Следовательно, количество создаваемых событий `MessageReceivedByTransport` может отличаться в зависимости от привязки службы и ее настроек.</span><span class="sxs-lookup"><span data-stu-id="38528-116">Therefore, the number of `MessageReceivedByTransport` events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38528-117">Это событие не создается для односторонних транспортов.</span><span class="sxs-lookup"><span data-stu-id="38528-117">This event is not emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="38528-118">Сообщение</span><span class="sxs-lookup"><span data-stu-id="38528-118">Message</span></span>  
 <span data-ttu-id="38528-119">Диспетчер получил сообщение от «%1».</span><span class="sxs-lookup"><span data-stu-id="38528-119">The transport received a message from '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="38528-120">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="38528-120">Details</span></span>  
  
|<span data-ttu-id="38528-121">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="38528-121">Data Item Name</span></span>|<span data-ttu-id="38528-122">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="38528-122">Data Item Type</span></span>|<span data-ttu-id="38528-123">Описание</span><span class="sxs-lookup"><span data-stu-id="38528-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="38528-124">Listen Address</span><span class="sxs-lookup"><span data-stu-id="38528-124">Listen Address</span></span>|`xs:string`|<span data-ttu-id="38528-125">Адрес, получивший сообщение.</span><span class="sxs-lookup"><span data-stu-id="38528-125">The address that received the message.</span></span>|  
|<span data-ttu-id="38528-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="38528-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="38528-127">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="38528-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="38528-128">Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="38528-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="38528-129">Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="38528-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="38528-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="38528-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="38528-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="38528-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
