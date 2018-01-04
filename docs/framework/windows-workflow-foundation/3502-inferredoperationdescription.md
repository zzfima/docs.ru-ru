---
title: 3502 - InferredOperationDescription
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e2c2464cd8c6f0c16946847a5503270453d5b019
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="17295-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="17295-102">3502 - InferredOperationDescription</span></span>
## <a name="properties"></a><span data-ttu-id="17295-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="17295-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="17295-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="17295-104">ID</span></span>|<span data-ttu-id="17295-105">3502</span><span class="sxs-lookup"><span data-stu-id="17295-105">3502</span></span>|  
|<span data-ttu-id="17295-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="17295-106">Keywords</span></span>|<span data-ttu-id="17295-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="17295-107">WFServices</span></span>|  
|<span data-ttu-id="17295-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="17295-108">Level</span></span>|<span data-ttu-id="17295-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="17295-109">Information</span></span>|  
|<span data-ttu-id="17295-110">Канал</span><span class="sxs-lookup"><span data-stu-id="17295-110">Channel</span></span>|<span data-ttu-id="17295-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="17295-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="17295-112">Описание</span><span class="sxs-lookup"><span data-stu-id="17295-112">Description</span></span>  
 <span data-ttu-id="17295-113">Указывает, что описание операции OperationDescription выведено из WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="17295-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="17295-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="17295-114">Message</span></span>  
 <span data-ttu-id="17295-115">Описание OperationDescription с параметром Name=«%1» в контракте «%2» было выведено из WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="17295-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="17295-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="17295-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="17295-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="17295-117">Details</span></span>  
  
|<span data-ttu-id="17295-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="17295-118">Data Item Name</span></span>|<span data-ttu-id="17295-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="17295-119">Data Item Type</span></span>|<span data-ttu-id="17295-120">Описание</span><span class="sxs-lookup"><span data-stu-id="17295-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="17295-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="17295-121">OperationName</span></span>|<span data-ttu-id="17295-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="17295-122">xs:string</span></span>|<span data-ttu-id="17295-123">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="17295-123">The name of the operation.</span></span>|  
|<span data-ttu-id="17295-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="17295-124">ContractName</span></span>|<span data-ttu-id="17295-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="17295-125">xs:string</span></span>|<span data-ttu-id="17295-126">Имя контракта.</span><span class="sxs-lookup"><span data-stu-id="17295-126">The name of the contract.</span></span>|  
|<span data-ttu-id="17295-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="17295-127">IsOneWay</span></span>|<span data-ttu-id="17295-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="17295-128">xs:string</span></span>|<span data-ttu-id="17295-129">Логическое значение True или False, указывающее, является ли контракт односторонним.</span><span class="sxs-lookup"><span data-stu-id="17295-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="17295-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="17295-130">AppDomain</span></span>|<span data-ttu-id="17295-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="17295-131">xs:string</span></span>|<span data-ttu-id="17295-132">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="17295-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
