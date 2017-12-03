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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a1021d7d23b8e9c25684da567b769c24380a8a0a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="03557-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="03557-102">1126 - InvokedMethodThrewException</span></span>
## <a name="properties"></a><span data-ttu-id="03557-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="03557-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="03557-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="03557-104">ID</span></span>|<span data-ttu-id="03557-105">1126</span><span class="sxs-lookup"><span data-stu-id="03557-105">1126</span></span>|  
|<span data-ttu-id="03557-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="03557-106">Keywords</span></span>|<span data-ttu-id="03557-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="03557-107">WFRuntime</span></span>|  
|<span data-ttu-id="03557-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="03557-108">Level</span></span>|<span data-ttu-id="03557-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="03557-109">Information</span></span>|  
|<span data-ttu-id="03557-110">Канал</span><span class="sxs-lookup"><span data-stu-id="03557-110">Channel</span></span>|<span data-ttu-id="03557-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="03557-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="03557-112">Описание</span><span class="sxs-lookup"><span data-stu-id="03557-112">Description</span></span>  
 <span data-ttu-id="03557-113">Означает, что метод, вызванный действием InvokeMethod, привел к созданию исключения.</span><span class="sxs-lookup"><span data-stu-id="03557-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="03557-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="03557-114">Message</span></span>  
 <span data-ttu-id="03557-115">Возникло исключение в методе, вызванном операцией «%1».</span><span class="sxs-lookup"><span data-stu-id="03557-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="03557-116">%2</span><span class="sxs-lookup"><span data-stu-id="03557-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="03557-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="03557-117">Details</span></span>  
  
|<span data-ttu-id="03557-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="03557-118">Data Item Name</span></span>|<span data-ttu-id="03557-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="03557-119">Data Item Type</span></span>|<span data-ttu-id="03557-120">Описание</span><span class="sxs-lookup"><span data-stu-id="03557-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="03557-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="03557-121">InvokeMethod</span></span>|<span data-ttu-id="03557-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="03557-122">xs:string</span></span>|<span data-ttu-id="03557-123">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="03557-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="03557-124">Исключение</span><span class="sxs-lookup"><span data-stu-id="03557-124">Exception</span></span>|<span data-ttu-id="03557-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="03557-125">xs:string</span></span>|<span data-ttu-id="03557-126">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="03557-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="03557-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="03557-127">AppDomain</span></span>|<span data-ttu-id="03557-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="03557-128">xs:string</span></span>|<span data-ttu-id="03557-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="03557-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
