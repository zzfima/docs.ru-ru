---
title: 1036 - RuntimeTransactionCompletionRequested
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4f497d777221a98b38603b2ced29342651b1020b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="36275-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="36275-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="36275-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="36275-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="36275-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="36275-104">ID</span></span>|<span data-ttu-id="36275-105">1036</span><span class="sxs-lookup"><span data-stu-id="36275-105">1036</span></span>|  
|<span data-ttu-id="36275-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36275-106">Keywords</span></span>|<span data-ttu-id="36275-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="36275-107">WFRuntime</span></span>|  
|<span data-ttu-id="36275-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="36275-108">Level</span></span>|<span data-ttu-id="36275-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="36275-109">Verbose</span></span>|  
|<span data-ttu-id="36275-110">Канал</span><span class="sxs-lookup"><span data-stu-id="36275-110">Channel</span></span>|<span data-ttu-id="36275-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="36275-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="36275-112">Описание</span><span class="sxs-lookup"><span data-stu-id="36275-112">Description</span></span>  
 <span data-ttu-id="36275-113">Указывает, что действие запланировало завершение транзакции среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="36275-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="36275-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="36275-114">Message</span></span>  
 <span data-ttu-id="36275-115">Действие «%1», DisplayName «%2», InstanceId «%3» запланировало завершение транзакции времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="36275-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="36275-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="36275-116">Details</span></span>  
  
|<span data-ttu-id="36275-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="36275-117">Data Item Name</span></span>|<span data-ttu-id="36275-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="36275-118">Data Item Type</span></span>|<span data-ttu-id="36275-119">Описание</span><span class="sxs-lookup"><span data-stu-id="36275-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="36275-120">Действие</span><span class="sxs-lookup"><span data-stu-id="36275-120">Activity</span></span>|<span data-ttu-id="36275-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="36275-121">xs:string</span></span>|<span data-ttu-id="36275-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="36275-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="36275-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="36275-123">DisplayName</span></span>|<span data-ttu-id="36275-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="36275-124">xs:string</span></span>|<span data-ttu-id="36275-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="36275-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="36275-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="36275-126">InstanceId</span></span>|<span data-ttu-id="36275-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="36275-127">xs:string</span></span>|<span data-ttu-id="36275-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="36275-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="36275-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="36275-129">AppDomain</span></span>|<span data-ttu-id="36275-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="36275-130">xs:string</span></span>|<span data-ttu-id="36275-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="36275-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
