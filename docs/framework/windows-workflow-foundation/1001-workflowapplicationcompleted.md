---
title: 1001 - WorkflowApplicationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 12b20ef893db12892636d73eeea2976f12bfccf9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="28147-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="28147-102">1001 - WorkflowApplicationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="28147-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="28147-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28147-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="28147-104">ID</span></span>|<span data-ttu-id="28147-105">1001</span><span class="sxs-lookup"><span data-stu-id="28147-105">1001</span></span>|  
|<span data-ttu-id="28147-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="28147-106">Keywords</span></span>|<span data-ttu-id="28147-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="28147-107">WFRuntime</span></span>|  
|<span data-ttu-id="28147-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="28147-108">Level</span></span>|<span data-ttu-id="28147-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="28147-109">Information</span></span>|  
|<span data-ttu-id="28147-110">Канал</span><span class="sxs-lookup"><span data-stu-id="28147-110">Channel</span></span>|<span data-ttu-id="28147-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="28147-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="28147-112">Описание</span><span class="sxs-lookup"><span data-stu-id="28147-112">Description</span></span>  
 <span data-ttu-id="28147-113">Указывает, что приложение рабочего процесса завершено в состоянии Closed.</span><span class="sxs-lookup"><span data-stu-id="28147-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="28147-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="28147-114">Message</span></span>  
 <span data-ttu-id="28147-115">Элемент WorkflowInstance с идентификатором «%1» завершил работу в состоянии Closed.</span><span class="sxs-lookup"><span data-stu-id="28147-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="28147-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="28147-116">Details</span></span>  
  
|<span data-ttu-id="28147-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="28147-117">Data Item Name</span></span>|<span data-ttu-id="28147-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="28147-118">Data Item Type</span></span>|<span data-ttu-id="28147-119">Описание</span><span class="sxs-lookup"><span data-stu-id="28147-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="28147-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="28147-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="28147-121">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="28147-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="28147-122">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="28147-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="28147-123">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="28147-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
