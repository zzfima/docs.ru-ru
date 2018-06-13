---
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: 40a92d77c57728249569a854eab8767ff371bca2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458823"
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="b4c93-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="b4c93-102">206 - ErrorHandlerInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="b4c93-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="b4c93-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b4c93-104">ID</span><span class="sxs-lookup"><span data-stu-id="b4c93-104">ID</span></span>|<span data-ttu-id="b4c93-105">206</span><span class="sxs-lookup"><span data-stu-id="b4c93-105">206</span></span>|  
|<span data-ttu-id="b4c93-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="b4c93-106">Keywords</span></span>|<span data-ttu-id="b4c93-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b4c93-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="b4c93-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="b4c93-108">Level</span></span>|<span data-ttu-id="b4c93-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="b4c93-109">Information</span></span>|  
|<span data-ttu-id="b4c93-110">Канал</span><span class="sxs-lookup"><span data-stu-id="b4c93-110">Channel</span></span>|<span data-ttu-id="b4c93-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b4c93-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b4c93-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b4c93-112">Description</span></span>  
 <span data-ttu-id="b4c93-113">Это событие создается после того, как обработчик `ErrorHandler` начинает обрабатывать исключение, возникшее в операции службы.</span><span class="sxs-lookup"><span data-stu-id="b4c93-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b4c93-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="b4c93-114">Message</span></span>  
 <span data-ttu-id="b4c93-115">Диспетчер запустил ErrorHandler типа «%1» с исключением типа «%3».</span><span class="sxs-lookup"><span data-stu-id="b4c93-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="b4c93-116">ErrorHandled == '%2'.</span><span class="sxs-lookup"><span data-stu-id="b4c93-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b4c93-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="b4c93-117">Details</span></span>  
  
|<span data-ttu-id="b4c93-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="b4c93-118">Data Item Name</span></span>|<span data-ttu-id="b4c93-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="b4c93-119">Data Item Type</span></span>|<span data-ttu-id="b4c93-120">Описание</span><span class="sxs-lookup"><span data-stu-id="b4c93-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b4c93-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="b4c93-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="b4c93-122">Имя CLR FullName типа вызванного инспектора `ErrorHandler`.</span><span class="sxs-lookup"><span data-stu-id="b4c93-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="b4c93-123">Handled</span><span class="sxs-lookup"><span data-stu-id="b4c93-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="b4c93-124">Значение `true`, если обработчик ошибок обработал ошибку, в противном случае значение `false`.</span><span class="sxs-lookup"><span data-stu-id="b4c93-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="b4c93-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="b4c93-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="b4c93-126">Имя CLR FullName обрабатываемого исключения.</span><span class="sxs-lookup"><span data-stu-id="b4c93-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="b4c93-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="b4c93-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="b4c93-128">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="b4c93-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="b4c93-129">Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="b4c93-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="b4c93-130">Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="b4c93-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="b4c93-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b4c93-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b4c93-132">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b4c93-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
