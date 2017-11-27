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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fb5636057193fcfb59e5062f6f3833a62b4f3027
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="85d97-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="85d97-102">3508 - TrackingProfileNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="85d97-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="85d97-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="85d97-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="85d97-104">ID</span></span>|<span data-ttu-id="85d97-105">3508</span><span class="sxs-lookup"><span data-stu-id="85d97-105">3508</span></span>|  
|<span data-ttu-id="85d97-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="85d97-106">Keywords</span></span>|<span data-ttu-id="85d97-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="85d97-107">WFServices</span></span>|  
|<span data-ttu-id="85d97-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="85d97-108">Level</span></span>|<span data-ttu-id="85d97-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="85d97-109">Verbose</span></span>|  
|<span data-ttu-id="85d97-110">Канал</span><span class="sxs-lookup"><span data-stu-id="85d97-110">Channel</span></span>|<span data-ttu-id="85d97-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="85d97-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="85d97-112">Описание</span><span class="sxs-lookup"><span data-stu-id="85d97-112">Description</span></span>  
 <span data-ttu-id="85d97-113">Указывает, что либо профиль TrackingProfile не найден в файле конфигурации, либо обнаружено несоответствие ActivityDefinitionId профилю.</span><span class="sxs-lookup"><span data-stu-id="85d97-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="85d97-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="85d97-114">Message</span></span>  
 <span data-ttu-id="85d97-115">Не найден TrackingProfile «%1» для ActivityDefinitionId «%2».</span><span class="sxs-lookup"><span data-stu-id="85d97-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="85d97-116">Профиль TrackingProfile не найден в файле конфигурации, или обнаружено несоответствие ActivityDefinitionId.</span><span class="sxs-lookup"><span data-stu-id="85d97-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="85d97-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="85d97-117">Details</span></span>  
  
|<span data-ttu-id="85d97-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="85d97-118">Data Item Name</span></span>|<span data-ttu-id="85d97-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="85d97-119">Data Item Type</span></span>|<span data-ttu-id="85d97-120">Описание</span><span class="sxs-lookup"><span data-stu-id="85d97-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="85d97-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="85d97-121">TrackingProfile</span></span>|<span data-ttu-id="85d97-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="85d97-122">xs:string</span></span>|<span data-ttu-id="85d97-123">Имя профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="85d97-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="85d97-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="85d97-124">ActivityDefinitionId</span></span>|<span data-ttu-id="85d97-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="85d97-125">xs:string</span></span>|<span data-ttu-id="85d97-126">Идентификатор определения действия.</span><span class="sxs-lookup"><span data-stu-id="85d97-126">The activity definition id.</span></span>|  
|<span data-ttu-id="85d97-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="85d97-127">AppDomain</span></span>|<span data-ttu-id="85d97-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="85d97-128">xs:string</span></span>|<span data-ttu-id="85d97-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="85d97-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
