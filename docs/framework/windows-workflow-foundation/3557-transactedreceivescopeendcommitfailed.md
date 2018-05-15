---
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.date: 03/30/2017
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
ms.openlocfilehash: 444fa2e51322edd793f709fd3f92c5f9fe826522
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="c96bf-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="c96bf-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="c96bf-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="c96bf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c96bf-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="c96bf-104">ID</span></span>|<span data-ttu-id="c96bf-105">3557</span><span class="sxs-lookup"><span data-stu-id="c96bf-105">3557</span></span>|  
|<span data-ttu-id="c96bf-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="c96bf-106">Keywords</span></span>|<span data-ttu-id="c96bf-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="c96bf-107">WFServices</span></span>|  
|<span data-ttu-id="c96bf-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="c96bf-108">Level</span></span>|<span data-ttu-id="c96bf-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="c96bf-109">Information</span></span>|  
|<span data-ttu-id="c96bf-110">Канал</span><span class="sxs-lookup"><span data-stu-id="c96bf-110">Channel</span></span>|<span data-ttu-id="c96bf-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="c96bf-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c96bf-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c96bf-112">Description</span></span>  
 <span data-ttu-id="c96bf-113">Указывает, что вызов к EndCommit в CommittableTransaction привел к созданию исключения TransactionException.</span><span class="sxs-lookup"><span data-stu-id="c96bf-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c96bf-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="c96bf-114">Message</span></span>  
 <span data-ttu-id="c96bf-115">Вызов EndCommit для CommittableTransaction с id = «%1» привел к созданию исключения TransactionException со следующим сообщением: «%2».</span><span class="sxs-lookup"><span data-stu-id="c96bf-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c96bf-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="c96bf-116">Details</span></span>  
  
|<span data-ttu-id="c96bf-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="c96bf-117">Data Item Name</span></span>|<span data-ttu-id="c96bf-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="c96bf-118">Data Item Type</span></span>|<span data-ttu-id="c96bf-119">Описание</span><span class="sxs-lookup"><span data-stu-id="c96bf-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c96bf-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="c96bf-120">TransactionId</span></span>|<span data-ttu-id="c96bf-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c96bf-121">xs:string</span></span>|<span data-ttu-id="c96bf-122">Идентификатор CommittableTransaction.</span><span class="sxs-lookup"><span data-stu-id="c96bf-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="c96bf-123">Исключение</span><span class="sxs-lookup"><span data-stu-id="c96bf-123">Exception</span></span>|<span data-ttu-id="c96bf-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c96bf-124">xs:string</span></span>|<span data-ttu-id="c96bf-125">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="c96bf-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="c96bf-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c96bf-126">AppDomain</span></span>|<span data-ttu-id="c96bf-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="c96bf-127">xs:string</span></span>|<span data-ttu-id="c96bf-128">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c96bf-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
