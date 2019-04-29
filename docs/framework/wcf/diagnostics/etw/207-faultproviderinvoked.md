---
title: 207 - FaultProviderInvoked
ms.date: 03/30/2017
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
ms.openlocfilehash: 9f97e74e7685d57b487f456625826ee9cd8e1760
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781918"
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="697e3-102">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="697e3-102">207 - FaultProviderInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="697e3-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="697e3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="697e3-104">ID</span><span class="sxs-lookup"><span data-stu-id="697e3-104">ID</span></span>|<span data-ttu-id="697e3-105">207</span><span class="sxs-lookup"><span data-stu-id="697e3-105">207</span></span>|  
|<span data-ttu-id="697e3-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="697e3-106">Keywords</span></span>|<span data-ttu-id="697e3-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="697e3-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="697e3-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="697e3-108">Level</span></span>|<span data-ttu-id="697e3-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="697e3-109">Information</span></span>|  
|<span data-ttu-id="697e3-110">Канал</span><span class="sxs-lookup"><span data-stu-id="697e3-110">Channel</span></span>|<span data-ttu-id="697e3-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="697e3-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="697e3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="697e3-112">Description</span></span>  
 <span data-ttu-id="697e3-113">Это событие создается после вызова `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="697e3-113">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="697e3-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="697e3-114">Message</span></span>  
 <span data-ttu-id="697e3-115">Диспетчер вызвал FaultProvider типа «%1» с исключением типа «%2».</span><span class="sxs-lookup"><span data-stu-id="697e3-115">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="697e3-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="697e3-116">Details</span></span>  
  
|<span data-ttu-id="697e3-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="697e3-117">Data Item Name</span></span>|<span data-ttu-id="697e3-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="697e3-118">Data Item Type</span></span>|<span data-ttu-id="697e3-119">Описание</span><span class="sxs-lookup"><span data-stu-id="697e3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="697e3-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="697e3-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="697e3-121">Имя CLR FullName типа вызванного инспектора `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="697e3-121">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="697e3-122">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="697e3-122">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="697e3-123">Имя CLR FullName исключения, обработанного `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="697e3-123">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="697e3-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="697e3-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="697e3-125">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="697e3-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="697e3-126">Формат определяется как "виртуальный путь приложения имя веб-сайта&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="697e3-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="697e3-127">Пример "По умолчанию веб-сайт/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="697e3-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="697e3-128">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="697e3-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="697e3-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="697e3-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
