---
title: 1012 - StartExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
ms.openlocfilehash: d6b330bc454c39584e5027f757fd9d9d3434d941
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="2cbfb-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="2cbfb-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="2cbfb-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="2cbfb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2cbfb-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="2cbfb-104">ID</span></span>|<span data-ttu-id="2cbfb-105">1012</span><span class="sxs-lookup"><span data-stu-id="2cbfb-105">1012</span></span>|  
|<span data-ttu-id="2cbfb-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2cbfb-106">Keywords</span></span>|<span data-ttu-id="2cbfb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2cbfb-107">WFRuntime</span></span>|  
|<span data-ttu-id="2cbfb-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="2cbfb-108">Level</span></span>|<span data-ttu-id="2cbfb-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="2cbfb-109">Verbose</span></span>|  
|<span data-ttu-id="2cbfb-110">Канал</span><span class="sxs-lookup"><span data-stu-id="2cbfb-110">Channel</span></span>|<span data-ttu-id="2cbfb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2cbfb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2cbfb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2cbfb-112">Description</span></span>  
 <span data-ttu-id="2cbfb-113">Указывает на начало выполнения элемента ExecuteActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="2cbfb-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2cbfb-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2cbfb-114">Message</span></span>  
 <span data-ttu-id="2cbfb-115">Начато выполнение ExecuteActivityWorkItem для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="2cbfb-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2cbfb-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="2cbfb-116">Details</span></span>  
  
|<span data-ttu-id="2cbfb-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="2cbfb-117">Data Item Name</span></span>|<span data-ttu-id="2cbfb-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="2cbfb-118">Data Item Type</span></span>|<span data-ttu-id="2cbfb-119">Описание</span><span class="sxs-lookup"><span data-stu-id="2cbfb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2cbfb-120">Действие</span><span class="sxs-lookup"><span data-stu-id="2cbfb-120">Activity</span></span>|<span data-ttu-id="2cbfb-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2cbfb-121">xs:string</span></span>|<span data-ttu-id="2cbfb-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="2cbfb-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="2cbfb-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="2cbfb-123">DisplayName</span></span>|<span data-ttu-id="2cbfb-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2cbfb-124">xs:string</span></span>|<span data-ttu-id="2cbfb-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="2cbfb-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="2cbfb-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="2cbfb-126">InstanceId</span></span>|<span data-ttu-id="2cbfb-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="2cbfb-127">xs:string</span></span>|<span data-ttu-id="2cbfb-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="2cbfb-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="2cbfb-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2cbfb-129">AppDomain</span></span>|<span data-ttu-id="2cbfb-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="2cbfb-130">xs:string</span></span>|<span data-ttu-id="2cbfb-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2cbfb-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
