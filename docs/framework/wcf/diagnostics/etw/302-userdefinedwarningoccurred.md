---
title: 302 - UserDefinedWarningOccurred
ms.date: 03/30/2017
ms.assetid: 8d1f0bf1-0151-45e6-be92-573d397b54de
ms.openlocfilehash: c70857951309ef54ba460e96e948c9320269d30f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61596756"
---
# <a name="302---userdefinedwarningoccurred"></a><span data-ttu-id="3ee6c-102">302 - UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="3ee6c-102">302 - UserDefinedWarningOccurred</span></span>
## <a name="properties"></a><span data-ttu-id="3ee6c-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="3ee6c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3ee6c-104">ID</span><span class="sxs-lookup"><span data-stu-id="3ee6c-104">ID</span></span>|<span data-ttu-id="3ee6c-105">302</span><span class="sxs-lookup"><span data-stu-id="3ee6c-105">302</span></span>|  
|<span data-ttu-id="3ee6c-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ee6c-106">Keywords</span></span>|<span data-ttu-id="3ee6c-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="3ee6c-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="3ee6c-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="3ee6c-108">Level</span></span>|<span data-ttu-id="3ee6c-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="3ee6c-109">Warning</span></span>|  
|<span data-ttu-id="3ee6c-110">Канал</span><span class="sxs-lookup"><span data-stu-id="3ee6c-110">Channel</span></span>|<span data-ttu-id="3ee6c-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="3ee6c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3ee6c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3ee6c-112">Description</span></span>  
 <span data-ttu-id="3ee6c-113">Это событие создается в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="3ee6c-113">This event is emitted from user code.</span></span> <span data-ttu-id="3ee6c-114">Разработчики могут создать это событие, если определенное пользователем событие предупреждения возникло в принадлежащей им службе.</span><span class="sxs-lookup"><span data-stu-id="3ee6c-114">Developers can emit this event when a custom-defined warning event occurs in their service.</span></span> <span data-ttu-id="3ee6c-115">Это можно сделать при помощи API-интерфейсов <xref:System.Diagnostics.Eventing>.</span><span class="sxs-lookup"><span data-stu-id="3ee6c-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="3ee6c-116">Помимо этого, есть образец WCF, который включает этот API-интерфейс и показывает, как правильно создать это событие.</span><span class="sxs-lookup"><span data-stu-id="3ee6c-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3ee6c-117">Сообщение</span><span class="sxs-lookup"><span data-stu-id="3ee6c-117">Message</span></span>  
 <span data-ttu-id="3ee6c-118">Имя: «%1», ссылка: «%2», полезные данные: %3</span><span class="sxs-lookup"><span data-stu-id="3ee6c-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="3ee6c-119">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="3ee6c-119">Details</span></span>  
  
|<span data-ttu-id="3ee6c-120">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="3ee6c-120">Data Item Name</span></span>|<span data-ttu-id="3ee6c-121">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="3ee6c-121">Data Item Type</span></span>|<span data-ttu-id="3ee6c-122">Описание</span><span class="sxs-lookup"><span data-stu-id="3ee6c-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3ee6c-123">name</span><span class="sxs-lookup"><span data-stu-id="3ee6c-123">Name</span></span>|`xs:string`|<span data-ttu-id="3ee6c-124">Определенное пользователем имя события.</span><span class="sxs-lookup"><span data-stu-id="3ee6c-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="3ee6c-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="3ee6c-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="3ee6c-126">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="3ee6c-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="3ee6c-127">Формат определяется как "виртуальный путь приложения имя веб-сайта&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="3ee6c-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="3ee6c-128">Пример "По умолчанию веб-сайт/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="3ee6c-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="3ee6c-129">Payload</span><span class="sxs-lookup"><span data-stu-id="3ee6c-129">Payload</span></span>|`xs:string`|<span data-ttu-id="3ee6c-130">Определенные пользователем полезные данные события.</span><span class="sxs-lookup"><span data-stu-id="3ee6c-130">The user-defined payload of the event.</span></span>|
