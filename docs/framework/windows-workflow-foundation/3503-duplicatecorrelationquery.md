---
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: 37a689b30b0bcab9124472deb98627afbe30dfee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511404"
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="ddfb2-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="ddfb2-102">3503 - DuplicateCorrelationQuery</span></span>
## <a name="properties"></a><span data-ttu-id="ddfb2-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="ddfb2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ddfb2-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="ddfb2-104">ID</span></span>|<span data-ttu-id="ddfb2-105">3503</span><span class="sxs-lookup"><span data-stu-id="ddfb2-105">3503</span></span>|  
|<span data-ttu-id="ddfb2-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ddfb2-106">Keywords</span></span>|<span data-ttu-id="ddfb2-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="ddfb2-107">WFServices</span></span>|  
|<span data-ttu-id="ddfb2-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="ddfb2-108">Level</span></span>|<span data-ttu-id="ddfb2-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="ddfb2-109">Warning</span></span>|  
|<span data-ttu-id="ddfb2-110">Канал</span><span class="sxs-lookup"><span data-stu-id="ddfb2-110">Channel</span></span>|<span data-ttu-id="ddfb2-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ddfb2-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ddfb2-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ddfb2-112">Description</span></span>  
 <span data-ttu-id="ddfb2-113">Указывает, что обнаружен повторяющийся запрос CorrelationQuery.</span><span class="sxs-lookup"><span data-stu-id="ddfb2-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="ddfb2-114">Повторяющийся запрос не будет использоваться при расчете корреляции.</span><span class="sxs-lookup"><span data-stu-id="ddfb2-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ddfb2-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ddfb2-115">Message</span></span>  
 <span data-ttu-id="ddfb2-116">Обнаружен повторяющийся запрос CorrelationQuery с параметром Where=«%1».</span><span class="sxs-lookup"><span data-stu-id="ddfb2-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="ddfb2-117">Это дубликат не будет использоваться при расчете корреляции.</span><span class="sxs-lookup"><span data-stu-id="ddfb2-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ddfb2-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ddfb2-118">Details</span></span>  
  
|<span data-ttu-id="ddfb2-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="ddfb2-119">Data Item Name</span></span>|<span data-ttu-id="ddfb2-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="ddfb2-120">Data Item Type</span></span>|<span data-ttu-id="ddfb2-121">Описание</span><span class="sxs-lookup"><span data-stu-id="ddfb2-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ddfb2-122">Where</span><span class="sxs-lookup"><span data-stu-id="ddfb2-122">Where</span></span>|<span data-ttu-id="ddfb2-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="ddfb2-123">xs:string</span></span>|<span data-ttu-id="ddfb2-124">Часть Where в запросе корреляции.</span><span class="sxs-lookup"><span data-stu-id="ddfb2-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="ddfb2-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ddfb2-125">AppDomain</span></span>|<span data-ttu-id="ddfb2-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="ddfb2-126">xs:string</span></span>|<span data-ttu-id="ddfb2-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ddfb2-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
