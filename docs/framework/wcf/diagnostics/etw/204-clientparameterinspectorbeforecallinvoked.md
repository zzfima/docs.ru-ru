---
title: 204 - ClientParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 8253555a-9002-4565-8ede-33d7a33a895f
ms.openlocfilehash: eb060cfa79b75452deae67705126a24b7ca9ffef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="204---clientparameterinspectorbeforecallinvoked"></a><span data-ttu-id="afbf7-102">204 - ClientParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="afbf7-102">204 - ClientParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="afbf7-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="afbf7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="afbf7-104">ID</span><span class="sxs-lookup"><span data-stu-id="afbf7-104">ID</span></span>|<span data-ttu-id="afbf7-105">204</span><span class="sxs-lookup"><span data-stu-id="afbf7-105">204</span></span>|  
|<span data-ttu-id="afbf7-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="afbf7-106">Keywords</span></span>|<span data-ttu-id="afbf7-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="afbf7-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="afbf7-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="afbf7-108">Level</span></span>|<span data-ttu-id="afbf7-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="afbf7-109">Information</span></span>|  
|<span data-ttu-id="afbf7-110">Канал</span><span class="sxs-lookup"><span data-stu-id="afbf7-110">Channel</span></span>|<span data-ttu-id="afbf7-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="afbf7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="afbf7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="afbf7-112">Description</span></span>  
 <span data-ttu-id="afbf7-113">Это событие создается после того, как модель службы вызывает метод `BeforeCall` для инспектора параметров клиента.</span><span class="sxs-lookup"><span data-stu-id="afbf7-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="afbf7-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="afbf7-114">Message</span></span>  
 <span data-ttu-id="afbf7-115">Диспетчер вызвал BeforeCall для ClientParameterInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="afbf7-115">The Dispatcher invoked 'BeforeCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="afbf7-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="afbf7-116">Details</span></span>  
  
|<span data-ttu-id="afbf7-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="afbf7-117">Data Item Name</span></span>|<span data-ttu-id="afbf7-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="afbf7-118">Data Item Type</span></span>|<span data-ttu-id="afbf7-119">Описание</span><span class="sxs-lookup"><span data-stu-id="afbf7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="afbf7-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="afbf7-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="afbf7-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="afbf7-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="afbf7-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="afbf7-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="afbf7-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="afbf7-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="afbf7-124">Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="afbf7-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="afbf7-125">Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="afbf7-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="afbf7-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="afbf7-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="afbf7-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="afbf7-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
