---
title: 1034 - CompleteRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
ms.openlocfilehash: bd49c608a8f6a6caab6975850507a00a2c0edb03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1034---completeruntimeworkitem"></a><span data-ttu-id="cdfff-102">1034 - CompleteRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="cdfff-102">1034 - CompleteRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="cdfff-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="cdfff-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cdfff-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="cdfff-104">ID</span></span>|<span data-ttu-id="cdfff-105">1034</span><span class="sxs-lookup"><span data-stu-id="cdfff-105">1034</span></span>|  
|<span data-ttu-id="cdfff-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="cdfff-106">Keywords</span></span>|<span data-ttu-id="cdfff-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="cdfff-107">WFRuntime</span></span>|  
|<span data-ttu-id="cdfff-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="cdfff-108">Level</span></span>|<span data-ttu-id="cdfff-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="cdfff-109">Verbose</span></span>|  
|<span data-ttu-id="cdfff-110">Канал</span><span class="sxs-lookup"><span data-stu-id="cdfff-110">Channel</span></span>|<span data-ttu-id="cdfff-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="cdfff-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cdfff-112">Описание</span><span class="sxs-lookup"><span data-stu-id="cdfff-112">Description</span></span>  
 <span data-ttu-id="cdfff-113">Указывает на завершение RuntimeWorkItem.</span><span class="sxs-lookup"><span data-stu-id="cdfff-113">Indicates a RuntimeWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cdfff-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="cdfff-114">Message</span></span>  
 <span data-ttu-id="cdfff-115">Рабочий элемент среды выполнения завершен для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="cdfff-115">A runtime work item has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cdfff-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="cdfff-116">Details</span></span>  
  
|<span data-ttu-id="cdfff-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="cdfff-117">Data Item Name</span></span>|<span data-ttu-id="cdfff-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="cdfff-118">Data Item Type</span></span>|<span data-ttu-id="cdfff-119">Описание</span><span class="sxs-lookup"><span data-stu-id="cdfff-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cdfff-120">Действие</span><span class="sxs-lookup"><span data-stu-id="cdfff-120">Activity</span></span>|<span data-ttu-id="cdfff-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="cdfff-121">xs:string</span></span>|<span data-ttu-id="cdfff-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="cdfff-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="cdfff-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="cdfff-123">DisplayName</span></span>|<span data-ttu-id="cdfff-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="cdfff-124">xs:string</span></span>|<span data-ttu-id="cdfff-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="cdfff-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="cdfff-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="cdfff-126">InstanceId</span></span>|<span data-ttu-id="cdfff-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="cdfff-127">xs:string</span></span>|<span data-ttu-id="cdfff-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="cdfff-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="cdfff-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cdfff-129">AppDomain</span></span>|<span data-ttu-id="cdfff-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="cdfff-130">xs:string</span></span>|<span data-ttu-id="cdfff-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="cdfff-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
