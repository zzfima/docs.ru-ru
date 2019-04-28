---
title: 225 - TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: 0bb54387dbd738a01225008edfc45ecb7297cd00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755666"
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="2a3c6-102">225 - TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="2a3c6-102">225 - TraceCorrelationKeys</span></span>
## <a name="properties"></a><span data-ttu-id="2a3c6-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="2a3c6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2a3c6-104">ID</span><span class="sxs-lookup"><span data-stu-id="2a3c6-104">ID</span></span>|<span data-ttu-id="2a3c6-105">225</span><span class="sxs-lookup"><span data-stu-id="2a3c6-105">225</span></span>|  
|<span data-ttu-id="2a3c6-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2a3c6-106">Keywords</span></span>|<span data-ttu-id="2a3c6-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2a3c6-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="2a3c6-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="2a3c6-108">Level</span></span>|<span data-ttu-id="2a3c6-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="2a3c6-109">Information</span></span>|  
|<span data-ttu-id="2a3c6-110">Канал</span><span class="sxs-lookup"><span data-stu-id="2a3c6-110">Channel</span></span>|<span data-ttu-id="2a3c6-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="2a3c6-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2a3c6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2a3c6-112">Description</span></span>  
 <span data-ttu-id="2a3c6-113">Это событие создается, если в качестве службы рабочего процесса используется корреляция на основе содержимого.</span><span class="sxs-lookup"><span data-stu-id="2a3c6-113">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="2a3c6-114">Оно содержит ключи, применяемые для корреляции сообщения с экземпляром.</span><span class="sxs-lookup"><span data-stu-id="2a3c6-114">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2a3c6-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2a3c6-115">Message</span></span>  
 <span data-ttu-id="2a3c6-116">Вычисленный ключ корреляции «%1» с использованием значений «%2» в родительской области «%3».</span><span class="sxs-lookup"><span data-stu-id="2a3c6-116">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2a3c6-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="2a3c6-117">Details</span></span>  
  
|<span data-ttu-id="2a3c6-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="2a3c6-118">Data Item Name</span></span>|<span data-ttu-id="2a3c6-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="2a3c6-119">Data Item Type</span></span>|<span data-ttu-id="2a3c6-120">Описание</span><span class="sxs-lookup"><span data-stu-id="2a3c6-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2a3c6-121">Instance Key</span><span class="sxs-lookup"><span data-stu-id="2a3c6-121">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="2a3c6-122">Ключ, созданный из значений корреляции.</span><span class="sxs-lookup"><span data-stu-id="2a3c6-122">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="2a3c6-123">Значения</span><span class="sxs-lookup"><span data-stu-id="2a3c6-123">Values</span></span>|`xs:string`|<span data-ttu-id="2a3c6-124">Значения, использованные для вычисления ключа экземпляра корреляции.</span><span class="sxs-lookup"><span data-stu-id="2a3c6-124">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="2a3c6-125">Parent Scope</span><span class="sxs-lookup"><span data-stu-id="2a3c6-125">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="2a3c6-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="2a3c6-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="2a3c6-127">Для служб, размещенных на веб-узле, это поле служит уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="2a3c6-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="2a3c6-128">Формат определяется как "виртуальный путь приложения имя веб-сайта&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="2a3c6-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="2a3c6-129">Пример "По умолчанию веб-сайт/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="2a3c6-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="2a3c6-130">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="2a3c6-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2a3c6-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2a3c6-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
