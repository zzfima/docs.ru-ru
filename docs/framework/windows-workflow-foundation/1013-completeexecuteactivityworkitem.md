---
title: 1013 - CompleteExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8f430e7b58d5aba277b0a35a20f1f5fdb707bce9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="f1b58-102">1013 - CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="f1b58-102">1013 - CompleteExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="f1b58-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="f1b58-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f1b58-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="f1b58-104">ID</span></span>|<span data-ttu-id="f1b58-105">1013</span><span class="sxs-lookup"><span data-stu-id="f1b58-105">1013</span></span>|  
|<span data-ttu-id="f1b58-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="f1b58-106">Keywords</span></span>|<span data-ttu-id="f1b58-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f1b58-107">WFRuntime</span></span>|  
|<span data-ttu-id="f1b58-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="f1b58-108">Level</span></span>|<span data-ttu-id="f1b58-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="f1b58-109">Verbose</span></span>|  
|<span data-ttu-id="f1b58-110">Канал</span><span class="sxs-lookup"><span data-stu-id="f1b58-110">Channel</span></span>|<span data-ttu-id="f1b58-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f1b58-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f1b58-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f1b58-112">Description</span></span>  
 <span data-ttu-id="f1b58-113">Указывает, что ExecuteActivityWorkItem завершено</span><span class="sxs-lookup"><span data-stu-id="f1b58-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="f1b58-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f1b58-114">Message</span></span>  
 <span data-ttu-id="f1b58-115">Завершено выполнение ExecuteActivityWorkItem для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="f1b58-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f1b58-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="f1b58-116">Details</span></span>  
  
|<span data-ttu-id="f1b58-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="f1b58-117">Data Item Name</span></span>|<span data-ttu-id="f1b58-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="f1b58-118">Data Item Type</span></span>|<span data-ttu-id="f1b58-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f1b58-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f1b58-120">Действие</span><span class="sxs-lookup"><span data-stu-id="f1b58-120">Activity</span></span>|<span data-ttu-id="f1b58-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f1b58-121">xs:string</span></span>|<span data-ttu-id="f1b58-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="f1b58-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="f1b58-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f1b58-123">DisplayName</span></span>|<span data-ttu-id="f1b58-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f1b58-124">xs:string</span></span>|<span data-ttu-id="f1b58-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="f1b58-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="f1b58-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f1b58-126">InstanceId</span></span>|<span data-ttu-id="f1b58-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f1b58-127">xs:string</span></span>|<span data-ttu-id="f1b58-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="f1b58-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f1b58-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f1b58-129">AppDomain</span></span>|<span data-ttu-id="f1b58-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="f1b58-130">xs:string</span></span>|<span data-ttu-id="f1b58-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f1b58-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
