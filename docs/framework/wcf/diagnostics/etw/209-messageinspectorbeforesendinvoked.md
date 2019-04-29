---
title: 209 - MessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
ms.openlocfilehash: 24184c24b9affdf3a56d7968c02cf5354d690749
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781888"
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="db60d-102">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="db60d-102">209 - MessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="db60d-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="db60d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="db60d-104">ID</span><span class="sxs-lookup"><span data-stu-id="db60d-104">ID</span></span>|<span data-ttu-id="db60d-105">209</span><span class="sxs-lookup"><span data-stu-id="db60d-105">209</span></span>|  
|<span data-ttu-id="db60d-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="db60d-106">Keywords</span></span>|<span data-ttu-id="db60d-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="db60d-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="db60d-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="db60d-108">Level</span></span>|<span data-ttu-id="db60d-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="db60d-109">Information</span></span>|  
|<span data-ttu-id="db60d-110">Канал</span><span class="sxs-lookup"><span data-stu-id="db60d-110">Channel</span></span>|<span data-ttu-id="db60d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="db60d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="db60d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="db60d-112">Description</span></span>  
 <span data-ttu-id="db60d-113">Это событие создается после того, как модель службы вызвала метод `BeforeSend` для инспектора сообщений.</span><span class="sxs-lookup"><span data-stu-id="db60d-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="db60d-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="db60d-114">Message</span></span>  
 <span data-ttu-id="db60d-115">Диспетчер вызвал BeforeSendRequest для MessageInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="db60d-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="db60d-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="db60d-116">Details</span></span>  
  
|<span data-ttu-id="db60d-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="db60d-117">Data Item Name</span></span>|<span data-ttu-id="db60d-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="db60d-118">Data Item Type</span></span>|<span data-ttu-id="db60d-119">Описание</span><span class="sxs-lookup"><span data-stu-id="db60d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="db60d-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="db60d-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="db60d-121">Имя CLR FullName типа вызванного инспектора `MessageInspector`.</span><span class="sxs-lookup"><span data-stu-id="db60d-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="db60d-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="db60d-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="db60d-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="db60d-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="db60d-124">Формат определяется как "виртуальный путь приложения имя веб-сайта&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="db60d-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="db60d-125">Пример "По умолчанию веб-сайт/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="db60d-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="db60d-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="db60d-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="db60d-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="db60d-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
