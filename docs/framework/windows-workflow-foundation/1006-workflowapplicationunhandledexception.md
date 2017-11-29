---
title: 1006 - WorkflowApplicationUnhandledException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a03809be5e5d61c505e295e2f769a0298f770f7f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="eea24-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="eea24-102">1006 - WorkflowApplicationUnhandledException</span></span>
## <a name="properties"></a><span data-ttu-id="eea24-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="eea24-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eea24-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="eea24-104">ID</span></span>|<span data-ttu-id="eea24-105">1006</span><span class="sxs-lookup"><span data-stu-id="eea24-105">1006</span></span>|  
|<span data-ttu-id="eea24-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="eea24-106">Keywords</span></span>|<span data-ttu-id="eea24-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="eea24-107">WFRuntime</span></span>|  
|<span data-ttu-id="eea24-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="eea24-108">Level</span></span>|<span data-ttu-id="eea24-109">Ошибка</span><span class="sxs-lookup"><span data-stu-id="eea24-109">Error</span></span>|  
|<span data-ttu-id="eea24-110">Канал</span><span class="sxs-lookup"><span data-stu-id="eea24-110">Channel</span></span>|<span data-ttu-id="eea24-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="eea24-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="eea24-112">Описание</span><span class="sxs-lookup"><span data-stu-id="eea24-112">Description</span></span>  
 <span data-ttu-id="eea24-113">Указывает, что приложение рабочего процесса обнаружило необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="eea24-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="eea24-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="eea24-114">Message</span></span>  
 <span data-ttu-id="eea24-115">Элемент WorkflowInstance с идентификатором: «%1» обнаружил необрабатываемое исключение.</span><span class="sxs-lookup"><span data-stu-id="eea24-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="eea24-116">Возникло исключение из действия «%2», DisplayName: «%3».</span><span class="sxs-lookup"><span data-stu-id="eea24-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="eea24-117">Будут выполнены следующие действия: %4.</span><span class="sxs-lookup"><span data-stu-id="eea24-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="eea24-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="eea24-118">Details</span></span>  
  
|<span data-ttu-id="eea24-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="eea24-119">Data Item Name</span></span>|<span data-ttu-id="eea24-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="eea24-120">Data Item Type</span></span>|<span data-ttu-id="eea24-121">Описание</span><span class="sxs-lookup"><span data-stu-id="eea24-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="eea24-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="eea24-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="eea24-123">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="eea24-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="eea24-124">Исключение</span><span class="sxs-lookup"><span data-stu-id="eea24-124">Exception</span></span>|`xs:string`|<span data-ttu-id="eea24-125">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="eea24-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="eea24-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="eea24-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="eea24-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="eea24-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
