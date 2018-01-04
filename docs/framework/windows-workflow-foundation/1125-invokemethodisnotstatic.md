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
ms.workload: dotnet
ms.openlocfilehash: c8b5e255e9a753c6476a070609b0cbda189d37a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="1620a-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="1620a-102">1125 - InvokeMethodIsNotStatic</span></span>
## <a name="properties"></a><span data-ttu-id="1620a-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="1620a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1620a-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="1620a-104">ID</span></span>|<span data-ttu-id="1620a-105">1125</span><span class="sxs-lookup"><span data-stu-id="1620a-105">1125</span></span>|  
|<span data-ttu-id="1620a-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1620a-106">Keywords</span></span>|<span data-ttu-id="1620a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1620a-107">WFRuntime</span></span>|  
|<span data-ttu-id="1620a-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="1620a-108">Level</span></span>|<span data-ttu-id="1620a-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="1620a-109">Information</span></span>|  
|<span data-ttu-id="1620a-110">Канал</span><span class="sxs-lookup"><span data-stu-id="1620a-110">Channel</span></span>|<span data-ttu-id="1620a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="1620a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1620a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="1620a-112">Description</span></span>  
 <span data-ttu-id="1620a-113">На шаге CacheMetadata действие InvokeMethod означает, что вызываемый метод - не статический.</span><span class="sxs-lookup"><span data-stu-id="1620a-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1620a-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="1620a-114">Message</span></span>  
 <span data-ttu-id="1620a-115">Метод InvokeMethod «%1»: метод не является статическим.</span><span class="sxs-lookup"><span data-stu-id="1620a-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1620a-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="1620a-116">Details</span></span>  
  
|<span data-ttu-id="1620a-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="1620a-117">Data Item Name</span></span>|<span data-ttu-id="1620a-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="1620a-118">Data Item Type</span></span>|<span data-ttu-id="1620a-119">Описание</span><span class="sxs-lookup"><span data-stu-id="1620a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1620a-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="1620a-120">InvokeMethod</span></span>|<span data-ttu-id="1620a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="1620a-121">xs:string</span></span>|<span data-ttu-id="1620a-122">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="1620a-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="1620a-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1620a-123">AppDomain</span></span>|<span data-ttu-id="1620a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="1620a-124">xs:string</span></span>|<span data-ttu-id="1620a-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1620a-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
