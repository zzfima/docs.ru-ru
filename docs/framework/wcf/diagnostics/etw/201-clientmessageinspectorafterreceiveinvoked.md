---
title: 201 - ClientMessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
ms.openlocfilehash: 96ca318c141d49e2ac5594d5ee101658a2aa8f21
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782042"
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="34534-102">201 - ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="34534-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="34534-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="34534-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34534-104">ID</span><span class="sxs-lookup"><span data-stu-id="34534-104">ID</span></span>|<span data-ttu-id="34534-105">201</span><span class="sxs-lookup"><span data-stu-id="34534-105">201</span></span>|  
|<span data-ttu-id="34534-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="34534-106">Keywords</span></span>|<span data-ttu-id="34534-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="34534-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="34534-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="34534-108">Level</span></span>|<span data-ttu-id="34534-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="34534-109">Information</span></span>|  
|<span data-ttu-id="34534-110">Канал</span><span class="sxs-lookup"><span data-stu-id="34534-110">Channel</span></span>|<span data-ttu-id="34534-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="34534-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="34534-112">Описание</span><span class="sxs-lookup"><span data-stu-id="34534-112">Description</span></span>  
 <span data-ttu-id="34534-113">Это событие создается после того, как модель службы вызывает метод `AfterReceiveReply` для инспектора сообщений клиента.</span><span class="sxs-lookup"><span data-stu-id="34534-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="34534-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="34534-114">Message</span></span>  
 <span data-ttu-id="34534-115">Диспетчер вызвал AfterReceiveReply относительно ClientMessageInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="34534-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="34534-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="34534-116">Details</span></span>  
  
|<span data-ttu-id="34534-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="34534-117">Data Item Name</span></span>|<span data-ttu-id="34534-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="34534-118">Data Item Type</span></span>|<span data-ttu-id="34534-119">Описание</span><span class="sxs-lookup"><span data-stu-id="34534-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="34534-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="34534-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="34534-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="34534-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="34534-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="34534-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="34534-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="34534-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="34534-124">Формат определяется как "виртуальный путь приложения имя веб-сайта&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="34534-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="34534-125">Пример "По умолчанию веб-сайт/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="34534-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="34534-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="34534-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="34534-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="34534-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
