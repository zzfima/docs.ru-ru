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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 112063d5cd550f438541b2d775eaa49124d9cc02
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="ed1cb-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="ed1cb-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="ed1cb-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="ed1cb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ed1cb-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="ed1cb-104">ID</span></span>|<span data-ttu-id="ed1cb-105">1036</span><span class="sxs-lookup"><span data-stu-id="ed1cb-105">1036</span></span>|  
|<span data-ttu-id="ed1cb-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ed1cb-106">Keywords</span></span>|<span data-ttu-id="ed1cb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ed1cb-107">WFRuntime</span></span>|  
|<span data-ttu-id="ed1cb-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="ed1cb-108">Level</span></span>|<span data-ttu-id="ed1cb-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="ed1cb-109">Verbose</span></span>|  
|<span data-ttu-id="ed1cb-110">Канал</span><span class="sxs-lookup"><span data-stu-id="ed1cb-110">Channel</span></span>|<span data-ttu-id="ed1cb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ed1cb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ed1cb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ed1cb-112">Description</span></span>  
 <span data-ttu-id="ed1cb-113">Указывает, что действие запланировало завершение транзакции среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ed1cb-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ed1cb-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ed1cb-114">Message</span></span>  
 <span data-ttu-id="ed1cb-115">Действие «%1», DisplayName «%2», InstanceId «%3» запланировало завершение транзакции времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="ed1cb-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ed1cb-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ed1cb-116">Details</span></span>  
  
|<span data-ttu-id="ed1cb-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="ed1cb-117">Data Item Name</span></span>|<span data-ttu-id="ed1cb-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="ed1cb-118">Data Item Type</span></span>|<span data-ttu-id="ed1cb-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ed1cb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ed1cb-120">Действие</span><span class="sxs-lookup"><span data-stu-id="ed1cb-120">Activity</span></span>|<span data-ttu-id="ed1cb-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ed1cb-121">xs:string</span></span>|<span data-ttu-id="ed1cb-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="ed1cb-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="ed1cb-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ed1cb-123">DisplayName</span></span>|<span data-ttu-id="ed1cb-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ed1cb-124">xs:string</span></span>|<span data-ttu-id="ed1cb-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="ed1cb-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="ed1cb-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ed1cb-126">InstanceId</span></span>|<span data-ttu-id="ed1cb-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ed1cb-127">xs:string</span></span>|<span data-ttu-id="ed1cb-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="ed1cb-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ed1cb-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ed1cb-129">AppDomain</span></span>|<span data-ttu-id="ed1cb-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="ed1cb-130">xs:string</span></span>|<span data-ttu-id="ed1cb-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ed1cb-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
