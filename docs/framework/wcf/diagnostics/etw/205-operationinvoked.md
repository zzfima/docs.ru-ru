---
title: 205 - OperationInvoked
ms.date: 03/30/2017
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
ms.openlocfilehash: e95b6923d21307b2ef68d4a5369b3cee86540239
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458353"
---
# <a name="205---operationinvoked"></a><span data-ttu-id="a0c27-102">205 - OperationInvoked</span><span class="sxs-lookup"><span data-stu-id="a0c27-102">205 - OperationInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="a0c27-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="a0c27-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a0c27-104">ID</span><span class="sxs-lookup"><span data-stu-id="a0c27-104">ID</span></span>|<span data-ttu-id="a0c27-105">205</span><span class="sxs-lookup"><span data-stu-id="a0c27-105">205</span></span>|  
|<span data-ttu-id="a0c27-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a0c27-106">Keywords</span></span>|<span data-ttu-id="a0c27-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a0c27-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a0c27-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="a0c27-108">Level</span></span>|<span data-ttu-id="a0c27-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="a0c27-109">Information</span></span>|  
|<span data-ttu-id="a0c27-110">Канал</span><span class="sxs-lookup"><span data-stu-id="a0c27-110">Channel</span></span>|<span data-ttu-id="a0c27-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a0c27-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a0c27-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a0c27-112">Description</span></span>  
 <span data-ttu-id="a0c27-113">Это событие создается непосредственно перед тем, как `OperationInvoker` по умолчанию модели службы начнет вызов метода.</span><span class="sxs-lookup"><span data-stu-id="a0c27-113">This event is emitted just before the Service Model's default `OperationInvoker` begins a call to a method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a0c27-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="a0c27-114">Message</span></span>  
 <span data-ttu-id="a0c27-115">OperationInvoker вызвал метод «%1».</span><span class="sxs-lookup"><span data-stu-id="a0c27-115">An OperationInvoker invoked the '%1' method.</span></span> <span data-ttu-id="a0c27-116">Сведения о вызывающем объекте: «%2».</span><span class="sxs-lookup"><span data-stu-id="a0c27-116">Caller information: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a0c27-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="a0c27-117">Details</span></span>  
  
|<span data-ttu-id="a0c27-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="a0c27-118">Data Item Name</span></span>|<span data-ttu-id="a0c27-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="a0c27-119">Data Item Type</span></span>|<span data-ttu-id="a0c27-120">Описание</span><span class="sxs-lookup"><span data-stu-id="a0c27-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a0c27-121">Имя метода</span><span class="sxs-lookup"><span data-stu-id="a0c27-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="a0c27-122">Имя CLR метода, который был вызван `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="a0c27-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="a0c27-123">Сведения о вызывающем</span><span class="sxs-lookup"><span data-stu-id="a0c27-123">Caller Information</span></span>|`xs:string`|<span data-ttu-id="a0c27-124">IP-адрес и номер порта клиента в формате «IPAddress:PortNumber».</span><span class="sxs-lookup"><span data-stu-id="a0c27-124">The IP address and port number of the client in the format 'IPAddress:PortNumber'.</span></span> <span data-ttu-id="a0c27-125">Эти два значения извлекаются из свойства сообщения «System.ServiceModel.Channels.RemoteEndpointMessageProperty» в контексте операции.</span><span class="sxs-lookup"><span data-stu-id="a0c27-125">The two values are retrieved from the 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' message property within the operation context.</span></span> <span data-ttu-id="a0c27-126">Следует отметить, что для привязок, отличных от TCP, это значение `null`.</span><span class="sxs-lookup"><span data-stu-id="a0c27-126">Note that for non-TCP bindings this value `null`.</span></span>|  
|<span data-ttu-id="a0c27-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="a0c27-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="a0c27-128">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="a0c27-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a0c27-129">Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="a0c27-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a0c27-130">Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="a0c27-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a0c27-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a0c27-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a0c27-132">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a0c27-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
