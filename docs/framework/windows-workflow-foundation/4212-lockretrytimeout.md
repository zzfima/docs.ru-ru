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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 897e6ef8b739654a61058106966c870c47f8129a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="f1322-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="f1322-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="f1322-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="f1322-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f1322-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="f1322-104">ID</span></span>|<span data-ttu-id="f1322-105">4212</span><span class="sxs-lookup"><span data-stu-id="f1322-105">4212</span></span>|  
|<span data-ttu-id="f1322-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="f1322-106">Keywords</span></span>|<span data-ttu-id="f1322-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="f1322-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="f1322-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="f1322-108">Level</span></span>|<span data-ttu-id="f1322-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="f1322-109">Warning</span></span>|  
|<span data-ttu-id="f1322-110">Канал</span><span class="sxs-lookup"><span data-stu-id="f1322-110">Channel</span></span>|<span data-ttu-id="f1322-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f1322-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f1322-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f1322-112">Description</span></span>  
 <span data-ttu-id="f1322-113">При попытке поставщика SQL получить блокировку для экземпляра истекло время ожидания.</span><span class="sxs-lookup"><span data-stu-id="f1322-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f1322-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f1322-114">Message</span></span>  
 <span data-ttu-id="f1322-115">Время ожидания при попытке получить блокировку для экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f1322-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="f1322-116">Не удалось выполнить операцию за выделенное время ожидания %1.</span><span class="sxs-lookup"><span data-stu-id="f1322-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="f1322-117">Возможно, выделенное для этой операции время было частью более длительного времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="f1322-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f1322-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="f1322-118">Details</span></span>  
  
|<span data-ttu-id="f1322-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="f1322-119">Data Item Name</span></span>|<span data-ttu-id="f1322-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="f1322-120">Data Item Type</span></span>|<span data-ttu-id="f1322-121">Описание</span><span class="sxs-lookup"><span data-stu-id="f1322-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f1322-122">Delay</span><span class="sxs-lookup"><span data-stu-id="f1322-122">Delay</span></span>|<span data-ttu-id="f1322-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="f1322-123">xs:string</span></span>|<span data-ttu-id="f1322-124">Задержка между попытками.</span><span class="sxs-lookup"><span data-stu-id="f1322-124">The delay between retries.</span></span>|  
|<span data-ttu-id="f1322-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f1322-125">AppDomain</span></span>|<span data-ttu-id="f1322-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="f1322-126">xs:string</span></span>|<span data-ttu-id="f1322-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f1322-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
