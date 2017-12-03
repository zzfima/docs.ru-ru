---
title: 401 - StopSignPostEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 30e796dec45035e6b68659400ebbae1357137b27
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="401--stopsignpostevent"></a><span data-ttu-id="b1e2c-102">401 - StopSignPostEvent</span><span class="sxs-lookup"><span data-stu-id="b1e2c-102">401- StopSignPostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="b1e2c-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="b1e2c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b1e2c-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="b1e2c-104">ID</span></span>|<span data-ttu-id="b1e2c-105">401</span><span class="sxs-lookup"><span data-stu-id="b1e2c-105">401</span></span>|  
|<span data-ttu-id="b1e2c-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="b1e2c-106">Keywords</span></span>|<span data-ttu-id="b1e2c-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="b1e2c-107">Troubleshooting</span></span>|  
|<span data-ttu-id="b1e2c-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="b1e2c-108">Level</span></span>|<span data-ttu-id="b1e2c-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="b1e2c-109">Information</span></span>|  
|<span data-ttu-id="b1e2c-110">Канал</span><span class="sxs-lookup"><span data-stu-id="b1e2c-110">Channel</span></span>|<span data-ttu-id="b1e2c-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b1e2c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b1e2c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b1e2c-112">Description</span></span>  
 <span data-ttu-id="b1e2c-113">Это событие отмечает окончание сквозного действия.</span><span class="sxs-lookup"><span data-stu-id="b1e2c-113">This event marks the end of an end-to-end activity.</span></span> <span data-ttu-id="b1e2c-114">В ней содержится имя действия.</span><span class="sxs-lookup"><span data-stu-id="b1e2c-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b1e2c-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="b1e2c-115">Message</span></span>  
 <span data-ttu-id="b1e2c-116">Граница действия.</span><span class="sxs-lookup"><span data-stu-id="b1e2c-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b1e2c-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="b1e2c-117">Details</span></span>  
  
|<span data-ttu-id="b1e2c-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="b1e2c-118">Data Item Name</span></span>|<span data-ttu-id="b1e2c-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="b1e2c-119">Data Item Type</span></span>|<span data-ttu-id="b1e2c-120">Описание</span><span class="sxs-lookup"><span data-stu-id="b1e2c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b1e2c-121">Расширенные данные</span><span class="sxs-lookup"><span data-stu-id="b1e2c-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="b1e2c-122">Имя действия.</span><span class="sxs-lookup"><span data-stu-id="b1e2c-122">The name of the activity.</span></span>|  
|<span data-ttu-id="b1e2c-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="b1e2c-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b1e2c-124">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b1e2c-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
