---
title: 3502 - InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 752cd73066c3c15ecbb36c40c417ee84b3fcf184
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="16cca-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="16cca-102">3502 - InferredOperationDescription</span></span>
## <a name="properties"></a><span data-ttu-id="16cca-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="16cca-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="16cca-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="16cca-104">ID</span></span>|<span data-ttu-id="16cca-105">3502</span><span class="sxs-lookup"><span data-stu-id="16cca-105">3502</span></span>|  
|<span data-ttu-id="16cca-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="16cca-106">Keywords</span></span>|<span data-ttu-id="16cca-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="16cca-107">WFServices</span></span>|  
|<span data-ttu-id="16cca-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="16cca-108">Level</span></span>|<span data-ttu-id="16cca-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="16cca-109">Information</span></span>|  
|<span data-ttu-id="16cca-110">Канал</span><span class="sxs-lookup"><span data-stu-id="16cca-110">Channel</span></span>|<span data-ttu-id="16cca-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="16cca-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="16cca-112">Описание</span><span class="sxs-lookup"><span data-stu-id="16cca-112">Description</span></span>  
 <span data-ttu-id="16cca-113">Указывает, что описание операции OperationDescription выведено из WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="16cca-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="16cca-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="16cca-114">Message</span></span>  
 <span data-ttu-id="16cca-115">Описание OperationDescription с параметром Name=«%1» в контракте «%2» было выведено из WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="16cca-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="16cca-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="16cca-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="16cca-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="16cca-117">Details</span></span>  
  
|<span data-ttu-id="16cca-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="16cca-118">Data Item Name</span></span>|<span data-ttu-id="16cca-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="16cca-119">Data Item Type</span></span>|<span data-ttu-id="16cca-120">Описание</span><span class="sxs-lookup"><span data-stu-id="16cca-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="16cca-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="16cca-121">OperationName</span></span>|<span data-ttu-id="16cca-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="16cca-122">xs:string</span></span>|<span data-ttu-id="16cca-123">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="16cca-123">The name of the operation.</span></span>|  
|<span data-ttu-id="16cca-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="16cca-124">ContractName</span></span>|<span data-ttu-id="16cca-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="16cca-125">xs:string</span></span>|<span data-ttu-id="16cca-126">Имя контракта.</span><span class="sxs-lookup"><span data-stu-id="16cca-126">The name of the contract.</span></span>|  
|<span data-ttu-id="16cca-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="16cca-127">IsOneWay</span></span>|<span data-ttu-id="16cca-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="16cca-128">xs:string</span></span>|<span data-ttu-id="16cca-129">Логическое значение True или False, указывающее, является ли контракт односторонним.</span><span class="sxs-lookup"><span data-stu-id="16cca-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="16cca-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="16cca-130">AppDomain</span></span>|<span data-ttu-id="16cca-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="16cca-131">xs:string</span></span>|<span data-ttu-id="16cca-132">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="16cca-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
