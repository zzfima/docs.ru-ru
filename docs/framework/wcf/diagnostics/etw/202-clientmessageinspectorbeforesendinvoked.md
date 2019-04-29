---
title: 202 - ClientMessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
ms.openlocfilehash: 98de1d7e8e5e87ec7fbd783092f7fbc212fec65d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781996"
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a><span data-ttu-id="57785-102">202 - ClientMessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="57785-102">202 - ClientMessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="57785-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="57785-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="57785-104">ID</span><span class="sxs-lookup"><span data-stu-id="57785-104">ID</span></span>|<span data-ttu-id="57785-105">202</span><span class="sxs-lookup"><span data-stu-id="57785-105">202</span></span>|  
|<span data-ttu-id="57785-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="57785-106">Keywords</span></span>|<span data-ttu-id="57785-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="57785-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="57785-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="57785-108">Level</span></span>|<span data-ttu-id="57785-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="57785-109">Information</span></span>|  
|<span data-ttu-id="57785-110">Канал</span><span class="sxs-lookup"><span data-stu-id="57785-110">Channel</span></span>|<span data-ttu-id="57785-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="57785-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="57785-112">Описание</span><span class="sxs-lookup"><span data-stu-id="57785-112">Description</span></span>  
 <span data-ttu-id="57785-113">Это событие создается после того, как модель службы вызывает метод `BeforeSendRequest` для инспектора сообщений клиента.</span><span class="sxs-lookup"><span data-stu-id="57785-113">This event is emitted after the Service Model has invoked the `BeforeSendRequest` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="57785-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="57785-114">Message</span></span>  
 <span data-ttu-id="57785-115">Диспетчер вызвал BeforeSendRequest для ClientMessageInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="57785-115">The Dispatcher invoked 'BeforeSendRequest' on a ClientMessageInspector of type  '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="57785-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="57785-116">Details</span></span>  
  
|<span data-ttu-id="57785-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="57785-117">Data Item Name</span></span>|<span data-ttu-id="57785-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="57785-118">Data Item Type</span></span>|<span data-ttu-id="57785-119">Описание</span><span class="sxs-lookup"><span data-stu-id="57785-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="57785-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="57785-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="57785-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="57785-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="57785-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="57785-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="57785-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="57785-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="57785-124">Формат определяется как "виртуальный путь приложения имя веб-сайта&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="57785-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="57785-125">Пример "По умолчанию веб-сайт/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="57785-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="57785-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="57785-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="57785-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="57785-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
