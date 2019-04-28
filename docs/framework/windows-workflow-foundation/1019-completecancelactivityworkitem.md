---
title: 1019 - CompleteCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
ms.openlocfilehash: 28d19742055c51ca94c36ffddf15dced7dfc14cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924440"
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="70036-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="70036-102">1019 - CompleteCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="70036-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="70036-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="70036-104">ID</span><span class="sxs-lookup"><span data-stu-id="70036-104">ID</span></span>|<span data-ttu-id="70036-105">1019</span><span class="sxs-lookup"><span data-stu-id="70036-105">1019</span></span>|  
|<span data-ttu-id="70036-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="70036-106">Keywords</span></span>|<span data-ttu-id="70036-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="70036-107">WFRuntime</span></span>|  
|<span data-ttu-id="70036-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="70036-108">Level</span></span>|<span data-ttu-id="70036-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="70036-109">Verbose</span></span>|  
|<span data-ttu-id="70036-110">Канал</span><span class="sxs-lookup"><span data-stu-id="70036-110">Channel</span></span>|<span data-ttu-id="70036-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="70036-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="70036-112">Описание</span><span class="sxs-lookup"><span data-stu-id="70036-112">Description</span></span>  
 <span data-ttu-id="70036-113">Указывает, что CancelActivityWorkItem завершено.</span><span class="sxs-lookup"><span data-stu-id="70036-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="70036-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="70036-114">Message</span></span>  
 <span data-ttu-id="70036-115">CancelActivityWorkItem завершен для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="70036-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="70036-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="70036-116">Details</span></span>  
  
|<span data-ttu-id="70036-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="70036-117">Data Item Name</span></span>|<span data-ttu-id="70036-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="70036-118">Data Item Type</span></span>|<span data-ttu-id="70036-119">Описание</span><span class="sxs-lookup"><span data-stu-id="70036-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="70036-120">Действие</span><span class="sxs-lookup"><span data-stu-id="70036-120">Activity</span></span>|<span data-ttu-id="70036-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="70036-121">xs:string</span></span>|<span data-ttu-id="70036-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="70036-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="70036-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="70036-123">DisplayName</span></span>|<span data-ttu-id="70036-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="70036-124">xs:string</span></span>|<span data-ttu-id="70036-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="70036-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="70036-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="70036-126">InstanceId</span></span>|<span data-ttu-id="70036-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="70036-127">xs:string</span></span>|<span data-ttu-id="70036-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="70036-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="70036-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="70036-129">AppDomain</span></span>|<span data-ttu-id="70036-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="70036-130">xs:string</span></span>|<span data-ttu-id="70036-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="70036-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
