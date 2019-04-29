---
title: 212 - ParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
ms.openlocfilehash: 02d4a4ed1e96983e132a1943dd39f9f885e5596a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781853"
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="13816-102">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="13816-102">212 - ParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="13816-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="13816-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="13816-104">ID</span><span class="sxs-lookup"><span data-stu-id="13816-104">ID</span></span>|<span data-ttu-id="13816-105">212</span><span class="sxs-lookup"><span data-stu-id="13816-105">212</span></span>|  
|<span data-ttu-id="13816-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="13816-106">Keywords</span></span>|<span data-ttu-id="13816-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="13816-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="13816-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="13816-108">Level</span></span>|<span data-ttu-id="13816-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="13816-109">Information</span></span>|  
|<span data-ttu-id="13816-110">Канал</span><span class="sxs-lookup"><span data-stu-id="13816-110">Channel</span></span>|<span data-ttu-id="13816-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="13816-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="13816-112">Описание</span><span class="sxs-lookup"><span data-stu-id="13816-112">Description</span></span>  
 <span data-ttu-id="13816-113">Это событие создается после того, как модель службы вызывает метод `BeforeCall` для `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="13816-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="13816-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="13816-114">Message</span></span>  
 <span data-ttu-id="13816-115">Диспетчер вызвал BeforeCall для ParameterInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="13816-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="13816-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="13816-116">Details</span></span>  
  
|<span data-ttu-id="13816-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="13816-117">Data Item Name</span></span>|<span data-ttu-id="13816-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="13816-118">Data Item Type</span></span>|<span data-ttu-id="13816-119">Описание</span><span class="sxs-lookup"><span data-stu-id="13816-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="13816-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="13816-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="13816-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="13816-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="13816-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="13816-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="13816-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="13816-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="13816-124">Формат определяется как "виртуальный путь приложения имя веб-сайта&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="13816-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="13816-125">Пример "По умолчанию веб-сайт/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="13816-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="13816-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="13816-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="13816-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="13816-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
