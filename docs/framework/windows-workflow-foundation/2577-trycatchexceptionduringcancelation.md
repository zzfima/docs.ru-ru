---
title: 2577 - TryCatchExceptionDuringCancelation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f1e851a50c9677b2f10ea3478c3599706007d4d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="f2fde-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="f2fde-102">2577 - TryCatchExceptionDuringCancelation</span></span>
## <a name="properties"></a><span data-ttu-id="f2fde-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="f2fde-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f2fde-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="f2fde-104">ID</span></span>|<span data-ttu-id="f2fde-105">2577</span><span class="sxs-lookup"><span data-stu-id="f2fde-105">2577</span></span>|  
|<span data-ttu-id="f2fde-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="f2fde-106">Keywords</span></span>|<span data-ttu-id="f2fde-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="f2fde-107">WFActivities</span></span>|  
|<span data-ttu-id="f2fde-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="f2fde-108">Level</span></span>|<span data-ttu-id="f2fde-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="f2fde-109">Warning</span></span>|  
|<span data-ttu-id="f2fde-110">Канал</span><span class="sxs-lookup"><span data-stu-id="f2fde-110">Channel</span></span>|<span data-ttu-id="f2fde-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f2fde-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f2fde-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f2fde-112">Description</span></span>  
 <span data-ttu-id="f2fde-113">Указывает, что дочернее действие для действия TryCatch вызвало исключение во время отмены.</span><span class="sxs-lookup"><span data-stu-id="f2fde-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f2fde-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f2fde-114">Message</span></span>  
 <span data-ttu-id="f2fde-115">При отмене дочернего действия для действия TryCatch «%1» произошло исключение.</span><span class="sxs-lookup"><span data-stu-id="f2fde-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f2fde-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="f2fde-116">Details</span></span>  
  
|<span data-ttu-id="f2fde-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="f2fde-117">Data Item Name</span></span>|<span data-ttu-id="f2fde-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="f2fde-118">Data Item Type</span></span>|<span data-ttu-id="f2fde-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f2fde-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f2fde-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f2fde-120">DisplayName</span></span>|<span data-ttu-id="f2fde-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2fde-121">xs:string</span></span>|<span data-ttu-id="f2fde-122">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="f2fde-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="f2fde-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f2fde-123">AppDomain</span></span>|<span data-ttu-id="f2fde-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2fde-124">xs:string</span></span>|<span data-ttu-id="f2fde-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f2fde-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
