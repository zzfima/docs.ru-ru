---
title: "1004 ― WorkflowInstanceAborted"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7394ebbcb14850af89d906b0b573c4f677346825
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="dea87-102">1004 ― WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="dea87-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="dea87-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="dea87-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dea87-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="dea87-104">ID</span></span>|<span data-ttu-id="dea87-105">1004</span><span class="sxs-lookup"><span data-stu-id="dea87-105">1004</span></span>|  
|<span data-ttu-id="dea87-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="dea87-106">Keywords</span></span>|<span data-ttu-id="dea87-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="dea87-107">WFRuntime</span></span>|  
|<span data-ttu-id="dea87-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="dea87-108">Level</span></span>|<span data-ttu-id="dea87-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="dea87-109">Information</span></span>|  
|<span data-ttu-id="dea87-110">Канал</span><span class="sxs-lookup"><span data-stu-id="dea87-110">Channel</span></span>|<span data-ttu-id="dea87-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="dea87-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="dea87-112">Описание</span><span class="sxs-lookup"><span data-stu-id="dea87-112">Description</span></span>  
 <span data-ttu-id="dea87-113">Указывает, что экземпляр рабочего процесса был прерван с исключением.</span><span class="sxs-lookup"><span data-stu-id="dea87-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="dea87-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="dea87-114">Message</span></span>  
 <span data-ttu-id="dea87-115">Выполнение элемента WorkflowInstance с идентификатором «%1» было прервано в результате исключения.</span><span class="sxs-lookup"><span data-stu-id="dea87-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="dea87-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="dea87-116">Details</span></span>  
  
|<span data-ttu-id="dea87-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="dea87-117">Data Item Name</span></span>|<span data-ttu-id="dea87-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="dea87-118">Data Item Type</span></span>|<span data-ttu-id="dea87-119">Описание</span><span class="sxs-lookup"><span data-stu-id="dea87-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="dea87-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="dea87-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="dea87-121">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="dea87-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="dea87-122">Исключение</span><span class="sxs-lookup"><span data-stu-id="dea87-122">Exception</span></span>|`xs:string`|<span data-ttu-id="dea87-123">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="dea87-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="dea87-124">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="dea87-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="dea87-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="dea87-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
