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
ms.openlocfilehash: 346cb98b1285883a9a85f2c7abb6147f42734395
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="01123-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="01123-102">3508 - TrackingProfileNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="01123-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="01123-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="01123-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="01123-104">ID</span></span>|<span data-ttu-id="01123-105">3508</span><span class="sxs-lookup"><span data-stu-id="01123-105">3508</span></span>|  
|<span data-ttu-id="01123-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="01123-106">Keywords</span></span>|<span data-ttu-id="01123-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="01123-107">WFServices</span></span>|  
|<span data-ttu-id="01123-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="01123-108">Level</span></span>|<span data-ttu-id="01123-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="01123-109">Verbose</span></span>|  
|<span data-ttu-id="01123-110">Канал</span><span class="sxs-lookup"><span data-stu-id="01123-110">Channel</span></span>|<span data-ttu-id="01123-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="01123-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="01123-112">Описание</span><span class="sxs-lookup"><span data-stu-id="01123-112">Description</span></span>  
 <span data-ttu-id="01123-113">Указывает, что либо профиль TrackingProfile не найден в файле конфигурации, либо обнаружено несоответствие ActivityDefinitionId профилю.</span><span class="sxs-lookup"><span data-stu-id="01123-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="01123-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="01123-114">Message</span></span>  
 <span data-ttu-id="01123-115">Не найден TrackingProfile «%1» для ActivityDefinitionId «%2».</span><span class="sxs-lookup"><span data-stu-id="01123-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="01123-116">Профиль TrackingProfile не найден в файле конфигурации, или обнаружено несоответствие ActivityDefinitionId.</span><span class="sxs-lookup"><span data-stu-id="01123-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="01123-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="01123-117">Details</span></span>  
  
|<span data-ttu-id="01123-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="01123-118">Data Item Name</span></span>|<span data-ttu-id="01123-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="01123-119">Data Item Type</span></span>|<span data-ttu-id="01123-120">Описание</span><span class="sxs-lookup"><span data-stu-id="01123-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="01123-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="01123-121">TrackingProfile</span></span>|<span data-ttu-id="01123-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="01123-122">xs:string</span></span>|<span data-ttu-id="01123-123">Имя профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="01123-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="01123-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="01123-124">ActivityDefinitionId</span></span>|<span data-ttu-id="01123-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="01123-125">xs:string</span></span>|<span data-ttu-id="01123-126">Идентификатор определения действия.</span><span class="sxs-lookup"><span data-stu-id="01123-126">The activity definition id.</span></span>|  
|<span data-ttu-id="01123-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="01123-127">AppDomain</span></span>|<span data-ttu-id="01123-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="01123-128">xs:string</span></span>|<span data-ttu-id="01123-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="01123-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
