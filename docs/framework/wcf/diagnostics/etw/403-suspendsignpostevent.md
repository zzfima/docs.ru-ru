---
title: 403 - SuspendSignpostEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb2e6f29-e556-47b4-b4c1-acd6b8879702
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee1daab843ad0a2161d13b86bcd657b7236ddaa6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="403---suspendsignpostevent"></a><span data-ttu-id="26233-102">403 - SuspendSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="26233-102">403 - SuspendSignpostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="26233-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="26233-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="26233-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="26233-104">ID</span></span>|<span data-ttu-id="26233-105">403</span><span class="sxs-lookup"><span data-stu-id="26233-105">403</span></span>|  
|<span data-ttu-id="26233-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="26233-106">Keywords</span></span>|<span data-ttu-id="26233-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="26233-107">Troubleshooting</span></span>|  
|<span data-ttu-id="26233-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="26233-108">Level</span></span>|<span data-ttu-id="26233-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="26233-109">Information</span></span>|  
|<span data-ttu-id="26233-110">Канал</span><span class="sxs-lookup"><span data-stu-id="26233-110">Channel</span></span>|<span data-ttu-id="26233-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="26233-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="26233-112">Описание</span><span class="sxs-lookup"><span data-stu-id="26233-112">Description</span></span>  
 <span data-ttu-id="26233-113">Это событие сигнализирует о приостановке сквозного действия.</span><span class="sxs-lookup"><span data-stu-id="26233-113">This event marks the suspension of an end-to-end activity.</span></span> <span data-ttu-id="26233-114">В ней содержится имя действия.</span><span class="sxs-lookup"><span data-stu-id="26233-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="26233-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="26233-115">Message</span></span>  
 <span data-ttu-id="26233-116">Граница действия.</span><span class="sxs-lookup"><span data-stu-id="26233-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="26233-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="26233-117">Details</span></span>  
  
|<span data-ttu-id="26233-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="26233-118">Data Item Name</span></span>|<span data-ttu-id="26233-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="26233-119">Data Item Type</span></span>|<span data-ttu-id="26233-120">Описание</span><span class="sxs-lookup"><span data-stu-id="26233-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="26233-121">Расширенные данные</span><span class="sxs-lookup"><span data-stu-id="26233-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="26233-122">Имя действия.</span><span class="sxs-lookup"><span data-stu-id="26233-122">The name of the activity.</span></span>|  
|<span data-ttu-id="26233-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="26233-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="26233-124">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="26233-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
