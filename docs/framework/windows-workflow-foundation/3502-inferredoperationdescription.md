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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 044d67bc2b721451ade04947484899266d288d8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="9cc2d-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="9cc2d-102">3502 - InferredOperationDescription</span></span>
## <a name="properties"></a><span data-ttu-id="9cc2d-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="9cc2d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9cc2d-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="9cc2d-104">ID</span></span>|<span data-ttu-id="9cc2d-105">3502</span><span class="sxs-lookup"><span data-stu-id="9cc2d-105">3502</span></span>|  
|<span data-ttu-id="9cc2d-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="9cc2d-106">Keywords</span></span>|<span data-ttu-id="9cc2d-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="9cc2d-107">WFServices</span></span>|  
|<span data-ttu-id="9cc2d-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="9cc2d-108">Level</span></span>|<span data-ttu-id="9cc2d-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="9cc2d-109">Information</span></span>|  
|<span data-ttu-id="9cc2d-110">Канал</span><span class="sxs-lookup"><span data-stu-id="9cc2d-110">Channel</span></span>|<span data-ttu-id="9cc2d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9cc2d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9cc2d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9cc2d-112">Description</span></span>  
 <span data-ttu-id="9cc2d-113">Указывает, что описание операции OperationDescription выведено из WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="9cc2d-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9cc2d-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="9cc2d-114">Message</span></span>  
 <span data-ttu-id="9cc2d-115">Описание OperationDescription с параметром Name=«%1» в контракте «%2» было выведено из WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="9cc2d-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="9cc2d-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="9cc2d-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9cc2d-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="9cc2d-117">Details</span></span>  
  
|<span data-ttu-id="9cc2d-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="9cc2d-118">Data Item Name</span></span>|<span data-ttu-id="9cc2d-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="9cc2d-119">Data Item Type</span></span>|<span data-ttu-id="9cc2d-120">Описание</span><span class="sxs-lookup"><span data-stu-id="9cc2d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9cc2d-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="9cc2d-121">OperationName</span></span>|<span data-ttu-id="9cc2d-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="9cc2d-122">xs:string</span></span>|<span data-ttu-id="9cc2d-123">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="9cc2d-123">The name of the operation.</span></span>|  
|<span data-ttu-id="9cc2d-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="9cc2d-124">ContractName</span></span>|<span data-ttu-id="9cc2d-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="9cc2d-125">xs:string</span></span>|<span data-ttu-id="9cc2d-126">Имя контракта.</span><span class="sxs-lookup"><span data-stu-id="9cc2d-126">The name of the contract.</span></span>|  
|<span data-ttu-id="9cc2d-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="9cc2d-127">IsOneWay</span></span>|<span data-ttu-id="9cc2d-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="9cc2d-128">xs:string</span></span>|<span data-ttu-id="9cc2d-129">Логическое значение True или False, указывающее, является ли контракт односторонним.</span><span class="sxs-lookup"><span data-stu-id="9cc2d-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="9cc2d-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9cc2d-130">AppDomain</span></span>|<span data-ttu-id="9cc2d-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="9cc2d-131">xs:string</span></span>|<span data-ttu-id="9cc2d-132">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9cc2d-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
