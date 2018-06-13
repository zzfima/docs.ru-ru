---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
ms.openlocfilehash: 3499131fcb52f0a0ab6d0e78e165522b7092612f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458902"
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="4d307-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="4d307-102">208 - MessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="4d307-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="4d307-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4d307-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="4d307-104">ID</span></span>|<span data-ttu-id="4d307-105">208</span><span class="sxs-lookup"><span data-stu-id="4d307-105">208</span></span>|  
|<span data-ttu-id="4d307-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="4d307-106">Keywords</span></span>|<span data-ttu-id="4d307-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4d307-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="4d307-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="4d307-108">Level</span></span>|<span data-ttu-id="4d307-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="4d307-109">Information</span></span>|  
|<span data-ttu-id="4d307-110">Канал</span><span class="sxs-lookup"><span data-stu-id="4d307-110">Channel</span></span>|<span data-ttu-id="4d307-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="4d307-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4d307-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4d307-112">Description</span></span>  
 <span data-ttu-id="4d307-113">Это событие создается после того, как модель службы вызвала метод `AfterReceive` для инспектора сообщений.</span><span class="sxs-lookup"><span data-stu-id="4d307-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4d307-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="4d307-114">Message</span></span>  
 <span data-ttu-id="4d307-115">Диспетчер вызвал AfterReceiveReply относительно MessageInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="4d307-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4d307-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="4d307-116">Details</span></span>  
  
|<span data-ttu-id="4d307-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="4d307-117">Data Item Name</span></span>|<span data-ttu-id="4d307-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="4d307-118">Data Item Type</span></span>|<span data-ttu-id="4d307-119">Описание</span><span class="sxs-lookup"><span data-stu-id="4d307-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4d307-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="4d307-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="4d307-121">Имя CLR FullName типа вызванного инспектора `MessageInspector`.</span><span class="sxs-lookup"><span data-stu-id="4d307-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="4d307-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="4d307-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="4d307-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="4d307-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="4d307-124">Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="4d307-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="4d307-125">Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="4d307-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="4d307-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4d307-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4d307-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4d307-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
