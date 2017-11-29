---
title: 3503 - DuplicateCorrelationQuery
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 60367b33e1e57cce8646b4fcde79c7d4fd20a4cc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="b8446-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="b8446-102">3503 - DuplicateCorrelationQuery</span></span>
## <a name="properties"></a><span data-ttu-id="b8446-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="b8446-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8446-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="b8446-104">ID</span></span>|<span data-ttu-id="b8446-105">3503</span><span class="sxs-lookup"><span data-stu-id="b8446-105">3503</span></span>|  
|<span data-ttu-id="b8446-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="b8446-106">Keywords</span></span>|<span data-ttu-id="b8446-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="b8446-107">WFServices</span></span>|  
|<span data-ttu-id="b8446-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="b8446-108">Level</span></span>|<span data-ttu-id="b8446-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="b8446-109">Warning</span></span>|  
|<span data-ttu-id="b8446-110">Канал</span><span class="sxs-lookup"><span data-stu-id="b8446-110">Channel</span></span>|<span data-ttu-id="b8446-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b8446-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b8446-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b8446-112">Description</span></span>  
 <span data-ttu-id="b8446-113">Указывает, что обнаружен повторяющийся запрос CorrelationQuery.</span><span class="sxs-lookup"><span data-stu-id="b8446-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="b8446-114">Повторяющийся запрос не будет использоваться при расчете корреляции.</span><span class="sxs-lookup"><span data-stu-id="b8446-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b8446-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="b8446-115">Message</span></span>  
 <span data-ttu-id="b8446-116">Обнаружен повторяющийся запрос CorrelationQuery с параметром Where=«%1».</span><span class="sxs-lookup"><span data-stu-id="b8446-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="b8446-117">Это дубликат не будет использоваться при расчете корреляции.</span><span class="sxs-lookup"><span data-stu-id="b8446-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b8446-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="b8446-118">Details</span></span>  
  
|<span data-ttu-id="b8446-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="b8446-119">Data Item Name</span></span>|<span data-ttu-id="b8446-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="b8446-120">Data Item Type</span></span>|<span data-ttu-id="b8446-121">Описание</span><span class="sxs-lookup"><span data-stu-id="b8446-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b8446-122">Where</span><span class="sxs-lookup"><span data-stu-id="b8446-122">Where</span></span>|<span data-ttu-id="b8446-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="b8446-123">xs:string</span></span>|<span data-ttu-id="b8446-124">Часть Where в запросе корреляции.</span><span class="sxs-lookup"><span data-stu-id="b8446-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="b8446-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b8446-125">AppDomain</span></span>|<span data-ttu-id="b8446-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="b8446-126">xs:string</span></span>|<span data-ttu-id="b8446-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b8446-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
