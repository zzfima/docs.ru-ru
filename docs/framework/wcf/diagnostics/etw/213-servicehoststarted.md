---
title: 213 - ServiceHostStarted
ms.date: 03/30/2017
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
ms.openlocfilehash: 819efa2e13c94e2c7a16c24f6ba9c7ef2b87ef8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="213---servicehoststarted"></a><span data-ttu-id="98dcf-102">213 - ServiceHostStarted</span><span class="sxs-lookup"><span data-stu-id="98dcf-102">213 - ServiceHostStarted</span></span>
## <a name="properties"></a><span data-ttu-id="98dcf-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="98dcf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98dcf-104">ID</span><span class="sxs-lookup"><span data-stu-id="98dcf-104">ID</span></span>|<span data-ttu-id="98dcf-105">213</span><span class="sxs-lookup"><span data-stu-id="98dcf-105">213</span></span>|  
|<span data-ttu-id="98dcf-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="98dcf-106">Keywords</span></span>|<span data-ttu-id="98dcf-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span><span class="sxs-lookup"><span data-stu-id="98dcf-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span></span>|  
|<span data-ttu-id="98dcf-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="98dcf-108">Level</span></span>|<span data-ttu-id="98dcf-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="98dcf-109">LogAlways</span></span>|  
|<span data-ttu-id="98dcf-110">Канал</span><span class="sxs-lookup"><span data-stu-id="98dcf-110">Channel</span></span>|<span data-ttu-id="98dcf-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="98dcf-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="98dcf-112">Описание</span><span class="sxs-lookup"><span data-stu-id="98dcf-112">Description</span></span>  
 <span data-ttu-id="98dcf-113">Это событие создается при запуске службы, размещенной на веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="98dcf-113">This event is emitted when a Web-hosted service host is started.</span></span> <span data-ttu-id="98dcf-114">Обычно это происходит, когда служба активируется сообщением.</span><span class="sxs-lookup"><span data-stu-id="98dcf-114">This typically happens when the service is activated by a message.</span></span> <span data-ttu-id="98dcf-115">Это также может произойти, если служба настроена для автоматического запуска.</span><span class="sxs-lookup"><span data-stu-id="98dcf-115">It may also happen if the service is configured to be automatically started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="98dcf-116">Сообщение</span><span class="sxs-lookup"><span data-stu-id="98dcf-116">Message</span></span>  
 <span data-ttu-id="98dcf-117">ServiceHost запущена: «%1».</span><span class="sxs-lookup"><span data-stu-id="98dcf-117">ServiceHost started: '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="98dcf-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="98dcf-118">Details</span></span>  
  
|<span data-ttu-id="98dcf-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="98dcf-119">Data Item Name</span></span>|<span data-ttu-id="98dcf-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="98dcf-120">Data Item Type</span></span>|<span data-ttu-id="98dcf-121">Описание</span><span class="sxs-lookup"><span data-stu-id="98dcf-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="98dcf-122">Имя типа службы</span><span class="sxs-lookup"><span data-stu-id="98dcf-122">Service Type Name</span></span>|`xs:string`|<span data-ttu-id="98dcf-123">Имя CLR FullName типа реализации службы.</span><span class="sxs-lookup"><span data-stu-id="98dcf-123">The CLR FullName of the type of the service implementation.</span></span>|  
|<span data-ttu-id="98dcf-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="98dcf-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="98dcf-125">Для служб, размещенных на веб-узле, это поле служит уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="98dcf-125">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="98dcf-126">Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="98dcf-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="98dcf-127">Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="98dcf-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="98dcf-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="98dcf-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="98dcf-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="98dcf-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
