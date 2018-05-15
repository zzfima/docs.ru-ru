---
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ede74eb642c5c2c79b90cf1458db424d9f83b087
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="a23b2-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="a23b2-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="a23b2-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="a23b2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a23b2-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="a23b2-104">ID</span></span>|<span data-ttu-id="a23b2-105">4211</span><span class="sxs-lookup"><span data-stu-id="a23b2-105">4211</span></span>|  
|<span data-ttu-id="a23b2-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a23b2-106">Keywords</span></span>|<span data-ttu-id="a23b2-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="a23b2-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="a23b2-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="a23b2-108">Level</span></span>|<span data-ttu-id="a23b2-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="a23b2-109">Warning</span></span>|  
|<span data-ttu-id="a23b2-110">Канал</span><span class="sxs-lookup"><span data-stu-id="a23b2-110">Channel</span></span>|<span data-ttu-id="a23b2-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a23b2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a23b2-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a23b2-112">Description</span></span>  
 <span data-ttu-id="a23b2-113">Указывает на повтор SQL с задержкой.</span><span class="sxs-lookup"><span data-stu-id="a23b2-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a23b2-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="a23b2-114">Message</span></span>  
 <span data-ttu-id="a23b2-115">Повторная попытка поместить SQL в очередь с задержкой %1 мс.</span><span class="sxs-lookup"><span data-stu-id="a23b2-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a23b2-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="a23b2-116">Details</span></span>  
  
|<span data-ttu-id="a23b2-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="a23b2-117">Data Item Name</span></span>|<span data-ttu-id="a23b2-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="a23b2-118">Data Item Type</span></span>|<span data-ttu-id="a23b2-119">Описание</span><span class="sxs-lookup"><span data-stu-id="a23b2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a23b2-120">Delay</span><span class="sxs-lookup"><span data-stu-id="a23b2-120">Delay</span></span>|<span data-ttu-id="a23b2-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="a23b2-121">xs:string</span></span>|<span data-ttu-id="a23b2-122">Задержка между попытками.</span><span class="sxs-lookup"><span data-stu-id="a23b2-122">The delay between retries.</span></span>|  
|<span data-ttu-id="a23b2-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a23b2-123">AppDomain</span></span>|<span data-ttu-id="a23b2-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a23b2-124">xs:string</span></span>|<span data-ttu-id="a23b2-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a23b2-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
