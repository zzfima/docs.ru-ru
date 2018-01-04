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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 997bdf4423364e9b5361635820849a6bde9e8960
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="0913d-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="0913d-102">3503 - DuplicateCorrelationQuery</span></span>
## <a name="properties"></a><span data-ttu-id="0913d-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="0913d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0913d-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="0913d-104">ID</span></span>|<span data-ttu-id="0913d-105">3503</span><span class="sxs-lookup"><span data-stu-id="0913d-105">3503</span></span>|  
|<span data-ttu-id="0913d-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="0913d-106">Keywords</span></span>|<span data-ttu-id="0913d-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="0913d-107">WFServices</span></span>|  
|<span data-ttu-id="0913d-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="0913d-108">Level</span></span>|<span data-ttu-id="0913d-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="0913d-109">Warning</span></span>|  
|<span data-ttu-id="0913d-110">Канал</span><span class="sxs-lookup"><span data-stu-id="0913d-110">Channel</span></span>|<span data-ttu-id="0913d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="0913d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0913d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0913d-112">Description</span></span>  
 <span data-ttu-id="0913d-113">Указывает, что обнаружен повторяющийся запрос CorrelationQuery.</span><span class="sxs-lookup"><span data-stu-id="0913d-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="0913d-114">Повторяющийся запрос не будет использоваться при расчете корреляции.</span><span class="sxs-lookup"><span data-stu-id="0913d-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0913d-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="0913d-115">Message</span></span>  
 <span data-ttu-id="0913d-116">Обнаружен повторяющийся запрос CorrelationQuery с параметром Where=«%1».</span><span class="sxs-lookup"><span data-stu-id="0913d-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="0913d-117">Это дубликат не будет использоваться при расчете корреляции.</span><span class="sxs-lookup"><span data-stu-id="0913d-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0913d-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="0913d-118">Details</span></span>  
  
|<span data-ttu-id="0913d-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="0913d-119">Data Item Name</span></span>|<span data-ttu-id="0913d-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="0913d-120">Data Item Type</span></span>|<span data-ttu-id="0913d-121">Описание</span><span class="sxs-lookup"><span data-stu-id="0913d-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0913d-122">Where</span><span class="sxs-lookup"><span data-stu-id="0913d-122">Where</span></span>|<span data-ttu-id="0913d-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="0913d-123">xs:string</span></span>|<span data-ttu-id="0913d-124">Часть Where в запросе корреляции.</span><span class="sxs-lookup"><span data-stu-id="0913d-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="0913d-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0913d-125">AppDomain</span></span>|<span data-ttu-id="0913d-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="0913d-126">xs:string</span></span>|<span data-ttu-id="0913d-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0913d-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
