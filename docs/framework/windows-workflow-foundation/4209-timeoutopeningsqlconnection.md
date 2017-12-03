---
title: 4209 - TimeoutOpeningSqlConnection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 86d971a2e5f1257281c453e7eb0c2dc1755098d8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="c9043-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="c9043-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="c9043-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="c9043-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c9043-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="c9043-104">ID</span></span>|<span data-ttu-id="c9043-105">4209</span><span class="sxs-lookup"><span data-stu-id="c9043-105">4209</span></span>|  
|<span data-ttu-id="c9043-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="c9043-106">Keywords</span></span>|<span data-ttu-id="c9043-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="c9043-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="c9043-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="c9043-108">Level</span></span>|<span data-ttu-id="c9043-109">Ошибка</span><span class="sxs-lookup"><span data-stu-id="c9043-109">Error</span></span>|  
|<span data-ttu-id="c9043-110">Канал</span><span class="sxs-lookup"><span data-stu-id="c9043-110">Channel</span></span>|<span data-ttu-id="c9043-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c9043-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c9043-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c9043-112">Description</span></span>  
 <span data-ttu-id="c9043-113">Указывает, что при попытке открыть соединение SQL превышено время ожидания.</span><span class="sxs-lookup"><span data-stu-id="c9043-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c9043-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="c9043-114">Message</span></span>  
 <span data-ttu-id="c9043-115">Истекло время ожидания при открытии соединения SQL.</span><span class="sxs-lookup"><span data-stu-id="c9043-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="c9043-116">Не удалось выполнить операцию за выделенное время ожидания %1.</span><span class="sxs-lookup"><span data-stu-id="c9043-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="c9043-117">Возможно, выделенное для этой операции время было частью более длительного времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="c9043-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c9043-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="c9043-118">Details</span></span>  
  
|<span data-ttu-id="c9043-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="c9043-119">Data Item Name</span></span>|<span data-ttu-id="c9043-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="c9043-120">Data Item Type</span></span>|<span data-ttu-id="c9043-121">Описание</span><span class="sxs-lookup"><span data-stu-id="c9043-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c9043-122">Время ожидания</span><span class="sxs-lookup"><span data-stu-id="c9043-122">Timeout</span></span>|<span data-ttu-id="c9043-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="c9043-123">xs:string</span></span>|<span data-ttu-id="c9043-124">Значение времени ожидания для открытия соединения SQL.</span><span class="sxs-lookup"><span data-stu-id="c9043-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="c9043-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c9043-125">AppDomain</span></span>|<span data-ttu-id="c9043-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="c9043-126">xs:string</span></span>|<span data-ttu-id="c9043-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c9043-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
