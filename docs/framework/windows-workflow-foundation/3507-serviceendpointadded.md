---
title: 3507 - ServiceEndpointAdded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 463482bbcc659c6dba15b854ff06f41754f63ccc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="3507---serviceendpointadded"></a><span data-ttu-id="3707c-102">3507 - ServiceEndpointAdded</span><span class="sxs-lookup"><span data-stu-id="3707c-102">3507 - ServiceEndpointAdded</span></span>
## <a name="properties"></a><span data-ttu-id="3707c-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="3707c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3707c-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="3707c-104">ID</span></span>|<span data-ttu-id="3707c-105">3507</span><span class="sxs-lookup"><span data-stu-id="3707c-105">3507</span></span>|  
|<span data-ttu-id="3707c-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3707c-106">Keywords</span></span>|<span data-ttu-id="3707c-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="3707c-107">WFServices</span></span>|  
|<span data-ttu-id="3707c-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="3707c-108">Level</span></span>|<span data-ttu-id="3707c-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="3707c-109">Information</span></span>|  
|<span data-ttu-id="3707c-110">Канал</span><span class="sxs-lookup"><span data-stu-id="3707c-110">Channel</span></span>|<span data-ttu-id="3707c-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="3707c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3707c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3707c-112">Description</span></span>  
 <span data-ttu-id="3707c-113">Указывает, что конечная точка службы была добавлена.</span><span class="sxs-lookup"><span data-stu-id="3707c-113">Indicates a service endpoint has been added.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3707c-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="3707c-114">Message</span></span>  
 <span data-ttu-id="3707c-115">Конечная точка службы была добавлена для адреса «%1», привязки «%2» и контракта «%3».</span><span class="sxs-lookup"><span data-stu-id="3707c-115">A service endpoint has been added for address '%1', binding '%2', and contract '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3707c-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="3707c-116">Details</span></span>  
  
|<span data-ttu-id="3707c-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="3707c-117">Data Item Name</span></span>|<span data-ttu-id="3707c-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="3707c-118">Data Item Type</span></span>|<span data-ttu-id="3707c-119">Описание</span><span class="sxs-lookup"><span data-stu-id="3707c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3707c-120">Адрес</span><span class="sxs-lookup"><span data-stu-id="3707c-120">Address</span></span>|<span data-ttu-id="3707c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3707c-121">xs:string</span></span>|<span data-ttu-id="3707c-122">Адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3707c-122">The address of the endpoint.</span></span>|  
|<span data-ttu-id="3707c-123">Привязка</span><span class="sxs-lookup"><span data-stu-id="3707c-123">Binding</span></span>|<span data-ttu-id="3707c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3707c-124">xs:string</span></span>|<span data-ttu-id="3707c-125">Привязка конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3707c-125">The binding of the endpoint.</span></span>|  
|<span data-ttu-id="3707c-126">Контракт</span><span class="sxs-lookup"><span data-stu-id="3707c-126">Contract</span></span>|<span data-ttu-id="3707c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3707c-127">xs:string</span></span>|<span data-ttu-id="3707c-128">Контракт конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3707c-128">The contract of the endpoint.</span></span>|  
|<span data-ttu-id="3707c-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3707c-129">AppDomain</span></span>|<span data-ttu-id="3707c-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3707c-130">xs:string</span></span>|<span data-ttu-id="3707c-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3707c-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
