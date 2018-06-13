---
title: 211 - ParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
ms.openlocfilehash: ada3ced31def2bb821b975e09f50ad83f28d56bf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459721"
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="f1c39-102">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="f1c39-102">211 - ParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="f1c39-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="f1c39-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f1c39-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="f1c39-104">ID</span></span>|<span data-ttu-id="f1c39-105">211</span><span class="sxs-lookup"><span data-stu-id="f1c39-105">211</span></span>|  
|<span data-ttu-id="f1c39-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="f1c39-106">Keywords</span></span>|<span data-ttu-id="f1c39-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f1c39-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f1c39-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="f1c39-108">Level</span></span>|<span data-ttu-id="f1c39-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="f1c39-109">Information</span></span>|  
|<span data-ttu-id="f1c39-110">Канал</span><span class="sxs-lookup"><span data-stu-id="f1c39-110">Channel</span></span>|<span data-ttu-id="f1c39-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f1c39-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f1c39-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f1c39-112">Description</span></span>  
 <span data-ttu-id="f1c39-113">Это событие создается после того, как модель службы вызывает метод `AfterCall` для `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="f1c39-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f1c39-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f1c39-114">Message</span></span>  
 <span data-ttu-id="f1c39-115">Диспетчер вызвал AfterCall относительно ParameterInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="f1c39-115">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f1c39-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="f1c39-116">Details</span></span>  
  
|<span data-ttu-id="f1c39-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="f1c39-117">Data Item Name</span></span>|<span data-ttu-id="f1c39-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="f1c39-118">Data Item Type</span></span>|<span data-ttu-id="f1c39-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f1c39-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f1c39-120">Имя типа</span><span class="sxs-lookup"><span data-stu-id="f1c39-120">Type Name</span></span>|`xs:string`|<span data-ttu-id="f1c39-121">Имя CLR FullName типа вызванного инспектора `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="f1c39-121">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="f1c39-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="f1c39-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="f1c39-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="f1c39-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f1c39-124">Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="f1c39-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f1c39-125">Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="f1c39-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f1c39-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f1c39-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f1c39-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f1c39-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
