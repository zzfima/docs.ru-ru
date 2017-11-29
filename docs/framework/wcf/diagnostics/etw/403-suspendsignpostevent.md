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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 10e745ded72caa493119d7e27a5c777b2185b96e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="403---suspendsignpostevent"></a><span data-ttu-id="e8c8f-102">403 - SuspendSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="e8c8f-102">403 - SuspendSignpostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="e8c8f-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="e8c8f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e8c8f-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="e8c8f-104">ID</span></span>|<span data-ttu-id="e8c8f-105">403</span><span class="sxs-lookup"><span data-stu-id="e8c8f-105">403</span></span>|  
|<span data-ttu-id="e8c8f-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e8c8f-106">Keywords</span></span>|<span data-ttu-id="e8c8f-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="e8c8f-107">Troubleshooting</span></span>|  
|<span data-ttu-id="e8c8f-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="e8c8f-108">Level</span></span>|<span data-ttu-id="e8c8f-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="e8c8f-109">Information</span></span>|  
|<span data-ttu-id="e8c8f-110">Канал</span><span class="sxs-lookup"><span data-stu-id="e8c8f-110">Channel</span></span>|<span data-ttu-id="e8c8f-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e8c8f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e8c8f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e8c8f-112">Description</span></span>  
 <span data-ttu-id="e8c8f-113">Это событие сигнализирует о приостановке сквозного действия.</span><span class="sxs-lookup"><span data-stu-id="e8c8f-113">This event marks the suspension of an end-to-end activity.</span></span> <span data-ttu-id="e8c8f-114">В ней содержится имя действия.</span><span class="sxs-lookup"><span data-stu-id="e8c8f-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e8c8f-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="e8c8f-115">Message</span></span>  
 <span data-ttu-id="e8c8f-116">Граница действия.</span><span class="sxs-lookup"><span data-stu-id="e8c8f-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e8c8f-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="e8c8f-117">Details</span></span>  
  
|<span data-ttu-id="e8c8f-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="e8c8f-118">Data Item Name</span></span>|<span data-ttu-id="e8c8f-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="e8c8f-119">Data Item Type</span></span>|<span data-ttu-id="e8c8f-120">Описание</span><span class="sxs-lookup"><span data-stu-id="e8c8f-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e8c8f-121">Расширенные данные</span><span class="sxs-lookup"><span data-stu-id="e8c8f-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="e8c8f-122">Имя действия.</span><span class="sxs-lookup"><span data-stu-id="e8c8f-122">The name of the activity.</span></span>|  
|<span data-ttu-id="e8c8f-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="e8c8f-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e8c8f-124">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e8c8f-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
