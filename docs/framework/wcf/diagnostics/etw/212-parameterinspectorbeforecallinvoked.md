---
title: 212 - ParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
ms.openlocfilehash: 02d4a4ed1e96983e132a1943dd39f9f885e5596a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458810"
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="62ae4-102">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="62ae4-102">212 - ParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="62ae4-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="62ae4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="62ae4-104">ID</span><span class="sxs-lookup"><span data-stu-id="62ae4-104">ID</span></span>|<span data-ttu-id="62ae4-105">212</span><span class="sxs-lookup"><span data-stu-id="62ae4-105">212</span></span>|  
|<span data-ttu-id="62ae4-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62ae4-106">Keywords</span></span>|<span data-ttu-id="62ae4-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="62ae4-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="62ae4-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="62ae4-108">Level</span></span>|<span data-ttu-id="62ae4-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="62ae4-109">Information</span></span>|  
|<span data-ttu-id="62ae4-110">Канал</span><span class="sxs-lookup"><span data-stu-id="62ae4-110">Channel</span></span>|<span data-ttu-id="62ae4-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="62ae4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="62ae4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="62ae4-112">Description</span></span>  
 <span data-ttu-id="62ae4-113">Это событие создается после того, как модель службы вызывает метод `BeforeCall` для `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="62ae4-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="62ae4-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="62ae4-114">Message</span></span>  
 <span data-ttu-id="62ae4-115">Диспетчер вызвал BeforeCall для ParameterInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="62ae4-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="62ae4-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="62ae4-116">Details</span></span>  
  
|<span data-ttu-id="62ae4-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="62ae4-117">Data Item Name</span></span>|<span data-ttu-id="62ae4-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="62ae4-118">Data Item Type</span></span>|<span data-ttu-id="62ae4-119">Описание</span><span class="sxs-lookup"><span data-stu-id="62ae4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="62ae4-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="62ae4-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="62ae4-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="62ae4-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="62ae4-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="62ae4-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="62ae4-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="62ae4-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="62ae4-124">Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="62ae4-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="62ae4-125">Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="62ae4-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="62ae4-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="62ae4-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="62ae4-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="62ae4-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
