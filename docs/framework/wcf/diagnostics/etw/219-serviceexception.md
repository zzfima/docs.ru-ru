---
title: 219 - ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: eb4289c0346c9e1d9481347d69db8c5f007e4325
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460519"
---
# <a name="219---serviceexception"></a><span data-ttu-id="1a360-102">219 - ServiceException</span><span class="sxs-lookup"><span data-stu-id="1a360-102">219 - ServiceException</span></span>
## <a name="properties"></a><span data-ttu-id="1a360-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="1a360-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1a360-104">ID</span><span class="sxs-lookup"><span data-stu-id="1a360-104">ID</span></span>|<span data-ttu-id="1a360-105">219</span><span class="sxs-lookup"><span data-stu-id="1a360-105">219</span></span>|  
|<span data-ttu-id="1a360-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1a360-106">Keywords</span></span>|<span data-ttu-id="1a360-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1a360-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="1a360-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="1a360-108">Level</span></span>|<span data-ttu-id="1a360-109">Ошибка</span><span class="sxs-lookup"><span data-stu-id="1a360-109">Error</span></span>|  
|<span data-ttu-id="1a360-110">Канал</span><span class="sxs-lookup"><span data-stu-id="1a360-110">Channel</span></span>|<span data-ttu-id="1a360-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="1a360-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1a360-112">Описание</span><span class="sxs-lookup"><span data-stu-id="1a360-112">Description</span></span>  
 <span data-ttu-id="1a360-113">Это событие создается при обнаружении службой WCF необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="1a360-113">This event is emitted when a WCF service encounters an unhandled exception.</span></span> <span data-ttu-id="1a360-114">В число необработанных входят исключения, возникшие во время активации, обработки сообщений и выполнения пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="1a360-114">This includes unhandled exceptions during activation, during message processing, and in user code.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1a360-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="1a360-115">Message</span></span>  
 <span data-ttu-id="1a360-116">Во время обработки сообщения возникло необработанное исключение типа «%2».</span><span class="sxs-lookup"><span data-stu-id="1a360-116">There was an unhandled exception of type '%2' during message processing.</span></span> <span data-ttu-id="1a360-117">Полное исключение ToString: %1.</span><span class="sxs-lookup"><span data-stu-id="1a360-117">Full Exception ToString: %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1a360-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="1a360-118">Details</span></span>  
  
|<span data-ttu-id="1a360-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="1a360-119">Data Item Name</span></span>|<span data-ttu-id="1a360-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="1a360-120">Data Item Type</span></span>|<span data-ttu-id="1a360-121">Описание</span><span class="sxs-lookup"><span data-stu-id="1a360-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1a360-122">ExceptionToString</span><span class="sxs-lookup"><span data-stu-id="1a360-122">ExceptionToString</span></span>|`xs:string`|<span data-ttu-id="1a360-123">Результат вызова метода `ToString`() относительно исключения CLR.</span><span class="sxs-lookup"><span data-stu-id="1a360-123">The result of calling `ToString`() on the CLR exception.</span></span>|  
|<span data-ttu-id="1a360-124">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="1a360-124">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="1a360-125">Имя CLR FullName типа исключения.</span><span class="sxs-lookup"><span data-stu-id="1a360-125">The CLR FullName of the exception's type.</span></span>|  
|<span data-ttu-id="1a360-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="1a360-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="1a360-127">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="1a360-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="1a360-128">Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="1a360-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="1a360-129">Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="1a360-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="1a360-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1a360-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1a360-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1a360-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
