---
title: 1034 - CompleteRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
ms.openlocfilehash: bd49c608a8f6a6caab6975850507a00a2c0edb03
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924557"
---
# <a name="1034---completeruntimeworkitem"></a><span data-ttu-id="9762b-102">1034 - CompleteRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="9762b-102">1034 - CompleteRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="9762b-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="9762b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9762b-104">ID</span><span class="sxs-lookup"><span data-stu-id="9762b-104">ID</span></span>|<span data-ttu-id="9762b-105">1034</span><span class="sxs-lookup"><span data-stu-id="9762b-105">1034</span></span>|  
|<span data-ttu-id="9762b-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="9762b-106">Keywords</span></span>|<span data-ttu-id="9762b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9762b-107">WFRuntime</span></span>|  
|<span data-ttu-id="9762b-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="9762b-108">Level</span></span>|<span data-ttu-id="9762b-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="9762b-109">Verbose</span></span>|  
|<span data-ttu-id="9762b-110">Канал</span><span class="sxs-lookup"><span data-stu-id="9762b-110">Channel</span></span>|<span data-ttu-id="9762b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="9762b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9762b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9762b-112">Description</span></span>  
 <span data-ttu-id="9762b-113">Указывает на завершение RuntimeWorkItem.</span><span class="sxs-lookup"><span data-stu-id="9762b-113">Indicates a RuntimeWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9762b-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="9762b-114">Message</span></span>  
 <span data-ttu-id="9762b-115">Рабочий элемент среды выполнения завершен для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="9762b-115">A runtime work item has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9762b-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="9762b-116">Details</span></span>  
  
|<span data-ttu-id="9762b-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="9762b-117">Data Item Name</span></span>|<span data-ttu-id="9762b-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="9762b-118">Data Item Type</span></span>|<span data-ttu-id="9762b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="9762b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9762b-120">Действие</span><span class="sxs-lookup"><span data-stu-id="9762b-120">Activity</span></span>|<span data-ttu-id="9762b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="9762b-121">xs:string</span></span>|<span data-ttu-id="9762b-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="9762b-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="9762b-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9762b-123">DisplayName</span></span>|<span data-ttu-id="9762b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="9762b-124">xs:string</span></span>|<span data-ttu-id="9762b-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="9762b-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="9762b-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="9762b-126">InstanceId</span></span>|<span data-ttu-id="9762b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="9762b-127">xs:string</span></span>|<span data-ttu-id="9762b-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="9762b-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="9762b-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="9762b-129">AppDomain</span></span>|<span data-ttu-id="9762b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="9762b-130">xs:string</span></span>|<span data-ttu-id="9762b-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9762b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
