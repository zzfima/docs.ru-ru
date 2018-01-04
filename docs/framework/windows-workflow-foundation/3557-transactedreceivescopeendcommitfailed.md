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
ms.workload: dotnet
ms.openlocfilehash: 85e9456f6b4c1884b2e28671b304728135b6b1d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="387d4-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="387d4-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="387d4-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="387d4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="387d4-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="387d4-104">ID</span></span>|<span data-ttu-id="387d4-105">3557</span><span class="sxs-lookup"><span data-stu-id="387d4-105">3557</span></span>|  
|<span data-ttu-id="387d4-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="387d4-106">Keywords</span></span>|<span data-ttu-id="387d4-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="387d4-107">WFServices</span></span>|  
|<span data-ttu-id="387d4-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="387d4-108">Level</span></span>|<span data-ttu-id="387d4-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="387d4-109">Information</span></span>|  
|<span data-ttu-id="387d4-110">Канал</span><span class="sxs-lookup"><span data-stu-id="387d4-110">Channel</span></span>|<span data-ttu-id="387d4-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="387d4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="387d4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="387d4-112">Description</span></span>  
 <span data-ttu-id="387d4-113">Указывает, что вызов к EndCommit в CommittableTransaction привел к созданию исключения TransactionException.</span><span class="sxs-lookup"><span data-stu-id="387d4-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="387d4-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="387d4-114">Message</span></span>  
 <span data-ttu-id="387d4-115">Вызов EndCommit для CommittableTransaction с id = «%1» привел к созданию исключения TransactionException со следующим сообщением: «%2».</span><span class="sxs-lookup"><span data-stu-id="387d4-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="387d4-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="387d4-116">Details</span></span>  
  
|<span data-ttu-id="387d4-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="387d4-117">Data Item Name</span></span>|<span data-ttu-id="387d4-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="387d4-118">Data Item Type</span></span>|<span data-ttu-id="387d4-119">Описание</span><span class="sxs-lookup"><span data-stu-id="387d4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="387d4-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="387d4-120">TransactionId</span></span>|<span data-ttu-id="387d4-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="387d4-121">xs:string</span></span>|<span data-ttu-id="387d4-122">Идентификатор CommittableTransaction.</span><span class="sxs-lookup"><span data-stu-id="387d4-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="387d4-123">Исключение</span><span class="sxs-lookup"><span data-stu-id="387d4-123">Exception</span></span>|<span data-ttu-id="387d4-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="387d4-124">xs:string</span></span>|<span data-ttu-id="387d4-125">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="387d4-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="387d4-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="387d4-126">AppDomain</span></span>|<span data-ttu-id="387d4-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="387d4-127">xs:string</span></span>|<span data-ttu-id="387d4-128">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="387d4-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
