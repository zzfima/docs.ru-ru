---
title: 1013 - CompleteExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
ms.openlocfilehash: c1ff62bb4143bb798ea7adb7c3fee539ef68bc37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509578"
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="f39d5-102">1013 - CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="f39d5-102">1013 - CompleteExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="f39d5-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="f39d5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f39d5-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="f39d5-104">ID</span></span>|<span data-ttu-id="f39d5-105">1013</span><span class="sxs-lookup"><span data-stu-id="f39d5-105">1013</span></span>|  
|<span data-ttu-id="f39d5-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="f39d5-106">Keywords</span></span>|<span data-ttu-id="f39d5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f39d5-107">WFRuntime</span></span>|  
|<span data-ttu-id="f39d5-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="f39d5-108">Level</span></span>|<span data-ttu-id="f39d5-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="f39d5-109">Verbose</span></span>|  
|<span data-ttu-id="f39d5-110">Канал</span><span class="sxs-lookup"><span data-stu-id="f39d5-110">Channel</span></span>|<span data-ttu-id="f39d5-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f39d5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f39d5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f39d5-112">Description</span></span>  
 <span data-ttu-id="f39d5-113">Указывает, что ExecuteActivityWorkItem завершено</span><span class="sxs-lookup"><span data-stu-id="f39d5-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="f39d5-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f39d5-114">Message</span></span>  
 <span data-ttu-id="f39d5-115">Завершено выполнение ExecuteActivityWorkItem для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="f39d5-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f39d5-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="f39d5-116">Details</span></span>  
  
|<span data-ttu-id="f39d5-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="f39d5-117">Data Item Name</span></span>|<span data-ttu-id="f39d5-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="f39d5-118">Data Item Type</span></span>|<span data-ttu-id="f39d5-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f39d5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f39d5-120">Действие</span><span class="sxs-lookup"><span data-stu-id="f39d5-120">Activity</span></span>|<span data-ttu-id="f39d5-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f39d5-121">xs:string</span></span>|<span data-ttu-id="f39d5-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="f39d5-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="f39d5-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f39d5-123">DisplayName</span></span>|<span data-ttu-id="f39d5-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f39d5-124">xs:string</span></span>|<span data-ttu-id="f39d5-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="f39d5-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="f39d5-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f39d5-126">InstanceId</span></span>|<span data-ttu-id="f39d5-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f39d5-127">xs:string</span></span>|<span data-ttu-id="f39d5-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="f39d5-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f39d5-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f39d5-129">AppDomain</span></span>|<span data-ttu-id="f39d5-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="f39d5-130">xs:string</span></span>|<span data-ttu-id="f39d5-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f39d5-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
