---
title: 4212 - LockRetryTimeout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abe1f560cc984551f069a75873a7e5545aec03cf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="fadb0-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="fadb0-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="fadb0-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="fadb0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fadb0-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="fadb0-104">ID</span></span>|<span data-ttu-id="fadb0-105">4212</span><span class="sxs-lookup"><span data-stu-id="fadb0-105">4212</span></span>|  
|<span data-ttu-id="fadb0-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="fadb0-106">Keywords</span></span>|<span data-ttu-id="fadb0-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="fadb0-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="fadb0-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="fadb0-108">Level</span></span>|<span data-ttu-id="fadb0-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="fadb0-109">Warning</span></span>|  
|<span data-ttu-id="fadb0-110">Канал</span><span class="sxs-lookup"><span data-stu-id="fadb0-110">Channel</span></span>|<span data-ttu-id="fadb0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fadb0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fadb0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fadb0-112">Description</span></span>  
 <span data-ttu-id="fadb0-113">При попытке поставщика SQL получить блокировку для экземпляра истекло время ожидания.</span><span class="sxs-lookup"><span data-stu-id="fadb0-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fadb0-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="fadb0-114">Message</span></span>  
 <span data-ttu-id="fadb0-115">Время ожидания при попытке получить блокировку для экземпляра.</span><span class="sxs-lookup"><span data-stu-id="fadb0-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="fadb0-116">Не удалось выполнить операцию за выделенное время ожидания %1.</span><span class="sxs-lookup"><span data-stu-id="fadb0-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="fadb0-117">Возможно, выделенное для этой операции время было частью более длительного времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="fadb0-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fadb0-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="fadb0-118">Details</span></span>  
  
|<span data-ttu-id="fadb0-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="fadb0-119">Data Item Name</span></span>|<span data-ttu-id="fadb0-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="fadb0-120">Data Item Type</span></span>|<span data-ttu-id="fadb0-121">Описание</span><span class="sxs-lookup"><span data-stu-id="fadb0-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fadb0-122">Delay</span><span class="sxs-lookup"><span data-stu-id="fadb0-122">Delay</span></span>|<span data-ttu-id="fadb0-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="fadb0-123">xs:string</span></span>|<span data-ttu-id="fadb0-124">Задержка между попытками.</span><span class="sxs-lookup"><span data-stu-id="fadb0-124">The delay between retries.</span></span>|  
|<span data-ttu-id="fadb0-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fadb0-125">AppDomain</span></span>|<span data-ttu-id="fadb0-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="fadb0-126">xs:string</span></span>|<span data-ttu-id="fadb0-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fadb0-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
