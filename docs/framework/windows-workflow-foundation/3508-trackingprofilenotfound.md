---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 94c7ce231df241778f7c6ec5fe5998eae364750d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755575"
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="f22e1-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="f22e1-102">3508 - TrackingProfileNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="f22e1-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="f22e1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f22e1-104">ID</span><span class="sxs-lookup"><span data-stu-id="f22e1-104">ID</span></span>|<span data-ttu-id="f22e1-105">3508</span><span class="sxs-lookup"><span data-stu-id="f22e1-105">3508</span></span>|  
|<span data-ttu-id="f22e1-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="f22e1-106">Keywords</span></span>|<span data-ttu-id="f22e1-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="f22e1-107">WFServices</span></span>|  
|<span data-ttu-id="f22e1-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="f22e1-108">Level</span></span>|<span data-ttu-id="f22e1-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="f22e1-109">Verbose</span></span>|  
|<span data-ttu-id="f22e1-110">Канал</span><span class="sxs-lookup"><span data-stu-id="f22e1-110">Channel</span></span>|<span data-ttu-id="f22e1-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f22e1-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f22e1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f22e1-112">Description</span></span>  
 <span data-ttu-id="f22e1-113">Указывает, что либо профиль TrackingProfile не найден в файле конфигурации, либо обнаружено несоответствие ActivityDefinitionId профилю.</span><span class="sxs-lookup"><span data-stu-id="f22e1-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f22e1-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f22e1-114">Message</span></span>  
 <span data-ttu-id="f22e1-115">Не найден TrackingProfile «%1» для ActivityDefinitionId «%2».</span><span class="sxs-lookup"><span data-stu-id="f22e1-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="f22e1-116">Профиль TrackingProfile не найден в файле конфигурации, или обнаружено несоответствие ActivityDefinitionId.</span><span class="sxs-lookup"><span data-stu-id="f22e1-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f22e1-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="f22e1-117">Details</span></span>  
  
|<span data-ttu-id="f22e1-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="f22e1-118">Data Item Name</span></span>|<span data-ttu-id="f22e1-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="f22e1-119">Data Item Type</span></span>|<span data-ttu-id="f22e1-120">Описание</span><span class="sxs-lookup"><span data-stu-id="f22e1-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f22e1-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="f22e1-121">TrackingProfile</span></span>|<span data-ttu-id="f22e1-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f22e1-122">xs:string</span></span>|<span data-ttu-id="f22e1-123">Имя профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f22e1-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="f22e1-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="f22e1-124">ActivityDefinitionId</span></span>|<span data-ttu-id="f22e1-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f22e1-125">xs:string</span></span>|<span data-ttu-id="f22e1-126">Идентификатор определения действия.</span><span class="sxs-lookup"><span data-stu-id="f22e1-126">The activity definition id.</span></span>|  
|<span data-ttu-id="f22e1-127">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="f22e1-127">AppDomain</span></span>|<span data-ttu-id="f22e1-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="f22e1-128">xs:string</span></span>|<span data-ttu-id="f22e1-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f22e1-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
