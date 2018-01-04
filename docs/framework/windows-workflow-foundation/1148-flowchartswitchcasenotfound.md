---
title: 1148 - FlowchartSwitchCaseNotFound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9ee7fcee-e040-4306-968e-ed840a1cb00c
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0735351f0f5fb830b889d012fd91e3cc99eb255f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1148---flowchartswitchcasenotfound"></a><span data-ttu-id="271cf-102">1148 - FlowchartSwitchCaseNotFound</span><span class="sxs-lookup"><span data-stu-id="271cf-102">1148 - FlowchartSwitchCaseNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="271cf-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="271cf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="271cf-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="271cf-104">ID</span></span>|<span data-ttu-id="271cf-105">1148</span><span class="sxs-lookup"><span data-stu-id="271cf-105">1148</span></span>|  
|<span data-ttu-id="271cf-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="271cf-106">Keywords</span></span>|<span data-ttu-id="271cf-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="271cf-107">WFActivities</span></span>|  
|<span data-ttu-id="271cf-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="271cf-108">Level</span></span>|<span data-ttu-id="271cf-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="271cf-109">Information</span></span>|  
|<span data-ttu-id="271cf-110">Канал</span><span class="sxs-lookup"><span data-stu-id="271cf-110">Channel</span></span>|<span data-ttu-id="271cf-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="271cf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="271cf-112">Описание</span><span class="sxs-lookup"><span data-stu-id="271cf-112">Description</span></span>  
 <span data-ttu-id="271cf-113">Указывает, что в параметре блок-схемы не найден ни соответствующий вариант, ни вариант по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="271cf-113">Indicates that neither a matching case or a default case in a Flowchart switch could be found.</span></span> <span data-ttu-id="271cf-114">Выполнение блок-схемы будет завершено.</span><span class="sxs-lookup"><span data-stu-id="271cf-114">Flowchart execution will end.</span></span>  
  
## <a name="message"></a><span data-ttu-id="271cf-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="271cf-115">Message</span></span>  
 <span data-ttu-id="271cf-116">Блок-схема «%1»/FlowSwitch - не удалось найти ни действие Case, ни действие Default Case, соответствующее результату выражения Expression.</span><span class="sxs-lookup"><span data-stu-id="271cf-116">Flowchart '%1'/FlowSwitch - could find neither a Case activity nor a Default Case matching the Expression result.</span></span> <span data-ttu-id="271cf-117">Выполнение блок-схемы будет завершено.</span><span class="sxs-lookup"><span data-stu-id="271cf-117">Flowchart execution will end.</span></span>  
  
## <a name="details"></a><span data-ttu-id="271cf-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="271cf-118">Details</span></span>  
  
|<span data-ttu-id="271cf-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="271cf-119">Data Item Name</span></span>|<span data-ttu-id="271cf-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="271cf-120">Data Item Type</span></span>|<span data-ttu-id="271cf-121">Описание</span><span class="sxs-lookup"><span data-stu-id="271cf-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="271cf-122">Блок-схема</span><span class="sxs-lookup"><span data-stu-id="271cf-122">FlowChart</span></span>|<span data-ttu-id="271cf-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="271cf-123">xs:string</span></span>|<span data-ttu-id="271cf-124">Отображаемое имя блок-схемы.</span><span class="sxs-lookup"><span data-stu-id="271cf-124">The display name of the FlowChart.</span></span>|  
|<span data-ttu-id="271cf-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="271cf-125">AppDomain</span></span>|<span data-ttu-id="271cf-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="271cf-126">xs:string</span></span>|<span data-ttu-id="271cf-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="271cf-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
