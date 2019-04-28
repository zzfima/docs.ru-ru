---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 198e11dd94b0ad5cdc1e01c3611280754ca081d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924856"
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="d0e97-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="d0e97-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="d0e97-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="d0e97-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d0e97-104">ID</span><span class="sxs-lookup"><span data-stu-id="d0e97-104">ID</span></span>|<span data-ttu-id="d0e97-105">1035</span><span class="sxs-lookup"><span data-stu-id="d0e97-105">1035</span></span>|  
|<span data-ttu-id="d0e97-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="d0e97-106">Keywords</span></span>|<span data-ttu-id="d0e97-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d0e97-107">WFRuntime</span></span>|  
|<span data-ttu-id="d0e97-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="d0e97-108">Level</span></span>|<span data-ttu-id="d0e97-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="d0e97-109">Verbose</span></span>|  
|<span data-ttu-id="d0e97-110">Канал</span><span class="sxs-lookup"><span data-stu-id="d0e97-110">Channel</span></span>|<span data-ttu-id="d0e97-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d0e97-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d0e97-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d0e97-112">Description</span></span>  
 <span data-ttu-id="d0e97-113">Указывает, что действие задало транзакцию среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="d0e97-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d0e97-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="d0e97-114">Message</span></span>  
 <span data-ttu-id="d0e97-115">Транзакция среды выполнения установлено с помощью действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="d0e97-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="d0e97-116">Выполнение изолированного действия «%4», DisplayName: «%5», InstanceId: «%6».</span><span class="sxs-lookup"><span data-stu-id="d0e97-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d0e97-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="d0e97-117">Details</span></span>  
  
|<span data-ttu-id="d0e97-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="d0e97-118">Data Item Name</span></span>|<span data-ttu-id="d0e97-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="d0e97-119">Data Item Type</span></span>|<span data-ttu-id="d0e97-120">Описание</span><span class="sxs-lookup"><span data-stu-id="d0e97-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d0e97-121">Действие</span><span class="sxs-lookup"><span data-stu-id="d0e97-121">Activity</span></span>|<span data-ttu-id="d0e97-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="d0e97-122">xs:string</span></span>|<span data-ttu-id="d0e97-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="d0e97-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="d0e97-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d0e97-124">DisplayName</span></span>|<span data-ttu-id="d0e97-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="d0e97-125">xs:string</span></span>|<span data-ttu-id="d0e97-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="d0e97-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="d0e97-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d0e97-127">InstanceId</span></span>|<span data-ttu-id="d0e97-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="d0e97-128">xs:string</span></span>|<span data-ttu-id="d0e97-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="d0e97-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="d0e97-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="d0e97-130">IsolatedActivity</span></span>|<span data-ttu-id="d0e97-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="d0e97-131">xs:string</span></span>|<span data-ttu-id="d0e97-132">Имя типа для действия, в котором изолирована транзакция.</span><span class="sxs-lookup"><span data-stu-id="d0e97-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="d0e97-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="d0e97-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="d0e97-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="d0e97-134">xs:string</span></span>|<span data-ttu-id="d0e97-135">Имя отображаемого имени действия, в котором изолирована транзакция.</span><span class="sxs-lookup"><span data-stu-id="d0e97-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="d0e97-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="d0e97-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="d0e97-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="d0e97-137">xs:string</span></span>|<span data-ttu-id="d0e97-138">Идентификатор экземпляра действия, в котором изолирована транзакция.</span><span class="sxs-lookup"><span data-stu-id="d0e97-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="d0e97-139">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="d0e97-139">AppDomain</span></span>|<span data-ttu-id="d0e97-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="d0e97-140">xs:string</span></span>|<span data-ttu-id="d0e97-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d0e97-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
