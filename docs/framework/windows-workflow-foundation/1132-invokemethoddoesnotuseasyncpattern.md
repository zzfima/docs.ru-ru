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
ms.openlocfilehash: 321d8c6185c8d24b7a3b6e255e235c36c119ff21
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="6bc4f-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="6bc4f-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="6bc4f-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="6bc4f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6bc4f-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="6bc4f-104">ID</span></span>|<span data-ttu-id="6bc4f-105">1132</span><span class="sxs-lookup"><span data-stu-id="6bc4f-105">1132</span></span>|  
|<span data-ttu-id="6bc4f-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6bc4f-106">Keywords</span></span>|<span data-ttu-id="6bc4f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6bc4f-107">WFRuntime</span></span>|  
|<span data-ttu-id="6bc4f-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="6bc4f-108">Level</span></span>|<span data-ttu-id="6bc4f-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="6bc4f-109">Information</span></span>|  
|<span data-ttu-id="6bc4f-110">Канал</span><span class="sxs-lookup"><span data-stu-id="6bc4f-110">Channel</span></span>|<span data-ttu-id="6bc4f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6bc4f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6bc4f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6bc4f-112">Description</span></span>  
 <span data-ttu-id="6bc4f-113">На шаге CacheMetadata действие InvokeMethod указывает, что при вызове метода не используется асинхронный шаблон.</span><span class="sxs-lookup"><span data-stu-id="6bc4f-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6bc4f-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="6bc4f-114">Message</span></span>  
 <span data-ttu-id="6bc4f-115">Метод InvokeMethod «%1»: в методе не используется асинхронная модель.</span><span class="sxs-lookup"><span data-stu-id="6bc4f-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6bc4f-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="6bc4f-116">Details</span></span>  
  
|<span data-ttu-id="6bc4f-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="6bc4f-117">Data Item Name</span></span>|<span data-ttu-id="6bc4f-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="6bc4f-118">Data Item Type</span></span>|<span data-ttu-id="6bc4f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="6bc4f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6bc4f-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="6bc4f-120">InvokeMethod</span></span>|<span data-ttu-id="6bc4f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="6bc4f-121">xs:string</span></span>|<span data-ttu-id="6bc4f-122">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="6bc4f-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="6bc4f-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6bc4f-123">AppDomain</span></span>|<span data-ttu-id="6bc4f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="6bc4f-124">xs:string</span></span>|<span data-ttu-id="6bc4f-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6bc4f-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
