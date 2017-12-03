---
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ea57cc60f9626763308267a98624c825f8312b0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="c10ec-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="c10ec-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="c10ec-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="c10ec-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c10ec-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="c10ec-104">ID</span></span>|<span data-ttu-id="c10ec-105">3557</span><span class="sxs-lookup"><span data-stu-id="c10ec-105">3557</span></span>|  
|<span data-ttu-id="c10ec-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="c10ec-106">Keywords</span></span>|<span data-ttu-id="c10ec-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="c10ec-107">WFServices</span></span>|  
|<span data-ttu-id="c10ec-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="c10ec-108">Level</span></span>|<span data-ttu-id="c10ec-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="c10ec-109">Information</span></span>|  
|<span data-ttu-id="c10ec-110">Канал</span><span class="sxs-lookup"><span data-stu-id="c10ec-110">Channel</span></span>|<span data-ttu-id="c10ec-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="c10ec-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c10ec-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c10ec-112">Description</span></span>  
 <span data-ttu-id="c10ec-113">Указывает, что вызов к EndCommit в CommittableTransaction привел к созданию исключения TransactionException.</span><span class="sxs-lookup"><span data-stu-id="c10ec-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c10ec-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="c10ec-114">Message</span></span>  
 <span data-ttu-id="c10ec-115">Вызов EndCommit для CommittableTransaction с id = «%1» привел к созданию исключения TransactionException со следующим сообщением: «%2».</span><span class="sxs-lookup"><span data-stu-id="c10ec-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c10ec-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="c10ec-116">Details</span></span>  
  
|<span data-ttu-id="c10ec-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="c10ec-117">Data Item Name</span></span>|<span data-ttu-id="c10ec-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="c10ec-118">Data Item Type</span></span>|<span data-ttu-id="c10ec-119">Описание</span><span class="sxs-lookup"><span data-stu-id="c10ec-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c10ec-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="c10ec-120">TransactionId</span></span>|<span data-ttu-id="c10ec-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c10ec-121">xs:string</span></span>|<span data-ttu-id="c10ec-122">Идентификатор CommittableTransaction.</span><span class="sxs-lookup"><span data-stu-id="c10ec-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="c10ec-123">Исключение</span><span class="sxs-lookup"><span data-stu-id="c10ec-123">Exception</span></span>|<span data-ttu-id="c10ec-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c10ec-124">xs:string</span></span>|<span data-ttu-id="c10ec-125">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="c10ec-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="c10ec-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c10ec-126">AppDomain</span></span>|<span data-ttu-id="c10ec-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="c10ec-127">xs:string</span></span>|<span data-ttu-id="c10ec-128">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c10ec-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
