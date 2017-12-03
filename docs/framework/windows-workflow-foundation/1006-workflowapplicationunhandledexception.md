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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7a2dad3135de6d3d96328ea039aa36906addb217
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="09cde-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="09cde-102">1006 - WorkflowApplicationUnhandledException</span></span>
## <a name="properties"></a><span data-ttu-id="09cde-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="09cde-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="09cde-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="09cde-104">ID</span></span>|<span data-ttu-id="09cde-105">1006</span><span class="sxs-lookup"><span data-stu-id="09cde-105">1006</span></span>|  
|<span data-ttu-id="09cde-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="09cde-106">Keywords</span></span>|<span data-ttu-id="09cde-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="09cde-107">WFRuntime</span></span>|  
|<span data-ttu-id="09cde-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="09cde-108">Level</span></span>|<span data-ttu-id="09cde-109">Ошибка</span><span class="sxs-lookup"><span data-stu-id="09cde-109">Error</span></span>|  
|<span data-ttu-id="09cde-110">Канал</span><span class="sxs-lookup"><span data-stu-id="09cde-110">Channel</span></span>|<span data-ttu-id="09cde-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="09cde-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="09cde-112">Описание</span><span class="sxs-lookup"><span data-stu-id="09cde-112">Description</span></span>  
 <span data-ttu-id="09cde-113">Указывает, что приложение рабочего процесса обнаружило необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="09cde-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="09cde-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="09cde-114">Message</span></span>  
 <span data-ttu-id="09cde-115">Элемент WorkflowInstance с идентификатором: «%1» обнаружил необрабатываемое исключение.</span><span class="sxs-lookup"><span data-stu-id="09cde-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="09cde-116">Возникло исключение из действия «%2», DisplayName: «%3».</span><span class="sxs-lookup"><span data-stu-id="09cde-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="09cde-117">Будут выполнены следующие действия: %4.</span><span class="sxs-lookup"><span data-stu-id="09cde-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="09cde-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="09cde-118">Details</span></span>  
  
|<span data-ttu-id="09cde-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="09cde-119">Data Item Name</span></span>|<span data-ttu-id="09cde-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="09cde-120">Data Item Type</span></span>|<span data-ttu-id="09cde-121">Описание</span><span class="sxs-lookup"><span data-stu-id="09cde-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="09cde-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="09cde-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="09cde-123">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="09cde-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="09cde-124">Исключение</span><span class="sxs-lookup"><span data-stu-id="09cde-124">Exception</span></span>|`xs:string`|<span data-ttu-id="09cde-125">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="09cde-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="09cde-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="09cde-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="09cde-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="09cde-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
