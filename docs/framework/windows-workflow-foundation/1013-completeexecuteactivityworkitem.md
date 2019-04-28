---
title: 1013 - CompleteExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
ms.openlocfilehash: c1ff62bb4143bb798ea7adb7c3fee539ef68bc37
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925194"
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="752b4-102">1013 - CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="752b4-102">1013 - CompleteExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="752b4-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="752b4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="752b4-104">ID</span><span class="sxs-lookup"><span data-stu-id="752b4-104">ID</span></span>|<span data-ttu-id="752b4-105">1013</span><span class="sxs-lookup"><span data-stu-id="752b4-105">1013</span></span>|  
|<span data-ttu-id="752b4-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="752b4-106">Keywords</span></span>|<span data-ttu-id="752b4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="752b4-107">WFRuntime</span></span>|  
|<span data-ttu-id="752b4-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="752b4-108">Level</span></span>|<span data-ttu-id="752b4-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="752b4-109">Verbose</span></span>|  
|<span data-ttu-id="752b4-110">Канал</span><span class="sxs-lookup"><span data-stu-id="752b4-110">Channel</span></span>|<span data-ttu-id="752b4-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="752b4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="752b4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="752b4-112">Description</span></span>  
 <span data-ttu-id="752b4-113">Указывает, что ExecuteActivityWorkItem завершено</span><span class="sxs-lookup"><span data-stu-id="752b4-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="752b4-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="752b4-114">Message</span></span>  
 <span data-ttu-id="752b4-115">Завершено выполнение ExecuteActivityWorkItem для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="752b4-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="752b4-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="752b4-116">Details</span></span>  
  
|<span data-ttu-id="752b4-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="752b4-117">Data Item Name</span></span>|<span data-ttu-id="752b4-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="752b4-118">Data Item Type</span></span>|<span data-ttu-id="752b4-119">Описание</span><span class="sxs-lookup"><span data-stu-id="752b4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="752b4-120">Действие</span><span class="sxs-lookup"><span data-stu-id="752b4-120">Activity</span></span>|<span data-ttu-id="752b4-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="752b4-121">xs:string</span></span>|<span data-ttu-id="752b4-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="752b4-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="752b4-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="752b4-123">DisplayName</span></span>|<span data-ttu-id="752b4-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="752b4-124">xs:string</span></span>|<span data-ttu-id="752b4-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="752b4-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="752b4-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="752b4-126">InstanceId</span></span>|<span data-ttu-id="752b4-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="752b4-127">xs:string</span></span>|<span data-ttu-id="752b4-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="752b4-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="752b4-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="752b4-129">AppDomain</span></span>|<span data-ttu-id="752b4-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="752b4-130">xs:string</span></span>|<span data-ttu-id="752b4-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="752b4-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
