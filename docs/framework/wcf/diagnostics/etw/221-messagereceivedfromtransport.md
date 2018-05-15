---
title: 221 - MessageReceivedFromTransport
ms.date: 03/30/2017
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
ms.openlocfilehash: 98dbf2728242fa73b3e54b7cf32f9e227e5251b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="a4b28-102">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="a4b28-102">221 - MessageReceivedFromTransport</span></span>
## <a name="properties"></a><span data-ttu-id="a4b28-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="a4b28-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a4b28-104">ID</span><span class="sxs-lookup"><span data-stu-id="a4b28-104">ID</span></span>|<span data-ttu-id="a4b28-105">221</span><span class="sxs-lookup"><span data-stu-id="a4b28-105">221</span></span>|  
|<span data-ttu-id="a4b28-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4b28-106">Keywords</span></span>|<span data-ttu-id="a4b28-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a4b28-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a4b28-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="a4b28-108">Level</span></span>|<span data-ttu-id="a4b28-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="a4b28-109">Information</span></span>|  
|<span data-ttu-id="a4b28-110">Канал</span><span class="sxs-lookup"><span data-stu-id="a4b28-110">Channel</span></span>|<span data-ttu-id="a4b28-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a4b28-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a4b28-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a4b28-112">Description</span></span>  
 <span data-ttu-id="a4b28-113">Это событие вызывается при получении моделью службы сообщения от транспортной подсистемы.</span><span class="sxs-lookup"><span data-stu-id="a4b28-113">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a4b28-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="a4b28-114">Message</span></span>  
 <span data-ttu-id="a4b28-115">Диспетчер получил сообщение от транспорта.</span><span class="sxs-lookup"><span data-stu-id="a4b28-115">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="a4b28-116">Идентификатор корреляции == «%1».</span><span class="sxs-lookup"><span data-stu-id="a4b28-116">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a4b28-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="a4b28-117">Details</span></span>  
  
|<span data-ttu-id="a4b28-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="a4b28-118">Data Item Name</span></span>|<span data-ttu-id="a4b28-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="a4b28-119">Data Item Type</span></span>|<span data-ttu-id="a4b28-120">Описание</span><span class="sxs-lookup"><span data-stu-id="a4b28-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a4b28-121">Идентификатор корреляции</span><span class="sxs-lookup"><span data-stu-id="a4b28-121">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="a4b28-122">Идентификатор действия, используемый для корреляции события `MessageSentToTransport` из службы или клиента с соответствующим транспортом `MessageReceivedFromTransport` на другом конце.</span><span class="sxs-lookup"><span data-stu-id="a4b28-122">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="a4b28-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="a4b28-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="a4b28-124">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="a4b28-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a4b28-125">Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="a4b28-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a4b28-126">Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="a4b28-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a4b28-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a4b28-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a4b28-128">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a4b28-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
