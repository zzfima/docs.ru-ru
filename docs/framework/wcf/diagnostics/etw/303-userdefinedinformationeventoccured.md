---
title: 303 - UserDefinedInformationEventOccured
ms.date: 03/30/2017
ms.assetid: 5ed5acaf-3755-4417-92c4-4ebc8e854ca1
ms.openlocfilehash: 0b782b5ac0527b5acb3ebf0bf11c117563042495
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459144"
---
# <a name="303---userdefinedinformationeventoccured"></a><span data-ttu-id="e3e70-102">303 - UserDefinedInformationEventOccured</span><span class="sxs-lookup"><span data-stu-id="e3e70-102">303 - UserDefinedInformationEventOccured</span></span>
## <a name="properties"></a><span data-ttu-id="e3e70-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="e3e70-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e3e70-104">ID</span><span class="sxs-lookup"><span data-stu-id="e3e70-104">ID</span></span>|<span data-ttu-id="e3e70-105">303</span><span class="sxs-lookup"><span data-stu-id="e3e70-105">303</span></span>|  
|<span data-ttu-id="e3e70-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e3e70-106">Keywords</span></span>|<span data-ttu-id="e3e70-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="e3e70-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="e3e70-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="e3e70-108">Level</span></span>|<span data-ttu-id="e3e70-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="e3e70-109">Information</span></span>|  
|<span data-ttu-id="e3e70-110">Канал</span><span class="sxs-lookup"><span data-stu-id="e3e70-110">Channel</span></span>|<span data-ttu-id="e3e70-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e3e70-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e3e70-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e3e70-112">Description</span></span>  
 <span data-ttu-id="e3e70-113">Это событие создается в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="e3e70-113">This event is emitted from user code.</span></span> <span data-ttu-id="e3e70-114">Разработчик может создавать это событие при возникновении определенных пользователем информационных событий в его службе.</span><span class="sxs-lookup"><span data-stu-id="e3e70-114">Developers can emit this event when a custom-defined informational event occurs in their service.</span></span> <span data-ttu-id="e3e70-115">Это можно сделать при помощи API-интерфейсов <xref:System.Diagnostics.Eventing>.</span><span class="sxs-lookup"><span data-stu-id="e3e70-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="e3e70-116">Помимо этого, есть образец WCF, который включает этот API-интерфейс и показывает, как правильно создать это событие.</span><span class="sxs-lookup"><span data-stu-id="e3e70-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e3e70-117">Сообщение</span><span class="sxs-lookup"><span data-stu-id="e3e70-117">Message</span></span>  
 <span data-ttu-id="e3e70-118">Имя: «%1», ссылка: «%2», полезные данные: %3</span><span class="sxs-lookup"><span data-stu-id="e3e70-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="e3e70-119">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="e3e70-119">Details</span></span>  
  
|<span data-ttu-id="e3e70-120">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="e3e70-120">Data Item Name</span></span>|<span data-ttu-id="e3e70-121">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="e3e70-121">Data Item Type</span></span>|<span data-ttu-id="e3e70-122">Описание</span><span class="sxs-lookup"><span data-stu-id="e3e70-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e3e70-123">name</span><span class="sxs-lookup"><span data-stu-id="e3e70-123">Name</span></span>|`xs:string`|<span data-ttu-id="e3e70-124">Определенное пользователем имя события.</span><span class="sxs-lookup"><span data-stu-id="e3e70-124">The user-defined name of the event</span></span>|  
|<span data-ttu-id="e3e70-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="e3e70-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="e3e70-126">Для служб, размещенных на веб-узле, это поле служит уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="e3e70-126">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e3e70-127">Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="e3e70-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e3e70-128">Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="e3e70-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e3e70-129">Payload</span><span class="sxs-lookup"><span data-stu-id="e3e70-129">Payload</span></span>|`xs:string`|<span data-ttu-id="e3e70-130">Определенные пользователем полезные данные события.</span><span class="sxs-lookup"><span data-stu-id="e3e70-130">The user-defined payload of the event.</span></span>|
