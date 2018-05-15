---
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 649ba542a9ed2f330ac71e447602d637530dc601
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="03739-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="03739-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="03739-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="03739-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="03739-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="03739-104">ID</span></span>|<span data-ttu-id="03739-105">1036</span><span class="sxs-lookup"><span data-stu-id="03739-105">1036</span></span>|  
|<span data-ttu-id="03739-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="03739-106">Keywords</span></span>|<span data-ttu-id="03739-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="03739-107">WFRuntime</span></span>|  
|<span data-ttu-id="03739-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="03739-108">Level</span></span>|<span data-ttu-id="03739-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="03739-109">Verbose</span></span>|  
|<span data-ttu-id="03739-110">Канал</span><span class="sxs-lookup"><span data-stu-id="03739-110">Channel</span></span>|<span data-ttu-id="03739-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="03739-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="03739-112">Описание</span><span class="sxs-lookup"><span data-stu-id="03739-112">Description</span></span>  
 <span data-ttu-id="03739-113">Указывает, что действие запланировало завершение транзакции среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="03739-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="03739-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="03739-114">Message</span></span>  
 <span data-ttu-id="03739-115">Действие «%1», DisplayName «%2», InstanceId «%3» запланировало завершение транзакции времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="03739-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="03739-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="03739-116">Details</span></span>  
  
|<span data-ttu-id="03739-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="03739-117">Data Item Name</span></span>|<span data-ttu-id="03739-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="03739-118">Data Item Type</span></span>|<span data-ttu-id="03739-119">Описание</span><span class="sxs-lookup"><span data-stu-id="03739-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="03739-120">Действие</span><span class="sxs-lookup"><span data-stu-id="03739-120">Activity</span></span>|<span data-ttu-id="03739-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="03739-121">xs:string</span></span>|<span data-ttu-id="03739-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="03739-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="03739-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="03739-123">DisplayName</span></span>|<span data-ttu-id="03739-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="03739-124">xs:string</span></span>|<span data-ttu-id="03739-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="03739-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="03739-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="03739-126">InstanceId</span></span>|<span data-ttu-id="03739-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="03739-127">xs:string</span></span>|<span data-ttu-id="03739-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="03739-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="03739-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="03739-129">AppDomain</span></span>|<span data-ttu-id="03739-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="03739-130">xs:string</span></span>|<span data-ttu-id="03739-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="03739-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
