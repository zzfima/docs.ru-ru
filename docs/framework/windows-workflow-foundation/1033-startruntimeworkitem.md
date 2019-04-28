---
title: 1033 - StartRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
ms.openlocfilehash: c7192ed7c5fb43fe6f65b47b8cebde3cf4aed32c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924245"
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="fcac5-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="fcac5-102">1033 - StartRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="fcac5-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="fcac5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fcac5-104">ID</span><span class="sxs-lookup"><span data-stu-id="fcac5-104">ID</span></span>|<span data-ttu-id="fcac5-105">1033</span><span class="sxs-lookup"><span data-stu-id="fcac5-105">1033</span></span>|  
|<span data-ttu-id="fcac5-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="fcac5-106">Keywords</span></span>|<span data-ttu-id="fcac5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fcac5-107">WFRuntime</span></span>|  
|<span data-ttu-id="fcac5-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="fcac5-108">Level</span></span>|<span data-ttu-id="fcac5-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="fcac5-109">Verbose</span></span>|  
|<span data-ttu-id="fcac5-110">Канал</span><span class="sxs-lookup"><span data-stu-id="fcac5-110">Channel</span></span>|<span data-ttu-id="fcac5-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fcac5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fcac5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fcac5-112">Description</span></span>  
 <span data-ttu-id="fcac5-113">Указывает, что начинается выполнение RuntimeWorkItem.</span><span class="sxs-lookup"><span data-stu-id="fcac5-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fcac5-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="fcac5-114">Message</span></span>  
 <span data-ttu-id="fcac5-115">Начато выполнение рабочего элемента среды выполнения для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="fcac5-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fcac5-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="fcac5-116">Details</span></span>  
  
|<span data-ttu-id="fcac5-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="fcac5-117">Data Item Name</span></span>|<span data-ttu-id="fcac5-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="fcac5-118">Data Item Type</span></span>|<span data-ttu-id="fcac5-119">Описание</span><span class="sxs-lookup"><span data-stu-id="fcac5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fcac5-120">Действие</span><span class="sxs-lookup"><span data-stu-id="fcac5-120">Activity</span></span>|<span data-ttu-id="fcac5-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="fcac5-121">xs:string</span></span>|<span data-ttu-id="fcac5-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="fcac5-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="fcac5-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="fcac5-123">DisplayName</span></span>|<span data-ttu-id="fcac5-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="fcac5-124">xs:string</span></span>|<span data-ttu-id="fcac5-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="fcac5-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="fcac5-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="fcac5-126">InstanceId</span></span>|<span data-ttu-id="fcac5-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="fcac5-127">xs:string</span></span>|<span data-ttu-id="fcac5-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="fcac5-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="fcac5-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="fcac5-129">AppDomain</span></span>|<span data-ttu-id="fcac5-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="fcac5-130">xs:string</span></span>|<span data-ttu-id="fcac5-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fcac5-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
