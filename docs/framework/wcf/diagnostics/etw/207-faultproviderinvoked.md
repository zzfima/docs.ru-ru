---
title: 207 - FaultProviderInvoked
ms.date: 03/30/2017
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
ms.openlocfilehash: 9f97e74e7685d57b487f456625826ee9cd8e1760
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457352"
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="a0ef7-102">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="a0ef7-102">207 - FaultProviderInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="a0ef7-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="a0ef7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a0ef7-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="a0ef7-104">ID</span></span>|<span data-ttu-id="a0ef7-105">207</span><span class="sxs-lookup"><span data-stu-id="a0ef7-105">207</span></span>|  
|<span data-ttu-id="a0ef7-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a0ef7-106">Keywords</span></span>|<span data-ttu-id="a0ef7-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a0ef7-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a0ef7-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="a0ef7-108">Level</span></span>|<span data-ttu-id="a0ef7-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="a0ef7-109">Information</span></span>|  
|<span data-ttu-id="a0ef7-110">Канал</span><span class="sxs-lookup"><span data-stu-id="a0ef7-110">Channel</span></span>|<span data-ttu-id="a0ef7-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a0ef7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a0ef7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a0ef7-112">Description</span></span>  
 <span data-ttu-id="a0ef7-113">Это событие создается после вызова `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="a0ef7-113">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a0ef7-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="a0ef7-114">Message</span></span>  
 <span data-ttu-id="a0ef7-115">Диспетчер вызвал FaultProvider типа «%1» с исключением типа «%2».</span><span class="sxs-lookup"><span data-stu-id="a0ef7-115">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a0ef7-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="a0ef7-116">Details</span></span>  
  
|<span data-ttu-id="a0ef7-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="a0ef7-117">Data Item Name</span></span>|<span data-ttu-id="a0ef7-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="a0ef7-118">Data Item Type</span></span>|<span data-ttu-id="a0ef7-119">Описание</span><span class="sxs-lookup"><span data-stu-id="a0ef7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a0ef7-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="a0ef7-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="a0ef7-121">Имя CLR FullName типа вызванного инспектора `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="a0ef7-121">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="a0ef7-122">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="a0ef7-122">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="a0ef7-123">Имя CLR FullName исключения, обработанного `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="a0ef7-123">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="a0ef7-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="a0ef7-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="a0ef7-125">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="a0ef7-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a0ef7-126">Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="a0ef7-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a0ef7-127">Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="a0ef7-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a0ef7-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a0ef7-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a0ef7-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a0ef7-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
