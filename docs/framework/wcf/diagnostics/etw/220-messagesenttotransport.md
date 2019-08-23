---
title: 220 - MessageSentToTransport
ms.date: 03/30/2017
ms.assetid: aef4e781-240b-45bc-bff8-400053037e71
ms.openlocfilehash: 9f95edf42e0b1ec19d2019773def282fc279871b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948286"
---
# <a name="220---messagesenttotransport"></a><span data-ttu-id="216b0-102">220 - MessageSentToTransport</span><span class="sxs-lookup"><span data-stu-id="216b0-102">220 - MessageSentToTransport</span></span>
## <a name="properties"></a><span data-ttu-id="216b0-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="216b0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="216b0-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="216b0-104">Id</span></span>|<span data-ttu-id="216b0-105">220</span><span class="sxs-lookup"><span data-stu-id="216b0-105">220</span></span>|  
|<span data-ttu-id="216b0-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="216b0-106">Keywords</span></span>|<span data-ttu-id="216b0-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="216b0-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="216b0-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="216b0-108">Level</span></span>|<span data-ttu-id="216b0-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="216b0-109">Information</span></span>|  
|<span data-ttu-id="216b0-110">Канал</span><span class="sxs-lookup"><span data-stu-id="216b0-110">Channel</span></span>|<span data-ttu-id="216b0-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="216b0-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="216b0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="216b0-112">Description</span></span>  
 <span data-ttu-id="216b0-113">Это событие создается, когда модель службы отправляет сообщение в транспорт.</span><span class="sxs-lookup"><span data-stu-id="216b0-113">This event is emitted when the Service Model sends a message to the transport.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="216b0-114">Это событие не создается для односторонних транспортов.</span><span class="sxs-lookup"><span data-stu-id="216b0-114">This event will not be emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="216b0-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="216b0-115">Message</span></span>  
 <span data-ttu-id="216b0-116">Диспетчер отправил сообщение транспорту.</span><span class="sxs-lookup"><span data-stu-id="216b0-116">The Dispatcher sent a message to the transport.</span></span> <span data-ttu-id="216b0-117">Идентификатор корреляции == «%1».</span><span class="sxs-lookup"><span data-stu-id="216b0-117">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="216b0-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="216b0-118">Details</span></span>  
  
|<span data-ttu-id="216b0-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="216b0-119">Data Item Name</span></span>|<span data-ttu-id="216b0-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="216b0-120">Data Item Type</span></span>|<span data-ttu-id="216b0-121">Описание</span><span class="sxs-lookup"><span data-stu-id="216b0-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="216b0-122">Идентификатор корреляции</span><span class="sxs-lookup"><span data-stu-id="216b0-122">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="216b0-123">Идентификатор действия, используемый для корреляции события `MessageSentToTransport` из службы или клиента с соответствующим транспортом `MessageReceivedFromTransport` на другом конце.</span><span class="sxs-lookup"><span data-stu-id="216b0-123">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="216b0-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="216b0-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="216b0-125">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="216b0-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="216b0-126">Его формат определяется как "имя веб-сайта приложение виртуальный путь&#124;службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="216b0-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="216b0-127">Пример "Default Web site/Калкулатораппликатион&#124;/калкулаторсервице.СВК&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="216b0-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="216b0-128">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="216b0-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="216b0-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="216b0-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
