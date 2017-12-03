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
ms.openlocfilehash: b9259ca71a21e36eaae06d33920adec538e36d98
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="403---suspendsignpostevent"></a><span data-ttu-id="93b14-102">403 - SuspendSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="93b14-102">403 - SuspendSignpostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="93b14-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="93b14-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="93b14-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="93b14-104">ID</span></span>|<span data-ttu-id="93b14-105">403</span><span class="sxs-lookup"><span data-stu-id="93b14-105">403</span></span>|  
|<span data-ttu-id="93b14-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="93b14-106">Keywords</span></span>|<span data-ttu-id="93b14-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="93b14-107">Troubleshooting</span></span>|  
|<span data-ttu-id="93b14-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="93b14-108">Level</span></span>|<span data-ttu-id="93b14-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="93b14-109">Information</span></span>|  
|<span data-ttu-id="93b14-110">Канал</span><span class="sxs-lookup"><span data-stu-id="93b14-110">Channel</span></span>|<span data-ttu-id="93b14-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="93b14-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="93b14-112">Описание</span><span class="sxs-lookup"><span data-stu-id="93b14-112">Description</span></span>  
 <span data-ttu-id="93b14-113">Это событие сигнализирует о приостановке сквозного действия.</span><span class="sxs-lookup"><span data-stu-id="93b14-113">This event marks the suspension of an end-to-end activity.</span></span> <span data-ttu-id="93b14-114">В ней содержится имя действия.</span><span class="sxs-lookup"><span data-stu-id="93b14-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="93b14-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="93b14-115">Message</span></span>  
 <span data-ttu-id="93b14-116">Граница действия.</span><span class="sxs-lookup"><span data-stu-id="93b14-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="93b14-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="93b14-117">Details</span></span>  
  
|<span data-ttu-id="93b14-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="93b14-118">Data Item Name</span></span>|<span data-ttu-id="93b14-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="93b14-119">Data Item Type</span></span>|<span data-ttu-id="93b14-120">Описание</span><span class="sxs-lookup"><span data-stu-id="93b14-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="93b14-121">Расширенные данные</span><span class="sxs-lookup"><span data-stu-id="93b14-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="93b14-122">Имя действия.</span><span class="sxs-lookup"><span data-stu-id="93b14-122">The name of the activity.</span></span>|  
|<span data-ttu-id="93b14-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="93b14-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="93b14-124">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="93b14-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
