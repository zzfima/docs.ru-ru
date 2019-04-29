---
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 9b7a463851d380eba1ef7b28fbc6decd0cfc979c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774222"
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="894bb-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="894bb-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="894bb-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="894bb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="894bb-104">ID</span><span class="sxs-lookup"><span data-stu-id="894bb-104">ID</span></span>|<span data-ttu-id="894bb-105">4212</span><span class="sxs-lookup"><span data-stu-id="894bb-105">4212</span></span>|  
|<span data-ttu-id="894bb-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="894bb-106">Keywords</span></span>|<span data-ttu-id="894bb-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="894bb-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="894bb-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="894bb-108">Level</span></span>|<span data-ttu-id="894bb-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="894bb-109">Warning</span></span>|  
|<span data-ttu-id="894bb-110">Канал</span><span class="sxs-lookup"><span data-stu-id="894bb-110">Channel</span></span>|<span data-ttu-id="894bb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="894bb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="894bb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="894bb-112">Description</span></span>  
 <span data-ttu-id="894bb-113">При попытке поставщика SQL получить блокировку для экземпляра истекло время ожидания.</span><span class="sxs-lookup"><span data-stu-id="894bb-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="894bb-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="894bb-114">Message</span></span>  
 <span data-ttu-id="894bb-115">Время ожидания при попытке получить блокировку для экземпляра.</span><span class="sxs-lookup"><span data-stu-id="894bb-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="894bb-116">Не удалось выполнить операцию за выделенное время ожидания %1.</span><span class="sxs-lookup"><span data-stu-id="894bb-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="894bb-117">Возможно, выделенное для этой операции время было частью более длительного времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="894bb-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="894bb-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="894bb-118">Details</span></span>  
  
|<span data-ttu-id="894bb-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="894bb-119">Data Item Name</span></span>|<span data-ttu-id="894bb-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="894bb-120">Data Item Type</span></span>|<span data-ttu-id="894bb-121">Описание</span><span class="sxs-lookup"><span data-stu-id="894bb-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="894bb-122">Задержка</span><span class="sxs-lookup"><span data-stu-id="894bb-122">Delay</span></span>|<span data-ttu-id="894bb-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="894bb-123">xs:string</span></span>|<span data-ttu-id="894bb-124">Задержка между попытками.</span><span class="sxs-lookup"><span data-stu-id="894bb-124">The delay between retries.</span></span>|  
|<span data-ttu-id="894bb-125">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="894bb-125">AppDomain</span></span>|<span data-ttu-id="894bb-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="894bb-126">xs:string</span></span>|<span data-ttu-id="894bb-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="894bb-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
