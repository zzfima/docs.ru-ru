---
title: 2578 - TryCatchExceptionFromCatchOrFinally
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4803fee6-b8d8-4937-9907-d5c5fd5299db
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 22a798dabd2253d340d7fb3dffb9f95fc66d0a9a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="2578---trycatchexceptionfromcatchorfinally"></a><span data-ttu-id="cb42f-102">2578 - TryCatchExceptionFromCatchOrFinally</span><span class="sxs-lookup"><span data-stu-id="cb42f-102">2578 - TryCatchExceptionFromCatchOrFinally</span></span>
## <a name="properties"></a><span data-ttu-id="cb42f-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="cb42f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cb42f-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="cb42f-104">ID</span></span>|<span data-ttu-id="cb42f-105">2578</span><span class="sxs-lookup"><span data-stu-id="cb42f-105">2578</span></span>|  
|<span data-ttu-id="cb42f-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="cb42f-106">Keywords</span></span>|<span data-ttu-id="cb42f-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="cb42f-107">WFActivities</span></span>|  
|<span data-ttu-id="cb42f-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="cb42f-108">Level</span></span>|<span data-ttu-id="cb42f-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="cb42f-109">Warning</span></span>|  
|<span data-ttu-id="cb42f-110">Канал</span><span class="sxs-lookup"><span data-stu-id="cb42f-110">Channel</span></span>|<span data-ttu-id="cb42f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="cb42f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cb42f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="cb42f-112">Description</span></span>  
 <span data-ttu-id="cb42f-113">Указывает, что действие Catch или Finally вызвало исключение.</span><span class="sxs-lookup"><span data-stu-id="cb42f-113">Indicates a Catch or Finally activity has thrown an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cb42f-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="cb42f-114">Message</span></span>  
 <span data-ttu-id="cb42f-115">В действии Catch или Finally, связанном с действием TryCatch «%1», произошло исключение.</span><span class="sxs-lookup"><span data-stu-id="cb42f-115">A Catch or Finally activity that is associated with the TryCatch activity '%1' has thrown an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cb42f-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="cb42f-116">Details</span></span>  
  
|<span data-ttu-id="cb42f-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="cb42f-117">Data Item Name</span></span>|<span data-ttu-id="cb42f-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="cb42f-118">Data Item Type</span></span>|<span data-ttu-id="cb42f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="cb42f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cb42f-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="cb42f-120">DisplayName</span></span>|<span data-ttu-id="cb42f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="cb42f-121">xs:string</span></span>|<span data-ttu-id="cb42f-122">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="cb42f-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="cb42f-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cb42f-123">AppDomain</span></span>|<span data-ttu-id="cb42f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="cb42f-124">xs:string</span></span>|<span data-ttu-id="cb42f-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="cb42f-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
