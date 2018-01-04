---
title: 4211 - QueuingSqlRetry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ffd44cf9d2333b22e3be809d05f2fa8c33d4cac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="672e3-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="672e3-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="672e3-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="672e3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="672e3-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="672e3-104">ID</span></span>|<span data-ttu-id="672e3-105">4211</span><span class="sxs-lookup"><span data-stu-id="672e3-105">4211</span></span>|  
|<span data-ttu-id="672e3-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="672e3-106">Keywords</span></span>|<span data-ttu-id="672e3-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="672e3-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="672e3-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="672e3-108">Level</span></span>|<span data-ttu-id="672e3-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="672e3-109">Warning</span></span>|  
|<span data-ttu-id="672e3-110">Канал</span><span class="sxs-lookup"><span data-stu-id="672e3-110">Channel</span></span>|<span data-ttu-id="672e3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="672e3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="672e3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="672e3-112">Description</span></span>  
 <span data-ttu-id="672e3-113">Указывает на повтор SQL с задержкой.</span><span class="sxs-lookup"><span data-stu-id="672e3-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="672e3-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="672e3-114">Message</span></span>  
 <span data-ttu-id="672e3-115">Повторная попытка поместить SQL в очередь с задержкой %1 мс.</span><span class="sxs-lookup"><span data-stu-id="672e3-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="672e3-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="672e3-116">Details</span></span>  
  
|<span data-ttu-id="672e3-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="672e3-117">Data Item Name</span></span>|<span data-ttu-id="672e3-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="672e3-118">Data Item Type</span></span>|<span data-ttu-id="672e3-119">Описание</span><span class="sxs-lookup"><span data-stu-id="672e3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="672e3-120">Delay</span><span class="sxs-lookup"><span data-stu-id="672e3-120">Delay</span></span>|<span data-ttu-id="672e3-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="672e3-121">xs:string</span></span>|<span data-ttu-id="672e3-122">Задержка между попытками.</span><span class="sxs-lookup"><span data-stu-id="672e3-122">The delay between retries.</span></span>|  
|<span data-ttu-id="672e3-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="672e3-123">AppDomain</span></span>|<span data-ttu-id="672e3-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="672e3-124">xs:string</span></span>|<span data-ttu-id="672e3-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="672e3-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
