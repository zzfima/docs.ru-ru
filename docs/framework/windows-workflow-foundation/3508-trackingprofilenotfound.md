---
title: 3508 - TrackingProfileNotFound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 34812b6ddefb69c053cfefa91d7227a7bf15f42e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="76415-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="76415-102">3508 - TrackingProfileNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="76415-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="76415-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="76415-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="76415-104">ID</span></span>|<span data-ttu-id="76415-105">3508</span><span class="sxs-lookup"><span data-stu-id="76415-105">3508</span></span>|  
|<span data-ttu-id="76415-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="76415-106">Keywords</span></span>|<span data-ttu-id="76415-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="76415-107">WFServices</span></span>|  
|<span data-ttu-id="76415-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="76415-108">Level</span></span>|<span data-ttu-id="76415-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="76415-109">Verbose</span></span>|  
|<span data-ttu-id="76415-110">Канал</span><span class="sxs-lookup"><span data-stu-id="76415-110">Channel</span></span>|<span data-ttu-id="76415-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="76415-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="76415-112">Описание</span><span class="sxs-lookup"><span data-stu-id="76415-112">Description</span></span>  
 <span data-ttu-id="76415-113">Указывает, что либо профиль TrackingProfile не найден в файле конфигурации, либо обнаружено несоответствие ActivityDefinitionId профилю.</span><span class="sxs-lookup"><span data-stu-id="76415-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="76415-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="76415-114">Message</span></span>  
 <span data-ttu-id="76415-115">Не найден TrackingProfile «%1» для ActivityDefinitionId «%2».</span><span class="sxs-lookup"><span data-stu-id="76415-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="76415-116">Профиль TrackingProfile не найден в файле конфигурации, или обнаружено несоответствие ActivityDefinitionId.</span><span class="sxs-lookup"><span data-stu-id="76415-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="76415-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="76415-117">Details</span></span>  
  
|<span data-ttu-id="76415-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="76415-118">Data Item Name</span></span>|<span data-ttu-id="76415-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="76415-119">Data Item Type</span></span>|<span data-ttu-id="76415-120">Описание</span><span class="sxs-lookup"><span data-stu-id="76415-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="76415-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="76415-121">TrackingProfile</span></span>|<span data-ttu-id="76415-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="76415-122">xs:string</span></span>|<span data-ttu-id="76415-123">Имя профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="76415-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="76415-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="76415-124">ActivityDefinitionId</span></span>|<span data-ttu-id="76415-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="76415-125">xs:string</span></span>|<span data-ttu-id="76415-126">Идентификатор определения действия.</span><span class="sxs-lookup"><span data-stu-id="76415-126">The activity definition id.</span></span>|  
|<span data-ttu-id="76415-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="76415-127">AppDomain</span></span>|<span data-ttu-id="76415-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="76415-128">xs:string</span></span>|<span data-ttu-id="76415-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="76415-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
