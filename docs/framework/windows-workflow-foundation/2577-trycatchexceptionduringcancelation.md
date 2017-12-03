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
ms.openlocfilehash: 11781bcab37a5034f3bbfadf2c50cbc1c6d378a2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="332be-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="332be-102">2577 - TryCatchExceptionDuringCancelation</span></span>
## <a name="properties"></a><span data-ttu-id="332be-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="332be-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="332be-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="332be-104">ID</span></span>|<span data-ttu-id="332be-105">2577</span><span class="sxs-lookup"><span data-stu-id="332be-105">2577</span></span>|  
|<span data-ttu-id="332be-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="332be-106">Keywords</span></span>|<span data-ttu-id="332be-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="332be-107">WFActivities</span></span>|  
|<span data-ttu-id="332be-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="332be-108">Level</span></span>|<span data-ttu-id="332be-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="332be-109">Warning</span></span>|  
|<span data-ttu-id="332be-110">Канал</span><span class="sxs-lookup"><span data-stu-id="332be-110">Channel</span></span>|<span data-ttu-id="332be-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="332be-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="332be-112">Описание</span><span class="sxs-lookup"><span data-stu-id="332be-112">Description</span></span>  
 <span data-ttu-id="332be-113">Указывает, что дочернее действие для действия TryCatch вызвало исключение во время отмены.</span><span class="sxs-lookup"><span data-stu-id="332be-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="332be-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="332be-114">Message</span></span>  
 <span data-ttu-id="332be-115">При отмене дочернего действия для действия TryCatch «%1» произошло исключение.</span><span class="sxs-lookup"><span data-stu-id="332be-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="332be-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="332be-116">Details</span></span>  
  
|<span data-ttu-id="332be-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="332be-117">Data Item Name</span></span>|<span data-ttu-id="332be-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="332be-118">Data Item Type</span></span>|<span data-ttu-id="332be-119">Описание</span><span class="sxs-lookup"><span data-stu-id="332be-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="332be-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="332be-120">DisplayName</span></span>|<span data-ttu-id="332be-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="332be-121">xs:string</span></span>|<span data-ttu-id="332be-122">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="332be-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="332be-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="332be-123">AppDomain</span></span>|<span data-ttu-id="332be-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="332be-124">xs:string</span></span>|<span data-ttu-id="332be-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="332be-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
