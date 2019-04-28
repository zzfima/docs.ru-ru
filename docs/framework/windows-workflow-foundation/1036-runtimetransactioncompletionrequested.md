---
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 649ba542a9ed2f330ac71e447602d637530dc601
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924843"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="2fb6c-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="2fb6c-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="2fb6c-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="2fb6c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2fb6c-104">ID</span><span class="sxs-lookup"><span data-stu-id="2fb6c-104">ID</span></span>|<span data-ttu-id="2fb6c-105">1036</span><span class="sxs-lookup"><span data-stu-id="2fb6c-105">1036</span></span>|  
|<span data-ttu-id="2fb6c-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2fb6c-106">Keywords</span></span>|<span data-ttu-id="2fb6c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2fb6c-107">WFRuntime</span></span>|  
|<span data-ttu-id="2fb6c-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="2fb6c-108">Level</span></span>|<span data-ttu-id="2fb6c-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="2fb6c-109">Verbose</span></span>|  
|<span data-ttu-id="2fb6c-110">Канал</span><span class="sxs-lookup"><span data-stu-id="2fb6c-110">Channel</span></span>|<span data-ttu-id="2fb6c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2fb6c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2fb6c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2fb6c-112">Description</span></span>  
 <span data-ttu-id="2fb6c-113">Указывает, что действие запланировало завершение транзакции среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2fb6c-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2fb6c-114">Message</span></span>  
 <span data-ttu-id="2fb6c-115">Действие «%1», DisplayName «%2», InstanceId «%3» запланировало завершение транзакции времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2fb6c-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="2fb6c-116">Details</span></span>  
  
|<span data-ttu-id="2fb6c-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="2fb6c-117">Data Item Name</span></span>|<span data-ttu-id="2fb6c-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="2fb6c-118">Data Item Type</span></span>|<span data-ttu-id="2fb6c-119">Описание</span><span class="sxs-lookup"><span data-stu-id="2fb6c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2fb6c-120">Действие</span><span class="sxs-lookup"><span data-stu-id="2fb6c-120">Activity</span></span>|<span data-ttu-id="2fb6c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2fb6c-121">xs:string</span></span>|<span data-ttu-id="2fb6c-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="2fb6c-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="2fb6c-123">DisplayName</span></span>|<span data-ttu-id="2fb6c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2fb6c-124">xs:string</span></span>|<span data-ttu-id="2fb6c-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="2fb6c-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="2fb6c-126">InstanceId</span></span>|<span data-ttu-id="2fb6c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="2fb6c-127">xs:string</span></span>|<span data-ttu-id="2fb6c-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="2fb6c-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="2fb6c-129">AppDomain</span></span>|<span data-ttu-id="2fb6c-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="2fb6c-130">xs:string</span></span>|<span data-ttu-id="2fb6c-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2fb6c-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
