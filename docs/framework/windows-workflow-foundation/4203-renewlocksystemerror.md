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
ms.openlocfilehash: 9c2214ec48f0c1cba1e3aacad0eaa5a29625f9c4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="f23be-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="f23be-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="f23be-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="f23be-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f23be-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="f23be-104">ID</span></span>|<span data-ttu-id="f23be-105">4203</span><span class="sxs-lookup"><span data-stu-id="f23be-105">4203</span></span>|  
|<span data-ttu-id="f23be-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="f23be-106">Keywords</span></span>|<span data-ttu-id="f23be-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="f23be-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="f23be-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="f23be-108">Level</span></span>|<span data-ttu-id="f23be-109">Ошибка</span><span class="sxs-lookup"><span data-stu-id="f23be-109">Error</span></span>|  
|<span data-ttu-id="f23be-110">Канал</span><span class="sxs-lookup"><span data-stu-id="f23be-110">Channel</span></span>|<span data-ttu-id="f23be-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f23be-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f23be-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f23be-112">Description</span></span>  
 <span data-ttu-id="f23be-113">Указывает, что поставщику SQL не удалось продлить срок блокировки либо из-за того, что срок блокировки уже истек, либо из-за того, что владелец блокировки был удален.</span><span class="sxs-lookup"><span data-stu-id="f23be-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="f23be-114">SqlWorkflowInstanceStore будет прервано.</span><span class="sxs-lookup"><span data-stu-id="f23be-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f23be-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f23be-115">Message</span></span>  
 <span data-ttu-id="f23be-116">Не удалось увеличить срок окончания блокировки, срок окончания блокировки уже истек или владелец блокировки удален.</span><span class="sxs-lookup"><span data-stu-id="f23be-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="f23be-117">Прерывание блокировки SqlWorkflowInstanceStore.</span><span class="sxs-lookup"><span data-stu-id="f23be-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f23be-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="f23be-118">Details</span></span>  
  
|<span data-ttu-id="f23be-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="f23be-119">Data Item Name</span></span>|<span data-ttu-id="f23be-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="f23be-120">Data Item Type</span></span>|<span data-ttu-id="f23be-121">Описание</span><span class="sxs-lookup"><span data-stu-id="f23be-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f23be-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f23be-122">AppDomain</span></span>|<span data-ttu-id="f23be-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="f23be-123">xs:string</span></span>|<span data-ttu-id="f23be-124">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f23be-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
