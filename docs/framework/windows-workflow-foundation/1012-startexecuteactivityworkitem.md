---
title: 1012 - StartExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bc60af91088fd61910dc0301b93844f4771177af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="fc1d8-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="fc1d8-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="fc1d8-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="fc1d8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fc1d8-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="fc1d8-104">ID</span></span>|<span data-ttu-id="fc1d8-105">1012</span><span class="sxs-lookup"><span data-stu-id="fc1d8-105">1012</span></span>|  
|<span data-ttu-id="fc1d8-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="fc1d8-106">Keywords</span></span>|<span data-ttu-id="fc1d8-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fc1d8-107">WFRuntime</span></span>|  
|<span data-ttu-id="fc1d8-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="fc1d8-108">Level</span></span>|<span data-ttu-id="fc1d8-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="fc1d8-109">Verbose</span></span>|  
|<span data-ttu-id="fc1d8-110">Канал</span><span class="sxs-lookup"><span data-stu-id="fc1d8-110">Channel</span></span>|<span data-ttu-id="fc1d8-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fc1d8-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fc1d8-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fc1d8-112">Description</span></span>  
 <span data-ttu-id="fc1d8-113">Указывает на начало выполнения элемента ExecuteActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="fc1d8-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fc1d8-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="fc1d8-114">Message</span></span>  
 <span data-ttu-id="fc1d8-115">Начато выполнение ExecuteActivityWorkItem для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="fc1d8-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fc1d8-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="fc1d8-116">Details</span></span>  
  
|<span data-ttu-id="fc1d8-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="fc1d8-117">Data Item Name</span></span>|<span data-ttu-id="fc1d8-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="fc1d8-118">Data Item Type</span></span>|<span data-ttu-id="fc1d8-119">Описание</span><span class="sxs-lookup"><span data-stu-id="fc1d8-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fc1d8-120">Действие</span><span class="sxs-lookup"><span data-stu-id="fc1d8-120">Activity</span></span>|<span data-ttu-id="fc1d8-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="fc1d8-121">xs:string</span></span>|<span data-ttu-id="fc1d8-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="fc1d8-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="fc1d8-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="fc1d8-123">DisplayName</span></span>|<span data-ttu-id="fc1d8-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="fc1d8-124">xs:string</span></span>|<span data-ttu-id="fc1d8-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="fc1d8-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="fc1d8-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="fc1d8-126">InstanceId</span></span>|<span data-ttu-id="fc1d8-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="fc1d8-127">xs:string</span></span>|<span data-ttu-id="fc1d8-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="fc1d8-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="fc1d8-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fc1d8-129">AppDomain</span></span>|<span data-ttu-id="fc1d8-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="fc1d8-130">xs:string</span></span>|<span data-ttu-id="fc1d8-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fc1d8-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
