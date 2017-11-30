---
title: 1131 - InvokeMethodUseAsyncPattern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6f9f8f4e836d5c5b437edcfaff6460c7b97210ce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="23a33-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="23a33-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="23a33-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="23a33-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="23a33-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="23a33-104">ID</span></span>|<span data-ttu-id="23a33-105">1131</span><span class="sxs-lookup"><span data-stu-id="23a33-105">1131</span></span>|  
|<span data-ttu-id="23a33-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="23a33-106">Keywords</span></span>|<span data-ttu-id="23a33-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="23a33-107">WFRuntime</span></span>|  
|<span data-ttu-id="23a33-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="23a33-108">Level</span></span>|<span data-ttu-id="23a33-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="23a33-109">Information</span></span>|  
|<span data-ttu-id="23a33-110">Канал</span><span class="sxs-lookup"><span data-stu-id="23a33-110">Channel</span></span>|<span data-ttu-id="23a33-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="23a33-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="23a33-112">Описание</span><span class="sxs-lookup"><span data-stu-id="23a33-112">Description</span></span>  
 <span data-ttu-id="23a33-113">На шаге CacheMetadata действие InvokeMethod указывает на использование асинхронного шаблона при вызове метода.</span><span class="sxs-lookup"><span data-stu-id="23a33-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="23a33-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="23a33-114">Message</span></span>  
 <span data-ttu-id="23a33-115">Метод InvokeMethod «%1»: в методе используется асинхронная модель «%2» и «%3».</span><span class="sxs-lookup"><span data-stu-id="23a33-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="23a33-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="23a33-116">Details</span></span>  
  
|<span data-ttu-id="23a33-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="23a33-117">Data Item Name</span></span>|<span data-ttu-id="23a33-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="23a33-118">Data Item Type</span></span>|<span data-ttu-id="23a33-119">Описание</span><span class="sxs-lookup"><span data-stu-id="23a33-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="23a33-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="23a33-120">InvokeMethod</span></span>|<span data-ttu-id="23a33-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="23a33-121">xs:string</span></span>|<span data-ttu-id="23a33-122">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="23a33-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="23a33-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="23a33-123">BeginMethod</span></span>|<span data-ttu-id="23a33-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="23a33-124">xs:string</span></span>|<span data-ttu-id="23a33-125">Имя метода Begin.</span><span class="sxs-lookup"><span data-stu-id="23a33-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="23a33-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="23a33-126">EndMethod</span></span>|<span data-ttu-id="23a33-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="23a33-127">xs:string</span></span>|<span data-ttu-id="23a33-128">Имя метода End.</span><span class="sxs-lookup"><span data-stu-id="23a33-128">The name of the end method.</span></span>|  
|<span data-ttu-id="23a33-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="23a33-129">AppDomain</span></span>|<span data-ttu-id="23a33-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="23a33-130">xs:string</span></span>|<span data-ttu-id="23a33-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="23a33-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
