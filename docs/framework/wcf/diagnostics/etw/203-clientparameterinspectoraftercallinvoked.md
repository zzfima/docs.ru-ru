---
title: 203 - ClientParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: b9592212-07e2-43e0-8b00-affd195cf55a
ms.openlocfilehash: 57192b44a0c3babc77fcca13ad4a1433b85bfdd7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458625"
---
# <a name="203---clientparameterinspectoraftercallinvoked"></a><span data-ttu-id="aa8d9-102">203 - ClientParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="aa8d9-102">203 - ClientParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="aa8d9-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="aa8d9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa8d9-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="aa8d9-104">ID</span></span>|<span data-ttu-id="aa8d9-105">203</span><span class="sxs-lookup"><span data-stu-id="aa8d9-105">203</span></span>|  
|<span data-ttu-id="aa8d9-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="aa8d9-106">Keywords</span></span>|<span data-ttu-id="aa8d9-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="aa8d9-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="aa8d9-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="aa8d9-108">Level</span></span>|<span data-ttu-id="aa8d9-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="aa8d9-109">Information</span></span>|  
|<span data-ttu-id="aa8d9-110">Канал</span><span class="sxs-lookup"><span data-stu-id="aa8d9-110">Channel</span></span>|<span data-ttu-id="aa8d9-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="aa8d9-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aa8d9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="aa8d9-112">Description</span></span>  
 <span data-ttu-id="aa8d9-113">Это событие создается после того, как модель службы вызывает метод `AfterCall` для инспектора параметров клиента.</span><span class="sxs-lookup"><span data-stu-id="aa8d9-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="aa8d9-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="aa8d9-114">Message</span></span>  
 <span data-ttu-id="aa8d9-115">Диспетчер вызвал «AfterCall» для ClientParameterInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="aa8d9-115">The Dispatcher invoked 'AfterCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="aa8d9-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="aa8d9-116">Details</span></span>  
  
|<span data-ttu-id="aa8d9-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="aa8d9-117">Data Item Name</span></span>|<span data-ttu-id="aa8d9-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="aa8d9-118">Data Item Type</span></span>|<span data-ttu-id="aa8d9-119">Описание</span><span class="sxs-lookup"><span data-stu-id="aa8d9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="aa8d9-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="aa8d9-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="aa8d9-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="aa8d9-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="aa8d9-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="aa8d9-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="aa8d9-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="aa8d9-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="aa8d9-124">Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="aa8d9-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="aa8d9-125">Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="aa8d9-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="aa8d9-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="aa8d9-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="aa8d9-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="aa8d9-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
