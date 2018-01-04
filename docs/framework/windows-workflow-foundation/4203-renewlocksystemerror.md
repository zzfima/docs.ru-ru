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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8fabe6f2c023bf9b997d2a4e19b4a3755c93f408
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="308b4-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="308b4-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="308b4-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="308b4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="308b4-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="308b4-104">ID</span></span>|<span data-ttu-id="308b4-105">4203</span><span class="sxs-lookup"><span data-stu-id="308b4-105">4203</span></span>|  
|<span data-ttu-id="308b4-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="308b4-106">Keywords</span></span>|<span data-ttu-id="308b4-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="308b4-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="308b4-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="308b4-108">Level</span></span>|<span data-ttu-id="308b4-109">Ошибка</span><span class="sxs-lookup"><span data-stu-id="308b4-109">Error</span></span>|  
|<span data-ttu-id="308b4-110">Канал</span><span class="sxs-lookup"><span data-stu-id="308b4-110">Channel</span></span>|<span data-ttu-id="308b4-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="308b4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="308b4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="308b4-112">Description</span></span>  
 <span data-ttu-id="308b4-113">Указывает, что поставщику SQL не удалось продлить срок блокировки либо из-за того, что срок блокировки уже истек, либо из-за того, что владелец блокировки был удален.</span><span class="sxs-lookup"><span data-stu-id="308b4-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="308b4-114">SqlWorkflowInstanceStore будет прервано.</span><span class="sxs-lookup"><span data-stu-id="308b4-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="308b4-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="308b4-115">Message</span></span>  
 <span data-ttu-id="308b4-116">Не удалось увеличить срок окончания блокировки, срок окончания блокировки уже истек или владелец блокировки удален.</span><span class="sxs-lookup"><span data-stu-id="308b4-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="308b4-117">Прерывание блокировки SqlWorkflowInstanceStore.</span><span class="sxs-lookup"><span data-stu-id="308b4-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="308b4-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="308b4-118">Details</span></span>  
  
|<span data-ttu-id="308b4-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="308b4-119">Data Item Name</span></span>|<span data-ttu-id="308b4-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="308b4-120">Data Item Type</span></span>|<span data-ttu-id="308b4-121">Описание</span><span class="sxs-lookup"><span data-stu-id="308b4-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="308b4-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="308b4-122">AppDomain</span></span>|<span data-ttu-id="308b4-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="308b4-123">xs:string</span></span>|<span data-ttu-id="308b4-124">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="308b4-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
