---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 75386b56f7926b9ddb883e0ca212d795898fe6f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="d4c4e-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="d4c4e-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="d4c4e-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="d4c4e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d4c4e-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="d4c4e-104">ID</span></span>|<span data-ttu-id="d4c4e-105">1132</span><span class="sxs-lookup"><span data-stu-id="d4c4e-105">1132</span></span>|  
|<span data-ttu-id="d4c4e-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="d4c4e-106">Keywords</span></span>|<span data-ttu-id="d4c4e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d4c4e-107">WFRuntime</span></span>|  
|<span data-ttu-id="d4c4e-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="d4c4e-108">Level</span></span>|<span data-ttu-id="d4c4e-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="d4c4e-109">Information</span></span>|  
|<span data-ttu-id="d4c4e-110">Канал</span><span class="sxs-lookup"><span data-stu-id="d4c4e-110">Channel</span></span>|<span data-ttu-id="d4c4e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d4c4e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d4c4e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d4c4e-112">Description</span></span>  
 <span data-ttu-id="d4c4e-113">На шаге CacheMetadata действие InvokeMethod указывает, что при вызове метода не используется асинхронный шаблон.</span><span class="sxs-lookup"><span data-stu-id="d4c4e-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d4c4e-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="d4c4e-114">Message</span></span>  
 <span data-ttu-id="d4c4e-115">Метод InvokeMethod «%1»: в методе не используется асинхронная модель.</span><span class="sxs-lookup"><span data-stu-id="d4c4e-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d4c4e-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="d4c4e-116">Details</span></span>  
  
|<span data-ttu-id="d4c4e-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="d4c4e-117">Data Item Name</span></span>|<span data-ttu-id="d4c4e-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="d4c4e-118">Data Item Type</span></span>|<span data-ttu-id="d4c4e-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d4c4e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d4c4e-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="d4c4e-120">InvokeMethod</span></span>|<span data-ttu-id="d4c4e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4c4e-121">xs:string</span></span>|<span data-ttu-id="d4c4e-122">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="d4c4e-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="d4c4e-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d4c4e-123">AppDomain</span></span>|<span data-ttu-id="d4c4e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4c4e-124">xs:string</span></span>|<span data-ttu-id="d4c4e-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d4c4e-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
