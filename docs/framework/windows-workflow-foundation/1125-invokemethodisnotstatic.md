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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 934c2947e86b429e9b990c273f22c0511f209a53
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="2f624-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="2f624-102">1125 - InvokeMethodIsNotStatic</span></span>
## <a name="properties"></a><span data-ttu-id="2f624-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="2f624-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f624-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="2f624-104">ID</span></span>|<span data-ttu-id="2f624-105">1125</span><span class="sxs-lookup"><span data-stu-id="2f624-105">1125</span></span>|  
|<span data-ttu-id="2f624-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2f624-106">Keywords</span></span>|<span data-ttu-id="2f624-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2f624-107">WFRuntime</span></span>|  
|<span data-ttu-id="2f624-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="2f624-108">Level</span></span>|<span data-ttu-id="2f624-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="2f624-109">Information</span></span>|  
|<span data-ttu-id="2f624-110">Канал</span><span class="sxs-lookup"><span data-stu-id="2f624-110">Channel</span></span>|<span data-ttu-id="2f624-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2f624-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2f624-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2f624-112">Description</span></span>  
 <span data-ttu-id="2f624-113">На шаге CacheMetadata действие InvokeMethod означает, что вызываемый метод - не статический.</span><span class="sxs-lookup"><span data-stu-id="2f624-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2f624-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2f624-114">Message</span></span>  
 <span data-ttu-id="2f624-115">Метод InvokeMethod «%1»: метод не является статическим.</span><span class="sxs-lookup"><span data-stu-id="2f624-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2f624-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="2f624-116">Details</span></span>  
  
|<span data-ttu-id="2f624-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="2f624-117">Data Item Name</span></span>|<span data-ttu-id="2f624-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="2f624-118">Data Item Type</span></span>|<span data-ttu-id="2f624-119">Описание</span><span class="sxs-lookup"><span data-stu-id="2f624-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2f624-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="2f624-120">InvokeMethod</span></span>|<span data-ttu-id="2f624-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f624-121">xs:string</span></span>|<span data-ttu-id="2f624-122">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="2f624-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="2f624-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2f624-123">AppDomain</span></span>|<span data-ttu-id="2f624-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f624-124">xs:string</span></span>|<span data-ttu-id="2f624-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2f624-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
