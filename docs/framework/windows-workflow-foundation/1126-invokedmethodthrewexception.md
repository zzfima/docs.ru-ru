---
title: 1126 - InvokedMethodThrewException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b11c2f167ce7afce992cddb2f32f840212d4ac8d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="d9ce4-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="d9ce4-102">1126 - InvokedMethodThrewException</span></span>
## <a name="properties"></a><span data-ttu-id="d9ce4-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="d9ce4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d9ce4-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="d9ce4-104">ID</span></span>|<span data-ttu-id="d9ce4-105">1126</span><span class="sxs-lookup"><span data-stu-id="d9ce4-105">1126</span></span>|  
|<span data-ttu-id="d9ce4-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="d9ce4-106">Keywords</span></span>|<span data-ttu-id="d9ce4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d9ce4-107">WFRuntime</span></span>|  
|<span data-ttu-id="d9ce4-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="d9ce4-108">Level</span></span>|<span data-ttu-id="d9ce4-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="d9ce4-109">Information</span></span>|  
|<span data-ttu-id="d9ce4-110">Канал</span><span class="sxs-lookup"><span data-stu-id="d9ce4-110">Channel</span></span>|<span data-ttu-id="d9ce4-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d9ce4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d9ce4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d9ce4-112">Description</span></span>  
 <span data-ttu-id="d9ce4-113">Означает, что метод, вызванный действием InvokeMethod, привел к созданию исключения.</span><span class="sxs-lookup"><span data-stu-id="d9ce4-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d9ce4-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="d9ce4-114">Message</span></span>  
 <span data-ttu-id="d9ce4-115">Возникло исключение в методе, вызванном операцией «%1».</span><span class="sxs-lookup"><span data-stu-id="d9ce4-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="d9ce4-116">%2</span><span class="sxs-lookup"><span data-stu-id="d9ce4-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="d9ce4-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="d9ce4-117">Details</span></span>  
  
|<span data-ttu-id="d9ce4-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="d9ce4-118">Data Item Name</span></span>|<span data-ttu-id="d9ce4-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="d9ce4-119">Data Item Type</span></span>|<span data-ttu-id="d9ce4-120">Описание</span><span class="sxs-lookup"><span data-stu-id="d9ce4-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d9ce4-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="d9ce4-121">InvokeMethod</span></span>|<span data-ttu-id="d9ce4-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="d9ce4-122">xs:string</span></span>|<span data-ttu-id="d9ce4-123">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="d9ce4-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="d9ce4-124">Исключение</span><span class="sxs-lookup"><span data-stu-id="d9ce4-124">Exception</span></span>|<span data-ttu-id="d9ce4-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="d9ce4-125">xs:string</span></span>|<span data-ttu-id="d9ce4-126">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="d9ce4-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="d9ce4-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d9ce4-127">AppDomain</span></span>|<span data-ttu-id="d9ce4-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="d9ce4-128">xs:string</span></span>|<span data-ttu-id="d9ce4-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d9ce4-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
