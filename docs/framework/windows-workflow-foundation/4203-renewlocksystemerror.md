---
title: 4203 - RenewLockSystemError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 06d4695eb125475f41a94c7f2266df6d2c3f400d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="8bd91-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="8bd91-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="8bd91-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="8bd91-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8bd91-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="8bd91-104">ID</span></span>|<span data-ttu-id="8bd91-105">4203</span><span class="sxs-lookup"><span data-stu-id="8bd91-105">4203</span></span>|  
|<span data-ttu-id="8bd91-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8bd91-106">Keywords</span></span>|<span data-ttu-id="8bd91-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="8bd91-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="8bd91-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="8bd91-108">Level</span></span>|<span data-ttu-id="8bd91-109">Ошибка</span><span class="sxs-lookup"><span data-stu-id="8bd91-109">Error</span></span>|  
|<span data-ttu-id="8bd91-110">Канал</span><span class="sxs-lookup"><span data-stu-id="8bd91-110">Channel</span></span>|<span data-ttu-id="8bd91-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8bd91-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8bd91-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8bd91-112">Description</span></span>  
 <span data-ttu-id="8bd91-113">Указывает, что поставщику SQL не удалось продлить срок блокировки либо из-за того, что срок блокировки уже истек, либо из-за того, что владелец блокировки был удален.</span><span class="sxs-lookup"><span data-stu-id="8bd91-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="8bd91-114">SqlWorkflowInstanceStore будет прервано.</span><span class="sxs-lookup"><span data-stu-id="8bd91-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8bd91-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="8bd91-115">Message</span></span>  
 <span data-ttu-id="8bd91-116">Не удалось увеличить срок окончания блокировки, срок окончания блокировки уже истек или владелец блокировки удален.</span><span class="sxs-lookup"><span data-stu-id="8bd91-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="8bd91-117">Прерывание блокировки SqlWorkflowInstanceStore.</span><span class="sxs-lookup"><span data-stu-id="8bd91-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8bd91-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="8bd91-118">Details</span></span>  
  
|<span data-ttu-id="8bd91-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="8bd91-119">Data Item Name</span></span>|<span data-ttu-id="8bd91-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="8bd91-120">Data Item Type</span></span>|<span data-ttu-id="8bd91-121">Описание</span><span class="sxs-lookup"><span data-stu-id="8bd91-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8bd91-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8bd91-122">AppDomain</span></span>|<span data-ttu-id="8bd91-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="8bd91-123">xs:string</span></span>|<span data-ttu-id="8bd91-124">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8bd91-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
