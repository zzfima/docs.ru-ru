---
title: 1028 - CompleteTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8770c0d41537ec1ce48dd0038aecc220f0e6ab32
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="d1599-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="d1599-102">1028 - CompleteTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="d1599-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="d1599-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d1599-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="d1599-104">ID</span></span>|<span data-ttu-id="d1599-105">1028</span><span class="sxs-lookup"><span data-stu-id="d1599-105">1028</span></span>|  
|<span data-ttu-id="d1599-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="d1599-106">Keywords</span></span>|<span data-ttu-id="d1599-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d1599-107">WFRuntime</span></span>|  
|<span data-ttu-id="d1599-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="d1599-108">Level</span></span>|<span data-ttu-id="d1599-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="d1599-109">Verbose</span></span>|  
|<span data-ttu-id="d1599-110">Канал</span><span class="sxs-lookup"><span data-stu-id="d1599-110">Channel</span></span>|<span data-ttu-id="d1599-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d1599-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d1599-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d1599-112">Description</span></span>  
 <span data-ttu-id="d1599-113">Указывает на завершение TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="d1599-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d1599-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="d1599-114">Message</span></span>  
 <span data-ttu-id="d1599-115">TransactionContextWorkItem завершен для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="d1599-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d1599-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="d1599-116">Details</span></span>  
  
|<span data-ttu-id="d1599-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="d1599-117">Data Item Name</span></span>|<span data-ttu-id="d1599-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="d1599-118">Data Item Type</span></span>|<span data-ttu-id="d1599-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d1599-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d1599-120">Действие</span><span class="sxs-lookup"><span data-stu-id="d1599-120">Activity</span></span>|<span data-ttu-id="d1599-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d1599-121">xs:string</span></span>|<span data-ttu-id="d1599-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="d1599-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="d1599-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d1599-123">DisplayName</span></span>|<span data-ttu-id="d1599-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d1599-124">xs:string</span></span>|<span data-ttu-id="d1599-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="d1599-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="d1599-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d1599-126">InstanceId</span></span>|<span data-ttu-id="d1599-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d1599-127">xs:string</span></span>|<span data-ttu-id="d1599-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="d1599-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="d1599-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d1599-129">AppDomain</span></span>|<span data-ttu-id="d1599-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="d1599-130">xs:string</span></span>|<span data-ttu-id="d1599-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d1599-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
