---
title: 1002 - WorkflowApplicationTerminated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 93a6a400576df84faae3cd58940462255b0073c6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="13c09-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="13c09-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="13c09-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="13c09-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="13c09-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="13c09-104">ID</span></span>|<span data-ttu-id="13c09-105">1002</span><span class="sxs-lookup"><span data-stu-id="13c09-105">1002</span></span>|  
|<span data-ttu-id="13c09-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="13c09-106">Keywords</span></span>|<span data-ttu-id="13c09-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="13c09-107">WFRuntime</span></span>|  
|<span data-ttu-id="13c09-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="13c09-108">Level</span></span>|<span data-ttu-id="13c09-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="13c09-109">Information</span></span>|  
|<span data-ttu-id="13c09-110">Канал</span><span class="sxs-lookup"><span data-stu-id="13c09-110">Channel</span></span>|<span data-ttu-id="13c09-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="13c09-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="13c09-112">Описание</span><span class="sxs-lookup"><span data-stu-id="13c09-112">Description</span></span>  
 <span data-ttu-id="13c09-113">Указывает, что приложение рабочего процесса было остановлено в состоянии Faulted с исключением.</span><span class="sxs-lookup"><span data-stu-id="13c09-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="13c09-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="13c09-114">Message</span></span>  
 <span data-ttu-id="13c09-115">WorkflowApplication с идентификатором «%1» остановлено.</span><span class="sxs-lookup"><span data-stu-id="13c09-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="13c09-116">Был прерван в состоянии сбоя с исключением.</span><span class="sxs-lookup"><span data-stu-id="13c09-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="13c09-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="13c09-117">Details</span></span>  
  
|<span data-ttu-id="13c09-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="13c09-118">Data Item Name</span></span>|<span data-ttu-id="13c09-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="13c09-119">Data Item Type</span></span>|<span data-ttu-id="13c09-120">Описание</span><span class="sxs-lookup"><span data-stu-id="13c09-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="13c09-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="13c09-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="13c09-122">Идентификатор приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="13c09-122">The workflow application id</span></span>|  
|<span data-ttu-id="13c09-123">Исключение</span><span class="sxs-lookup"><span data-stu-id="13c09-123">Exception</span></span>|`xs:string`|<span data-ttu-id="13c09-124">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="13c09-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="13c09-125">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="13c09-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="13c09-126">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="13c09-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
