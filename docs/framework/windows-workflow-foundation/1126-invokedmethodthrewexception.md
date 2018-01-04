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
ms.workload: dotnet
ms.openlocfilehash: 5dc752a5c9d5bebe39a4d4be2c3642333aa041de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="39bfd-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="39bfd-102">1126 - InvokedMethodThrewException</span></span>
## <a name="properties"></a><span data-ttu-id="39bfd-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="39bfd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39bfd-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="39bfd-104">ID</span></span>|<span data-ttu-id="39bfd-105">1126</span><span class="sxs-lookup"><span data-stu-id="39bfd-105">1126</span></span>|  
|<span data-ttu-id="39bfd-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="39bfd-106">Keywords</span></span>|<span data-ttu-id="39bfd-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="39bfd-107">WFRuntime</span></span>|  
|<span data-ttu-id="39bfd-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="39bfd-108">Level</span></span>|<span data-ttu-id="39bfd-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="39bfd-109">Information</span></span>|  
|<span data-ttu-id="39bfd-110">Канал</span><span class="sxs-lookup"><span data-stu-id="39bfd-110">Channel</span></span>|<span data-ttu-id="39bfd-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="39bfd-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="39bfd-112">Описание</span><span class="sxs-lookup"><span data-stu-id="39bfd-112">Description</span></span>  
 <span data-ttu-id="39bfd-113">Означает, что метод, вызванный действием InvokeMethod, привел к созданию исключения.</span><span class="sxs-lookup"><span data-stu-id="39bfd-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="39bfd-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="39bfd-114">Message</span></span>  
 <span data-ttu-id="39bfd-115">Возникло исключение в методе, вызванном операцией «%1».</span><span class="sxs-lookup"><span data-stu-id="39bfd-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="39bfd-116">%2</span><span class="sxs-lookup"><span data-stu-id="39bfd-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="39bfd-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="39bfd-117">Details</span></span>  
  
|<span data-ttu-id="39bfd-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="39bfd-118">Data Item Name</span></span>|<span data-ttu-id="39bfd-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="39bfd-119">Data Item Type</span></span>|<span data-ttu-id="39bfd-120">Описание</span><span class="sxs-lookup"><span data-stu-id="39bfd-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="39bfd-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="39bfd-121">InvokeMethod</span></span>|<span data-ttu-id="39bfd-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="39bfd-122">xs:string</span></span>|<span data-ttu-id="39bfd-123">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="39bfd-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="39bfd-124">Исключение</span><span class="sxs-lookup"><span data-stu-id="39bfd-124">Exception</span></span>|<span data-ttu-id="39bfd-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="39bfd-125">xs:string</span></span>|<span data-ttu-id="39bfd-126">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="39bfd-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="39bfd-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="39bfd-127">AppDomain</span></span>|<span data-ttu-id="39bfd-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="39bfd-128">xs:string</span></span>|<span data-ttu-id="39bfd-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="39bfd-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
