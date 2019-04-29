---
title: 204 - ClientParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 8253555a-9002-4565-8ede-33d7a33a895f
ms.openlocfilehash: eb060cfa79b75452deae67705126a24b7ca9ffef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782048"
---
# <a name="204---clientparameterinspectorbeforecallinvoked"></a><span data-ttu-id="4b943-102">204 - ClientParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="4b943-102">204 - ClientParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="4b943-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="4b943-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4b943-104">ID</span><span class="sxs-lookup"><span data-stu-id="4b943-104">ID</span></span>|<span data-ttu-id="4b943-105">204</span><span class="sxs-lookup"><span data-stu-id="4b943-105">204</span></span>|  
|<span data-ttu-id="4b943-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="4b943-106">Keywords</span></span>|<span data-ttu-id="4b943-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4b943-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="4b943-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="4b943-108">Level</span></span>|<span data-ttu-id="4b943-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="4b943-109">Information</span></span>|  
|<span data-ttu-id="4b943-110">Канал</span><span class="sxs-lookup"><span data-stu-id="4b943-110">Channel</span></span>|<span data-ttu-id="4b943-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="4b943-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4b943-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4b943-112">Description</span></span>  
 <span data-ttu-id="4b943-113">Это событие создается после того, как модель службы вызывает метод `BeforeCall` для инспектора параметров клиента.</span><span class="sxs-lookup"><span data-stu-id="4b943-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4b943-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="4b943-114">Message</span></span>  
 <span data-ttu-id="4b943-115">Диспетчер вызвал BeforeCall для ClientParameterInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="4b943-115">The Dispatcher invoked 'BeforeCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4b943-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="4b943-116">Details</span></span>  
  
|<span data-ttu-id="4b943-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="4b943-117">Data Item Name</span></span>|<span data-ttu-id="4b943-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="4b943-118">Data Item Type</span></span>|<span data-ttu-id="4b943-119">Описание</span><span class="sxs-lookup"><span data-stu-id="4b943-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4b943-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="4b943-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="4b943-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="4b943-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="4b943-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="4b943-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="4b943-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="4b943-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="4b943-124">Формат определяется как "виртуальный путь приложения имя веб-сайта&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="4b943-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="4b943-125">Пример "По умолчанию веб-сайт/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="4b943-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="4b943-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="4b943-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4b943-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4b943-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
