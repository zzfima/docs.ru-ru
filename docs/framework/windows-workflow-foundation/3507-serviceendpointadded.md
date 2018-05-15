---
title: 3507 - ServiceEndpointAdded
ms.date: 03/30/2017
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
ms.openlocfilehash: c787a1a5af752a3d08e2049cfa0b600b7739e56c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="3507---serviceendpointadded"></a><span data-ttu-id="f10b9-102">3507 - ServiceEndpointAdded</span><span class="sxs-lookup"><span data-stu-id="f10b9-102">3507 - ServiceEndpointAdded</span></span>
## <a name="properties"></a><span data-ttu-id="f10b9-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="f10b9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f10b9-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="f10b9-104">ID</span></span>|<span data-ttu-id="f10b9-105">3507</span><span class="sxs-lookup"><span data-stu-id="f10b9-105">3507</span></span>|  
|<span data-ttu-id="f10b9-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="f10b9-106">Keywords</span></span>|<span data-ttu-id="f10b9-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="f10b9-107">WFServices</span></span>|  
|<span data-ttu-id="f10b9-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="f10b9-108">Level</span></span>|<span data-ttu-id="f10b9-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="f10b9-109">Information</span></span>|  
|<span data-ttu-id="f10b9-110">Канал</span><span class="sxs-lookup"><span data-stu-id="f10b9-110">Channel</span></span>|<span data-ttu-id="f10b9-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f10b9-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f10b9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f10b9-112">Description</span></span>  
 <span data-ttu-id="f10b9-113">Указывает, что конечная точка службы была добавлена.</span><span class="sxs-lookup"><span data-stu-id="f10b9-113">Indicates a service endpoint has been added.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f10b9-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f10b9-114">Message</span></span>  
 <span data-ttu-id="f10b9-115">Конечная точка службы была добавлена для адреса «%1», привязки «%2» и контракта «%3».</span><span class="sxs-lookup"><span data-stu-id="f10b9-115">A service endpoint has been added for address '%1', binding '%2', and contract '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f10b9-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="f10b9-116">Details</span></span>  
  
|<span data-ttu-id="f10b9-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="f10b9-117">Data Item Name</span></span>|<span data-ttu-id="f10b9-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="f10b9-118">Data Item Type</span></span>|<span data-ttu-id="f10b9-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f10b9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f10b9-120">Адрес</span><span class="sxs-lookup"><span data-stu-id="f10b9-120">Address</span></span>|<span data-ttu-id="f10b9-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f10b9-121">xs:string</span></span>|<span data-ttu-id="f10b9-122">Адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f10b9-122">The address of the endpoint.</span></span>|  
|<span data-ttu-id="f10b9-123">Привязка</span><span class="sxs-lookup"><span data-stu-id="f10b9-123">Binding</span></span>|<span data-ttu-id="f10b9-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f10b9-124">xs:string</span></span>|<span data-ttu-id="f10b9-125">Привязка конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f10b9-125">The binding of the endpoint.</span></span>|  
|<span data-ttu-id="f10b9-126">Контракт</span><span class="sxs-lookup"><span data-stu-id="f10b9-126">Contract</span></span>|<span data-ttu-id="f10b9-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f10b9-127">xs:string</span></span>|<span data-ttu-id="f10b9-128">Контракт конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f10b9-128">The contract of the endpoint.</span></span>|  
|<span data-ttu-id="f10b9-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f10b9-129">AppDomain</span></span>|<span data-ttu-id="f10b9-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="f10b9-130">xs:string</span></span>|<span data-ttu-id="f10b9-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f10b9-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
