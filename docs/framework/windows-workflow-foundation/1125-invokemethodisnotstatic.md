---
title: 1125 - InvokeMethodIsNotStatic
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b31bb8db8252474d20f7523e08cadf35bfcc84a8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="b1be7-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="b1be7-102">1125 - InvokeMethodIsNotStatic</span></span>
## <a name="properties"></a><span data-ttu-id="b1be7-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="b1be7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b1be7-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="b1be7-104">ID</span></span>|<span data-ttu-id="b1be7-105">1125</span><span class="sxs-lookup"><span data-stu-id="b1be7-105">1125</span></span>|  
|<span data-ttu-id="b1be7-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="b1be7-106">Keywords</span></span>|<span data-ttu-id="b1be7-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b1be7-107">WFRuntime</span></span>|  
|<span data-ttu-id="b1be7-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="b1be7-108">Level</span></span>|<span data-ttu-id="b1be7-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="b1be7-109">Information</span></span>|  
|<span data-ttu-id="b1be7-110">Канал</span><span class="sxs-lookup"><span data-stu-id="b1be7-110">Channel</span></span>|<span data-ttu-id="b1be7-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b1be7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b1be7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b1be7-112">Description</span></span>  
 <span data-ttu-id="b1be7-113">На шаге CacheMetadata действие InvokeMethod означает, что вызываемый метод - не статический.</span><span class="sxs-lookup"><span data-stu-id="b1be7-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b1be7-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="b1be7-114">Message</span></span>  
 <span data-ttu-id="b1be7-115">Метод InvokeMethod «%1»: метод не является статическим.</span><span class="sxs-lookup"><span data-stu-id="b1be7-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b1be7-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="b1be7-116">Details</span></span>  
  
|<span data-ttu-id="b1be7-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="b1be7-117">Data Item Name</span></span>|<span data-ttu-id="b1be7-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="b1be7-118">Data Item Type</span></span>|<span data-ttu-id="b1be7-119">Описание</span><span class="sxs-lookup"><span data-stu-id="b1be7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b1be7-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="b1be7-120">InvokeMethod</span></span>|<span data-ttu-id="b1be7-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b1be7-121">xs:string</span></span>|<span data-ttu-id="b1be7-122">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="b1be7-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="b1be7-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b1be7-123">AppDomain</span></span>|<span data-ttu-id="b1be7-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b1be7-124">xs:string</span></span>|<span data-ttu-id="b1be7-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b1be7-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
