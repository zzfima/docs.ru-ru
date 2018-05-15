---
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 150973935d12455aa671043a619fbd6fd7e77425
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="e4a12-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="e4a12-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="e4a12-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="e4a12-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e4a12-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="e4a12-104">ID</span></span>|<span data-ttu-id="e4a12-105">1131</span><span class="sxs-lookup"><span data-stu-id="e4a12-105">1131</span></span>|  
|<span data-ttu-id="e4a12-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e4a12-106">Keywords</span></span>|<span data-ttu-id="e4a12-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e4a12-107">WFRuntime</span></span>|  
|<span data-ttu-id="e4a12-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="e4a12-108">Level</span></span>|<span data-ttu-id="e4a12-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="e4a12-109">Information</span></span>|  
|<span data-ttu-id="e4a12-110">Канал</span><span class="sxs-lookup"><span data-stu-id="e4a12-110">Channel</span></span>|<span data-ttu-id="e4a12-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e4a12-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e4a12-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e4a12-112">Description</span></span>  
 <span data-ttu-id="e4a12-113">На шаге CacheMetadata действие InvokeMethod указывает на использование асинхронного шаблона при вызове метода.</span><span class="sxs-lookup"><span data-stu-id="e4a12-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e4a12-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="e4a12-114">Message</span></span>  
 <span data-ttu-id="e4a12-115">Метод InvokeMethod «%1»: в методе используется асинхронная модель «%2» и «%3».</span><span class="sxs-lookup"><span data-stu-id="e4a12-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e4a12-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="e4a12-116">Details</span></span>  
  
|<span data-ttu-id="e4a12-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="e4a12-117">Data Item Name</span></span>|<span data-ttu-id="e4a12-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="e4a12-118">Data Item Type</span></span>|<span data-ttu-id="e4a12-119">Описание</span><span class="sxs-lookup"><span data-stu-id="e4a12-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e4a12-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="e4a12-120">InvokeMethod</span></span>|<span data-ttu-id="e4a12-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e4a12-121">xs:string</span></span>|<span data-ttu-id="e4a12-122">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="e4a12-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="e4a12-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="e4a12-123">BeginMethod</span></span>|<span data-ttu-id="e4a12-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e4a12-124">xs:string</span></span>|<span data-ttu-id="e4a12-125">Имя метода Begin.</span><span class="sxs-lookup"><span data-stu-id="e4a12-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="e4a12-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="e4a12-126">EndMethod</span></span>|<span data-ttu-id="e4a12-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="e4a12-127">xs:string</span></span>|<span data-ttu-id="e4a12-128">Имя метода End.</span><span class="sxs-lookup"><span data-stu-id="e4a12-128">The name of the end method.</span></span>|  
|<span data-ttu-id="e4a12-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e4a12-129">AppDomain</span></span>|<span data-ttu-id="e4a12-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="e4a12-130">xs:string</span></span>|<span data-ttu-id="e4a12-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e4a12-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
