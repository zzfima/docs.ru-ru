---
title: 221 - MessageReceivedFromTransport
ms.date: 03/30/2017
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
ms.openlocfilehash: 98dbf2728242fa73b3e54b7cf32f9e227e5251b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781723"
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="834df-102">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="834df-102">221 - MessageReceivedFromTransport</span></span>
## <a name="properties"></a><span data-ttu-id="834df-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="834df-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="834df-104">ID</span><span class="sxs-lookup"><span data-stu-id="834df-104">ID</span></span>|<span data-ttu-id="834df-105">221</span><span class="sxs-lookup"><span data-stu-id="834df-105">221</span></span>|  
|<span data-ttu-id="834df-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="834df-106">Keywords</span></span>|<span data-ttu-id="834df-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="834df-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="834df-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="834df-108">Level</span></span>|<span data-ttu-id="834df-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="834df-109">Information</span></span>|  
|<span data-ttu-id="834df-110">Канал</span><span class="sxs-lookup"><span data-stu-id="834df-110">Channel</span></span>|<span data-ttu-id="834df-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="834df-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="834df-112">Описание</span><span class="sxs-lookup"><span data-stu-id="834df-112">Description</span></span>  
 <span data-ttu-id="834df-113">Это событие вызывается при получении моделью службы сообщения от транспортной подсистемы.</span><span class="sxs-lookup"><span data-stu-id="834df-113">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="834df-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="834df-114">Message</span></span>  
 <span data-ttu-id="834df-115">Диспетчер получил сообщение от транспорта.</span><span class="sxs-lookup"><span data-stu-id="834df-115">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="834df-116">Идентификатор корреляции == «%1».</span><span class="sxs-lookup"><span data-stu-id="834df-116">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="834df-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="834df-117">Details</span></span>  
  
|<span data-ttu-id="834df-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="834df-118">Data Item Name</span></span>|<span data-ttu-id="834df-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="834df-119">Data Item Type</span></span>|<span data-ttu-id="834df-120">Описание</span><span class="sxs-lookup"><span data-stu-id="834df-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="834df-121">Идентификатор корреляции</span><span class="sxs-lookup"><span data-stu-id="834df-121">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="834df-122">Идентификатор действия, используемый для корреляции события `MessageSentToTransport` из службы или клиента с соответствующим транспортом `MessageReceivedFromTransport` на другом конце.</span><span class="sxs-lookup"><span data-stu-id="834df-122">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="834df-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="834df-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="834df-124">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="834df-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="834df-125">Формат определяется как "виртуальный путь приложения имя веб-сайта&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="834df-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="834df-126">Пример "По умолчанию веб-сайт/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="834df-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="834df-127">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="834df-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="834df-128">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="834df-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
