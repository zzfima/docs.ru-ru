---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
ms.openlocfilehash: 3499131fcb52f0a0ab6d0e78e165522b7092612f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781905"
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="70452-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="70452-102">208 - MessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="70452-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="70452-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="70452-104">ID</span><span class="sxs-lookup"><span data-stu-id="70452-104">ID</span></span>|<span data-ttu-id="70452-105">208</span><span class="sxs-lookup"><span data-stu-id="70452-105">208</span></span>|  
|<span data-ttu-id="70452-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="70452-106">Keywords</span></span>|<span data-ttu-id="70452-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="70452-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="70452-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="70452-108">Level</span></span>|<span data-ttu-id="70452-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="70452-109">Information</span></span>|  
|<span data-ttu-id="70452-110">Канал</span><span class="sxs-lookup"><span data-stu-id="70452-110">Channel</span></span>|<span data-ttu-id="70452-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="70452-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="70452-112">Описание</span><span class="sxs-lookup"><span data-stu-id="70452-112">Description</span></span>  
 <span data-ttu-id="70452-113">Это событие создается после того, как модель службы вызвала метод `AfterReceive` для инспектора сообщений.</span><span class="sxs-lookup"><span data-stu-id="70452-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="70452-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="70452-114">Message</span></span>  
 <span data-ttu-id="70452-115">Диспетчер вызвал AfterReceiveReply относительно MessageInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="70452-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="70452-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="70452-116">Details</span></span>  
  
|<span data-ttu-id="70452-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="70452-117">Data Item Name</span></span>|<span data-ttu-id="70452-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="70452-118">Data Item Type</span></span>|<span data-ttu-id="70452-119">Описание</span><span class="sxs-lookup"><span data-stu-id="70452-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="70452-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="70452-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="70452-121">Имя CLR FullName типа вызванного инспектора `MessageInspector`.</span><span class="sxs-lookup"><span data-stu-id="70452-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="70452-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="70452-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="70452-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="70452-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="70452-124">Формат определяется как "виртуальный путь приложения имя веб-сайта&#124;виртуальный путь службы&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="70452-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="70452-125">Пример "По умолчанию веб-сайт/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="70452-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="70452-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="70452-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="70452-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="70452-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
