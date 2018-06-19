---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 94c7ce231df241778f7c6ec5fe5998eae364750d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512188"
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="28389-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="28389-102">3508 - TrackingProfileNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="28389-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="28389-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28389-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="28389-104">ID</span></span>|<span data-ttu-id="28389-105">3508</span><span class="sxs-lookup"><span data-stu-id="28389-105">3508</span></span>|  
|<span data-ttu-id="28389-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="28389-106">Keywords</span></span>|<span data-ttu-id="28389-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="28389-107">WFServices</span></span>|  
|<span data-ttu-id="28389-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="28389-108">Level</span></span>|<span data-ttu-id="28389-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="28389-109">Verbose</span></span>|  
|<span data-ttu-id="28389-110">Канал</span><span class="sxs-lookup"><span data-stu-id="28389-110">Channel</span></span>|<span data-ttu-id="28389-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="28389-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="28389-112">Описание</span><span class="sxs-lookup"><span data-stu-id="28389-112">Description</span></span>  
 <span data-ttu-id="28389-113">Указывает, что либо профиль TrackingProfile не найден в файле конфигурации, либо обнаружено несоответствие ActivityDefinitionId профилю.</span><span class="sxs-lookup"><span data-stu-id="28389-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="28389-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="28389-114">Message</span></span>  
 <span data-ttu-id="28389-115">Не найден TrackingProfile «%1» для ActivityDefinitionId «%2».</span><span class="sxs-lookup"><span data-stu-id="28389-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="28389-116">Профиль TrackingProfile не найден в файле конфигурации, или обнаружено несоответствие ActivityDefinitionId.</span><span class="sxs-lookup"><span data-stu-id="28389-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="28389-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="28389-117">Details</span></span>  
  
|<span data-ttu-id="28389-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="28389-118">Data Item Name</span></span>|<span data-ttu-id="28389-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="28389-119">Data Item Type</span></span>|<span data-ttu-id="28389-120">Описание</span><span class="sxs-lookup"><span data-stu-id="28389-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="28389-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="28389-121">TrackingProfile</span></span>|<span data-ttu-id="28389-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="28389-122">xs:string</span></span>|<span data-ttu-id="28389-123">Имя профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="28389-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="28389-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="28389-124">ActivityDefinitionId</span></span>|<span data-ttu-id="28389-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="28389-125">xs:string</span></span>|<span data-ttu-id="28389-126">Идентификатор определения действия.</span><span class="sxs-lookup"><span data-stu-id="28389-126">The activity definition id.</span></span>|  
|<span data-ttu-id="28389-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="28389-127">AppDomain</span></span>|<span data-ttu-id="28389-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="28389-128">xs:string</span></span>|<span data-ttu-id="28389-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="28389-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
