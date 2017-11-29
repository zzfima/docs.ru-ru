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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2a4bc0d9ab45fe8e2f025c651fce137d6a4255bc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="519e9-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="519e9-102">2577 - TryCatchExceptionDuringCancelation</span></span>
## <a name="properties"></a><span data-ttu-id="519e9-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="519e9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="519e9-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="519e9-104">ID</span></span>|<span data-ttu-id="519e9-105">2577</span><span class="sxs-lookup"><span data-stu-id="519e9-105">2577</span></span>|  
|<span data-ttu-id="519e9-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="519e9-106">Keywords</span></span>|<span data-ttu-id="519e9-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="519e9-107">WFActivities</span></span>|  
|<span data-ttu-id="519e9-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="519e9-108">Level</span></span>|<span data-ttu-id="519e9-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="519e9-109">Warning</span></span>|  
|<span data-ttu-id="519e9-110">Канал</span><span class="sxs-lookup"><span data-stu-id="519e9-110">Channel</span></span>|<span data-ttu-id="519e9-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="519e9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="519e9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="519e9-112">Description</span></span>  
 <span data-ttu-id="519e9-113">Указывает, что дочернее действие для действия TryCatch вызвало исключение во время отмены.</span><span class="sxs-lookup"><span data-stu-id="519e9-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="519e9-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="519e9-114">Message</span></span>  
 <span data-ttu-id="519e9-115">При отмене дочернего действия для действия TryCatch «%1» произошло исключение.</span><span class="sxs-lookup"><span data-stu-id="519e9-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="519e9-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="519e9-116">Details</span></span>  
  
|<span data-ttu-id="519e9-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="519e9-117">Data Item Name</span></span>|<span data-ttu-id="519e9-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="519e9-118">Data Item Type</span></span>|<span data-ttu-id="519e9-119">Описание</span><span class="sxs-lookup"><span data-stu-id="519e9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="519e9-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="519e9-120">DisplayName</span></span>|<span data-ttu-id="519e9-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="519e9-121">xs:string</span></span>|<span data-ttu-id="519e9-122">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="519e9-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="519e9-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="519e9-123">AppDomain</span></span>|<span data-ttu-id="519e9-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="519e9-124">xs:string</span></span>|<span data-ttu-id="519e9-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="519e9-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
