---
title: 1018 - StartCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
ms.openlocfilehash: 8d7045b0a7f31ecfd5dd90f319192bd202804353
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510657"
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="66004-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="66004-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="66004-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="66004-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="66004-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="66004-104">ID</span></span>|<span data-ttu-id="66004-105">1018</span><span class="sxs-lookup"><span data-stu-id="66004-105">1018</span></span>|  
|<span data-ttu-id="66004-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="66004-106">Keywords</span></span>|<span data-ttu-id="66004-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="66004-107">WFRuntime</span></span>|  
|<span data-ttu-id="66004-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="66004-108">Level</span></span>|<span data-ttu-id="66004-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="66004-109">Verbose</span></span>|  
|<span data-ttu-id="66004-110">Канал</span><span class="sxs-lookup"><span data-stu-id="66004-110">Channel</span></span>|<span data-ttu-id="66004-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="66004-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="66004-112">Описание</span><span class="sxs-lookup"><span data-stu-id="66004-112">Description</span></span>  
 <span data-ttu-id="66004-113">Указывает, что CancelActivityWorkItem начинает выполнение.</span><span class="sxs-lookup"><span data-stu-id="66004-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="66004-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="66004-114">Message</span></span>  
 <span data-ttu-id="66004-115">Начато выполнение CancelActivityWorkItem для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="66004-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="66004-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="66004-116">Details</span></span>  
  
|<span data-ttu-id="66004-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="66004-117">Data Item Name</span></span>|<span data-ttu-id="66004-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="66004-118">Data Item Type</span></span>|<span data-ttu-id="66004-119">Описание</span><span class="sxs-lookup"><span data-stu-id="66004-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="66004-120">Действие</span><span class="sxs-lookup"><span data-stu-id="66004-120">Activity</span></span>|<span data-ttu-id="66004-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="66004-121">xs:string</span></span>|<span data-ttu-id="66004-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="66004-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="66004-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="66004-123">DisplayName</span></span>|<span data-ttu-id="66004-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="66004-124">xs:string</span></span>|<span data-ttu-id="66004-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="66004-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="66004-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="66004-126">InstanceId</span></span>|<span data-ttu-id="66004-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="66004-127">xs:string</span></span>|<span data-ttu-id="66004-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="66004-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="66004-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="66004-129">AppDomain</span></span>|<span data-ttu-id="66004-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="66004-130">xs:string</span></span>|<span data-ttu-id="66004-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="66004-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
