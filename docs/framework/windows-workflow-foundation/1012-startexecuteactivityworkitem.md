---
title: 1012 - StartExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
ms.openlocfilehash: d6b330bc454c39584e5027f757fd9d9d3434d941
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924583"
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="55943-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="55943-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="55943-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="55943-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="55943-104">ID</span><span class="sxs-lookup"><span data-stu-id="55943-104">ID</span></span>|<span data-ttu-id="55943-105">1012</span><span class="sxs-lookup"><span data-stu-id="55943-105">1012</span></span>|  
|<span data-ttu-id="55943-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="55943-106">Keywords</span></span>|<span data-ttu-id="55943-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="55943-107">WFRuntime</span></span>|  
|<span data-ttu-id="55943-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="55943-108">Level</span></span>|<span data-ttu-id="55943-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="55943-109">Verbose</span></span>|  
|<span data-ttu-id="55943-110">Канал</span><span class="sxs-lookup"><span data-stu-id="55943-110">Channel</span></span>|<span data-ttu-id="55943-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="55943-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="55943-112">Описание</span><span class="sxs-lookup"><span data-stu-id="55943-112">Description</span></span>  
 <span data-ttu-id="55943-113">Указывает на начало выполнения элемента ExecuteActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="55943-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="55943-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="55943-114">Message</span></span>  
 <span data-ttu-id="55943-115">Начато выполнение ExecuteActivityWorkItem для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="55943-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="55943-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="55943-116">Details</span></span>  
  
|<span data-ttu-id="55943-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="55943-117">Data Item Name</span></span>|<span data-ttu-id="55943-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="55943-118">Data Item Type</span></span>|<span data-ttu-id="55943-119">Описание</span><span class="sxs-lookup"><span data-stu-id="55943-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="55943-120">Действие</span><span class="sxs-lookup"><span data-stu-id="55943-120">Activity</span></span>|<span data-ttu-id="55943-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="55943-121">xs:string</span></span>|<span data-ttu-id="55943-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="55943-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="55943-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="55943-123">DisplayName</span></span>|<span data-ttu-id="55943-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="55943-124">xs:string</span></span>|<span data-ttu-id="55943-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="55943-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="55943-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="55943-126">InstanceId</span></span>|<span data-ttu-id="55943-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="55943-127">xs:string</span></span>|<span data-ttu-id="55943-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="55943-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="55943-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="55943-129">AppDomain</span></span>|<span data-ttu-id="55943-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="55943-130">xs:string</span></span>|<span data-ttu-id="55943-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="55943-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
