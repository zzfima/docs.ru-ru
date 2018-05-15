---
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 9b7a463851d380eba1ef7b28fbc6decd0cfc979c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="ff4d3-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="ff4d3-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="ff4d3-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="ff4d3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ff4d3-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="ff4d3-104">ID</span></span>|<span data-ttu-id="ff4d3-105">4212</span><span class="sxs-lookup"><span data-stu-id="ff4d3-105">4212</span></span>|  
|<span data-ttu-id="ff4d3-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ff4d3-106">Keywords</span></span>|<span data-ttu-id="ff4d3-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="ff4d3-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="ff4d3-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="ff4d3-108">Level</span></span>|<span data-ttu-id="ff4d3-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="ff4d3-109">Warning</span></span>|  
|<span data-ttu-id="ff4d3-110">Канал</span><span class="sxs-lookup"><span data-stu-id="ff4d3-110">Channel</span></span>|<span data-ttu-id="ff4d3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ff4d3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ff4d3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ff4d3-112">Description</span></span>  
 <span data-ttu-id="ff4d3-113">При попытке поставщика SQL получить блокировку для экземпляра истекло время ожидания.</span><span class="sxs-lookup"><span data-stu-id="ff4d3-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ff4d3-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ff4d3-114">Message</span></span>  
 <span data-ttu-id="ff4d3-115">Время ожидания при попытке получить блокировку для экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ff4d3-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="ff4d3-116">Не удалось выполнить операцию за выделенное время ожидания %1.</span><span class="sxs-lookup"><span data-stu-id="ff4d3-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="ff4d3-117">Возможно, выделенное для этой операции время было частью более длительного времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="ff4d3-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ff4d3-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ff4d3-118">Details</span></span>  
  
|<span data-ttu-id="ff4d3-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="ff4d3-119">Data Item Name</span></span>|<span data-ttu-id="ff4d3-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="ff4d3-120">Data Item Type</span></span>|<span data-ttu-id="ff4d3-121">Описание</span><span class="sxs-lookup"><span data-stu-id="ff4d3-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ff4d3-122">Delay</span><span class="sxs-lookup"><span data-stu-id="ff4d3-122">Delay</span></span>|<span data-ttu-id="ff4d3-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="ff4d3-123">xs:string</span></span>|<span data-ttu-id="ff4d3-124">Задержка между попытками.</span><span class="sxs-lookup"><span data-stu-id="ff4d3-124">The delay between retries.</span></span>|  
|<span data-ttu-id="ff4d3-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ff4d3-125">AppDomain</span></span>|<span data-ttu-id="ff4d3-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="ff4d3-126">xs:string</span></span>|<span data-ttu-id="ff4d3-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ff4d3-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
